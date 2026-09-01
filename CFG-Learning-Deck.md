---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  section {
    font-size: 26px;
  }
  pre {
    font-size: 20px;
  }
  code {
    font-size: 0.9em;
  }
---

<!-- Slide 1 -->
# Control Flow Graphs (CFGs): From C Code to LLVM

### Learn to draw and reason about the CFG of any program

Why does a compiler need a CFG at all?

- Optimizations need to know **what can happen before / after** a piece of code.
- A compiler cannot optimize code by just reading it top-to-bottom like a human —
  it needs a precise, machine-readable model of **all possible execution paths**.
- The **Control Flow Graph (CFG)** is that model. It underlies:
  - Dead code elimination, constant propagation, loop optimizations
  - Register allocation
  - SSA construction (the form almost all modern compilers use internally)

> By the end of this deck, you will be able to take **any** unfamiliar C/C++ or
> LLVM IR function and systematically draw its CFG by hand.

---

<!-- Slide 2 -->
## What is "control flow"?

```cpp
int foo(int x) {
    int y = 10;
    y = y + x;
    return y;
}
```

- Normally, the CPU/interpreter executes statements **one after another**,
  top to bottom — this is called **sequential flow**.
- Some statements **change** this default path:
  - `if`, `else`, `switch` → conditional jumps
  - `for`, `while`, `do-while` → jumps backward
  - `break`, `continue`, `return`, `goto` → jumps forward/out

The core question a compiler must answer for every instruction is:

> **"Where can execution go next?"**

The CFG is simply the graph of answers to that question, for every point
in the program.

---

<!-- Slide 3 -->
## What is a CFG?

**Control Flow Graph = a directed graph representing every possible path
control can take through a function.**

- **Node** = a *Basic Block* (a chunk of straight-line code)
- **Edge** = a possible transfer of control from one block to another
- The graph is **directed** (edges have a direction — "flows to")
- Usually **one entry** block, and **one or more exit** blocks

```text
        Entry
          |
          v
       Block A
          |
          v
       Block B
          |
          v
        Exit
```

Every C/C++ function, and every LLVM IR function, has exactly one CFG.
Our whole job in this deck is: **given code, produce this picture.**

---

<!-- Slide 4 -->
## What is a Basic Block?

A **basic block** is a maximal sequence of instructions such that:

1. It has exactly **one entry point** (the first instruction — nobody jumps
   into the middle of it).
2. It has exactly **one exit point** (the last instruction — a "terminator"
   that decides where to go next: branch, return, jump).
3. It contains **straight-line code** — if you execute the first instruction,
   you are guaranteed to execute *every* instruction in the block, in order.

> Once execution enters a basic block, all its instructions execute in
> sequence until the terminator fires. No shortcuts, no exits mid-block.

```cpp
int y = 10;     // ---
y = y + x;      //  one basic block: no jumps in or out of the middle
return y;       // ---
```

This whole function body above is **one single basic block** — there is no
branching at all.

---

<!-- Slide 5 -->
## How to identify Basic Blocks — the "Leader" method

A **leader** is the first instruction of a basic block. Once you find all
leaders, each basic block = a leader + every instruction up to (but not
including) the next leader.

**Leader rules:**

1. The **first** instruction of the function is a leader.
2. Any instruction that is the **target of a branch/jump** is a leader.
3. Any instruction that **immediately follows a branch/jump** (including
   the "fall-through" after a conditional) is a leader.

```cpp
1  int x = 10;
2  if (x > 5)
3      x = 20;
4  else
5      x = 30;
6  x++;
7  return x;
```

Walkthrough:
- Line **1** → leader (rule 1: first instruction).
- Line **2** is the `if` — its condition/branch is part of the block started at 1.
- Line **3** → leader (rule 3: target of the "true" branch from line 2).
- Line **5** → leader (rule 3: target of the "false" branch / fall-through of `else`).
- Line **6** → leader (rule 2/3: target that both line 3 and line 5 jump to).

**Basic blocks:** `B1 = {1,2}`, `B2 = {3}`, `B3 = {5}`, `B4 = {6,7}`

---

<!-- Slide 6 -->
## From Basic Blocks to CFG

Using the leaders from Slide 5, connect blocks by **who can jump to whom**:

```text
             B1
         (x = 10; x>5?)
              |
          x > 5?
          /     \
       true     false
         v         v
        B2       B3
      (x=20)   (x=30)
         \       /
          \     /
            v
            B4
        (x++; return x)
             |
             v
            Exit
```

Labels:
- **Entry** = B1 (first block executed)
- **Exit** = after B4's `return`
- **Branch point** = B1 (two outgoing edges: true/false)
- **Join / Merge point** = B4 (two incoming edges from B2 and B3)
- **Edges**: B1→B2, B1→B3, B2→B4, B3→B4

This B1→(B2,B3)→B4 "diamond" shape is the single most common CFG pattern
you'll see — memorize its shape, not the example.

---

<!-- Slide 7 -->
## CFG vocabulary

| Term | Meaning | Tiny example |
|---|---|---|
| **Node** | A basic block in the graph | `B1`, `B2`, ... |
| **Edge** | A possible control transfer, node → node | `B1 → B2` |
| **Basic block** | Straight-line code, one entry/one exit | see Slide 4 |
| **Entry block** | The block executed first | `B1` above |
| **Exit block** | A block ending in `return` (or unreachable end) | `B4` above |
| **Predecessor** | A node with an edge *into* this node | `pred(B4)={B2,B3}` |
| **Successor** | A node with an edge *out of* this node | `succ(B1)={B2,B3}` |
| **Branch** | A terminator with 2+ possible successors | `if (x>5)` |
| **Fall-through** | Reaching the next block without an explicit jump | `if` with no `else` |
| **Join / Merge** | A node with 2+ predecessors | `B4` above |
| **Terminator** | The last instruction of a block; decides successors | `br`, `ret`, `switch` |

---

<!-- Slide 8 -->
## Predecessors and Successors

```text
       B1
      /  \
     B2  B3
      \  /
       B4
        |
       B5
```

Reading edges **out** of a node gives its **successors**;
reading edges **into** a node gives its **predecessors**.

- `succ(B1) = {B2, B3}` — B1 branches two ways
- `pred(B1) = {}` — B1 is the entry, nothing flows into it
- `succ(B4) = {B5}`
- `pred(B4) = {B2, B3}` — a **join point**: 2 predecessors
- `succ(B5) = {}`, this is the **exit block**

**Key insight:** a block can have *multiple* predecessors (a join) and/or
*multiple* successors (a branch) — these are not mutually exclusive.
`pred`/`succ` sets are exactly what LLVM's `pred_begin/pred_end` and
`succ_begin/succ_end` iterators expose on `llvm::BasicBlock`.

---

<!-- Slide 9 -->
## CFG for if / else

```cpp
if (x > 10)
    foo();
else
    bar();

baz();
```

```text
             Entry
               |
          x > 10?
          /     \
       true     false
         |         |
        foo       bar
         |         |
          \       /
           \     /
             v
            baz
             |
            Exit
```

Why each edge exists:
- `Entry → foo`: taken when the condition is **true**.
- `Entry → bar`: taken when the condition is **false**.
- `foo → baz` and `bar → baz`: after either branch finishes, control always
  **falls through / jumps** to the code after the `if/else` — this is the
  **join point**.

---

<!-- Slide 10 -->
## CFG for if without else

```cpp
if (x > 10)
    foo();

bar();
```

```text
             Entry
               |
          x > 10?
          /     \
       true     false
         |         |
        foo        |
         |         |
          \       /
           \     /
             v
            bar
             |
            Exit
```

**Key difference from Slide 9:** there is no `else` block, so the
**false** edge goes **directly** to `bar()` instead of to a separate
block. This direct "condition-false" edge to the join point is exactly
what "fall-through" means: skipping the `if` body entirely.

Compare: the shape is still a diamond, just with one side "empty."

---

<!-- Slide 11 -->
## CFG for while loop

```cpp
while (x < 10) {
    x++;
}
```

```text
        Entry
          |
          v
       Header
       x < 10?
       /     \
     yes      no
      |        |
      v        v
    Body      Exit
      |
      +-------> Header   (back edge)
```

New vocabulary:
- **Loop header**: the block containing the loop condition — every
  iteration re-enters here. It's the only block with an edge coming
  *from later in the loop* (the back edge).
- **Loop body**: executes if the condition is true.
- **Back edge**: `Body → Header`, an edge that goes **backward** to a
  block that dominates it (more on dominance later) — this is the
  formal signature of a loop.
- **Loop exit**: the `no` edge, `Header → Exit`.

---

<!-- Slide 12 -->
## CFG for for loop

```cpp
for (int i = 0; i < 10; i++) {
    foo(i);
}
```

```text
       Init
        |
        v
      Cond <---------+
      /   \          |
   true   false      |
    |       |        |
   Body    Exit      |
    |                |
    v                |
   Inc ---------------+
```

A `for` loop is just syntactic sugar over 4 pieces glued with a back edge:

- **Init** runs once (`i = 0`), always falls through to `Cond`.
- **Cond** is the loop header (`i < 10`).
- **Body** runs the loop's statements (`foo(i)`).
- **Inc** runs the increment (`i++`), then jumps **back** to `Cond`.

Mentally rewrite every `for` as an equivalent `while` — the CFG shape is
identical; only where the increment textually lives differs.

---

<!-- Slide 13 -->
## do-while loop

```cpp
do {
    x++;
} while (x < 10);
```

```text
        Entry
          |
          v
        Body      <-------+
      (x++)                |
          |                |
          v                |
       Cond?                |
       x < 10?               |
       /     \               |
     yes------+ (back edge)  |
       \                    |
        no                  |
         |                  |
         v                  |
        Exit
```

**Key difference from `while`:** the **body executes before the condition
is ever checked** — there is an unconditional edge `Entry → Body`, with no
test in front of it. The condition check happens **after** the body, and
only the back edge (`Cond → Body`, on `yes`) closes the loop.

So `do-while` guarantees ≥ 1 execution; plain `while`/`for` guarantee 0+.

---

<!-- Slide 14 -->
## break and continue

```cpp
while (x < 10) {
    x++;
    if (x == 5)
        break;
    if (x == 3)
        continue;
    foo();
}
```

```text
        Header (x<10?) <-------------------+
        /     \                            |
      yes      no --> Exit                 |
       |                                    |
       v                                    |
     x++                                    |
       |                                    |
      x==5? --yes--> [break] --------> Exit |
       |no                                  |
      x==3? --yes--> [continue] ------------+
       |no
      foo() ------------------------------->+ (back to Header)
```

> **`break`** creates an edge straight to the loop's **Exit** block —
> it skips all remaining loop code, including the condition re-check.
>
> **`continue`** creates an edge straight to the loop's **Header** (or, in
> a `for` loop, to the **Increment** block) — it skips the rest of the
> body but *does* re-check the loop condition (or run the increment first).

---

<!-- Slide 15 -->
## switch statement

```cpp
switch (x) {
case 1:
    foo();
    break;
case 2:
    bar();
    break;
default:
    baz();
}
```

```text
                 Entry
                   |
              switch(x)
             /     |      \
          x==1   x==2    default
            |      |        |
           foo    bar      baz
            |      |        |
          break  break       |
            \      |        /
             \     |       /
              v    v      v
                  Exit
```

- A `switch` terminator can have **many** outgoing edges (one per case,
  plus `default`) — unlike `if`, which has at most 2.
- Each `case` label marks the start of a new basic block (it's a branch
  **target** → leader rule 2).
- `break` inside a case sends control to the block **after** the switch
  (the join point), same idea as `break` in a loop.
- Without `break`, control would **fall through** to the next case block
  — an important C/C++ gotcha that is directly visible as a CFG edge.

---

<!-- Slide 16 -->
## return, unreachable, and multiple exits

```cpp
int foo(int error) {
    if (error)
        return -1;
    return 0;
}
```

```text
        Entry
          |
       error?
       /     \
     yes      no
      |        |
   return -1  return 0
      |        |
    Exit1    Exit2
```

- Each `return` ends a basic block — it's a **terminator**, just like `br`.
- A function can have **multiple exit blocks** (one per `return` site).
- **Unreachable code**: code that no path from Entry can ever reach
  (e.g. code after an unconditional `return`, or after `while(true){}`
  with no `break`). LLVM marks such a block's terminator as
  `unreachable` — it tells the optimizer "execution can never get here;
  you're free to assume anything."

```cpp
void bar() {
    return;
    foo();   // <-- unreachable: dead basic block, no predecessors
}
```

---

<!-- Slide 17 -->
## LLVM IR Basic Blocks

Compiling `if (x > 10) then... else...` produces LLVM IR that mirrors the
CFG diagram *exactly*:

```llvm
define i32 @foo(i32 %x) {
entry:
    %cmp = icmp sgt i32 %x, 10
    br i1 %cmp, label %then, label %else

then:
    ; ... body ...
    br label %merge

else:
    ; ... body ...
    br label %merge

merge:
    ; ... 
    ret i32 %x
}
```

- `entry:`, `then:`, `else:`, `merge:` are **basic block labels** —
  each label is exactly a node in our hand-drawn CFG.
- Every block ends with a **terminator instruction** (`br` or `ret`) —
  this is LLVM enforcing the "one exit point" basic-block rule from
  Slide 4 as a hard structural invariant, not just a convention.
- `llvm::BasicBlock` is the C++ class representing each of these nodes.

---

<!-- Slide 18 -->
## LLVM CFG rules: terminators define edges

> **Every LLVM basic block must end with exactly one terminator
> instruction.** No exceptions — IR without a terminator is invalid.

Terminator instructions and the edges they create:

| Terminator | Successors it creates |
|---|---|
| `br label %X` | Unconditional edge → `%X` |
| `br i1 %c, label %T, label %F` | Two edges → `%T` (true), `%F` (false) |
| `switch i32 %v, label %def [ ... ]` | One edge per case + `%def` |
| `ret ...` | **No** successors (this is an exit block) |
| `unreachable` | **No** successors (this block is provably dead) |
| `invoke ... to label %normal unwind label %lpad` | Edge to `%normal` (no exception) + `%lpad` (exception) |
| `indirectbr` | Edges to a computed set of possible targets |
| `callbr` | Edges to normal + inline-asm-selected labels |

The CFG of an LLVM function is **derived automatically** by scanning the
terminator of each block — nothing else is needed to build it.

---

<!-- Slide 19 -->
## LLVM CFG visualization — checking your work

You don't have to draw CFGs blind — LLVM can show you the *real* answer,
so you can check your hand-drawn diagram against ground truth.

**From the command line** (produces Graphviz `.dot` files, viewable with
`xdot`, `dot -Tpng`, or online viewers):

```bash
opt -passes='dot-cfg' input.ll
# writes .dot files like .foo.dot per function, describing the CFG
```

**From inside a debugger** (e.g. `lldb`/`gdb`, when stopped in LLVM's own
code, on any `Function*` or `BasicBlock*` object `F`):

```text
(lldb) call F->viewCFG()       // opens a graphical CFG for the whole function
(lldb) call F->viewCFGOnly()   // same, but omits instruction text (structure only)
```

**Workflow:** draw your CFG by hand from the source → compile with
`clang -S -emit-llvm` → run `opt -passes='dot-cfg'` → compare shapes.
Differences usually mean you missed a leader or an edge.

---

<!-- Slide 20 -->
## What does "dominate" mean?

```text
        Entry
          |
          A
         / \
        B   C
         \ /
          D
          |
          E
```

> **Node D dominates node E** if **every** path from Entry to E must
> pass through D.

Walking the examples above:
- **A dominates B, C, D, E** — the only way to reach any of them from
  Entry is through A.
- **B does *not* dominate D** — there's a path Entry→A→C→D that never
  visits B.
- **D dominates E** — the only path to E goes through D.
- Every node **trivially dominates itself** (D dominates D).

**Strict dominance**: D *strictly* dominates E if D dominates E **and**
D ≠ E. (Excludes the "dominates itself" trivial case — useful when you
want to talk about dominators *other than the node itself*.)

---

<!-- Slide 21 -->
## Immediate Dominator

> The **immediate dominator** of node E (written `idom(E)`) is E's
> **closest** strict dominator — the last strict dominator you pass
> through right before reaching E.

Using the same CFG:

```text
        Entry
          |
          A
         / \
        B   C
         \ /
          D
          |
          E
```

- Strict dominators of **D**: `{Entry, A}` → closest is **A** →
  `idom(D) = A`.
- Strict dominators of **E**: `{Entry, A, D}` → closest is **D** →
  `idom(E) = D`.
- Strict dominators of **B**: `{Entry, A}` → closest is **A** →
  `idom(B) = A`.
- `idom(Entry)` does not exist (Entry has no strict dominator).

Every node (except Entry) has **exactly one** immediate dominator —
this uniqueness is what lets us build a *tree* next.

---

<!-- Slide 22 -->
## Dominator Tree

Take every node's `idom()` from Slide 21 and draw it as a parent-child
relationship:

```text
CFG:                      Dominator Tree:

    Entry                     Entry
      |                         |
      A                         A
     / \                     /  |  \
    B   C                   B   C   D
     \ /                            |
      D                             E
      |
      E
```

**CFG ≠ Dominator Tree — this is critical:**
- The **CFG** shows *actual control-flow edges* (B→D, C→D both exist).
- The **Dominator Tree** shows *dominance*, a different relationship —
  D's parent is A (its immediate dominator), **not** B or C, even
  though B and C are D's CFG predecessors.

**Why compilers care:** if you prove a fact about a value at node A, and
node X is a descendant of A in the dominator tree, that fact is
guaranteed to still hold at X — because *every* path to X went through A.
This underlies constant propagation, LICM, and SSA construction.

---

<!-- Slide 23 -->
## Dominance Frontier

Forget the formal definition for now. Start with the intuitive question:

> **"Where do different control-flow paths come back together?"**

```cpp
if (condition)
    x = 10;   // path 1
else
    x = 20;   // path 2

use(x);       // <-- paths REJOIN here
```

```text
        Entry
          |
       condition
       /       \
      /         \
   x=10        x=20
      \         /
       \       /
        Merge   <-- this is exactly where the "different worlds" meet
          |
       use(x)
```

`Merge` is where **two definitions of `x`** (from `x=10` and `x=20`)
both reach — it's in the **dominance frontier** of both the `x=10` block
and the `x=20` block. Formally: node F is in the dominance frontier of
node D if D dominates a predecessor of F, but D does **not** strictly
dominate F itself. Intuitively: F is the *first place* D's influence
"runs out" because another path also arrives. This is precisely where
compilers must insert **PHI nodes** (Slide 26).

---

<!-- Slide 24 -->
## Back edges and natural loops

```text
        Entry
          |
          v
       Header  <----------+
       /    \              |
     Exit   Body           |
              |             |
              +-------------+
              (back edge)
```

- **Back edge**: an edge `X → Y` where **Y dominates X**. This is the
  *formal* test for a loop — much stronger than "goes upward in the
  source text."
- **Loop header**: the target of the back edge (`Header`, here) — the
  single entry point into the loop.
- **Loop body**: everything reachable from Header that eventually
  reaches back to Header without leaving.
- **Loop exit**: any edge leaving the loop body (`Header → Exit`, or a
  `break` edge).
- **Natural loop**: the set of blocks that (a) includes the header,
  (b) all other blocks are reachable from the header, and (c) all can
  reach back to the header **without going through Entry** — i.e. a
  loop with exactly one entry point (the header). Nearly all loops
  written in structured C/C++ (`for`, `while`, `do-while`) are natural.

---

<!-- Slide 25 -->
## Nested loops

```cpp
while (outerCond) {
    while (innerCond) {
        foo();
    }
}
```

```text
       Entry
         |
         v
   OuterHeader <------------------+
     /      \                     |
  OuterExit  v                    |
        InnerHeader <----+        |
          /      \        |       |
     (join)      InnerBody|       |
          |         |     |       |
          |         +-----+       |
          |     (inner back edge) |
          v                       |
     (back to OuterHeader) -------+
     (outer back edge)
```

- **Outer loop**: header = `OuterHeader`, back edge from bottom of the
  outer body → `OuterHeader`.
- **Inner loop**: header = `InnerHeader`, back edge `InnerBody →
  InnerHeader`. This is a **natural loop nested inside** the outer
  loop's body.
- **Loop nesting depth**: `InnerHeader`/`InnerBody` are at depth 2;
  `OuterHeader` is at depth 1. LLVM's `LoopInfo` pass computes this
  nesting automatically from back edges + dominance, exposing it as a
  tree of `Loop` objects (`getLoopDepth()`, `getSubLoops()`).

---

<!-- Slide 26 -->
## Why CFG matters for SSA

```cpp
if (condition)
    x = 10;
else
    x = 20;

use(x);
```

```text
        Entry
          |
       condition
       /       \
      /         \
   x=10        x=20
      \         /
       \       /
        Merge
          |
       use(x)
```

At `Merge`, **which** definition of `x` is live? It depends on which
branch was taken — there is no single answer in text form. **SSA (Static
Single Assignment)** solves this by giving each definition of `x` a
unique name, and inserting a special instruction at the merge point that
says "pick the right one based on which predecessor we came from":

```llvm
%x = phi i32 [ 10, %then ], [ 20, %else ]
```

The **PHI node**'s operand list is literally `[value, predecessor-block]`
pairs — **one entry per CFG predecessor of the block containing the
PHI**. The CFG (specifically, the dominance frontier from Slide 23)
tells the compiler *exactly* which blocks need a PHI and for which
variables.

---

<!-- Slide 27 -->
## Big picture: how it all connects

```text
              Program
                 |
                 v
            Basic Blocks
             (Leaders)
                 |
                 v
                CFG
       (nodes + edges + terminators)
                 |
        +--------+--------+
        |        |        |
        v        v        v
    Dominance  Loops   Reachability
    (idom, DT)  (back    (unreachable
        |       edges)    blocks)
        v
Dominator Tree
        |
        v
Dominance Frontier
   ("where paths rejoin")
        |
        v
       SSA
   (unique variable names)
        |
        v
      PHI nodes
  (merge values at joins)
```

Every box above starts from the **same CFG**. This is why getting
comfortable *drawing* CFGs by hand (Slides 4–16) is the single highest-
leverage skill for understanding the rest of a compiler's middle-end.

---

<!-- Slide 28 -->
## LLVM IR CFG vs Machine CFG

The exact same node/edge/dominance ideas apply **twice** in LLVM's
pipeline — once at IR level, once after instruction selection:

```text
LLVM IR                       Machine IR
   ↓                             ↓
BasicBlock                MachineBasicBlock
   ↓                             ↓
  CFG                       Machine CFG
   ↓                             ↓
DominatorTree            MachineDominatorTree
```

| IR level | Machine level |
|---|---|
| `llvm::BasicBlock` | `llvm::MachineBasicBlock` |
| `llvm::Function` | `llvm::MachineFunction` |
| `llvm::DominatorTree` | `llvm::MachineDominatorTree` |
| `br`, `switch`, `ret` | target branch instructions (`JMP`, `Bcc`, ...) |

**Why CFG analysis still matters after instruction selection:**
register allocation, instruction scheduling, branch folding, and
machine-level loop optimizations (e.g. `MachineLoopInfo`) all need to
know predecessors/successors/dominance **again**, because the shape of
the graph (and sometimes even the block boundaries) can change during
lowering — e.g. a single IR block might split into several
`MachineBasicBlock`s, or blocks might be merged/reordered.

---

<!-- Slide 29 -->
## The universal CFG-drawing procedure

Use this checklist on **any** unfamiliar program:

```text
 1. Find the entry (first statement of the function).
 2. Scan top to bottom; mark every branch, jump, and return.
 3. Apply the leader rules:
      - first instruction
      - branch/jump targets
      - instructions right after a branch/jump
 4. Split the instruction stream into basic blocks at each leader.
 5. Give each block a label (B0, B1, B2, ... or entry/then/else/...).
 6. Identify each block's terminator (br / switch / ret / fall-through).
 7. Draw one edge per possible successor of each terminator.
 8. List predecessors and successors for every block.
 9. Look for back edges (edge X->Y where Y dominates X) -> loops.
10. Look for join points (2+ predecessors) -> merge / PHI candidates.
11. Check reachability: any block with pred() = {} other than Entry
    is unreachable/dead.
12. Sanity check: every edge you drew out of a block must correspond
    to exactly one possible outcome of that block's terminator.
```

Print this slide. Use it every single time until it's automatic.

---

<!-- Slide 30 -->
## Final challenge

Before looking at the solution below, work through the checklist
yourself on this function:

```cpp
int foo(int x) {
    int y = 0;

    if (x > 0) {
        y = 10;

        while (x < 5) {
            x++;

            if (x == 3)
                continue;

            y++;
        }
    } else {
        y = -10;
    }

    return y;
}
```

Do the following **on paper** first:
1. Identify leaders. 2. Create basic blocks. 3. Draw the CFG.
4. Label predecessors/successors. 5. Identify the loop header.
6. Identify the back edge. 7. Identify join points.
8. Identify dominance relationships (what dominates the `return`?).
9. Predict where a PHI node is required (hint: for `y`, and for `x`).
10. Compare your answer with the solution below.

### Solution to the final challenge

```text
B0 (entry): y = 0; if (x > 0) ?
   succ: B1 (true), B5 (false)      pred: {}

B1: y = 10;  [falls through into loop header]
   succ: B2                          pred: {B0}

B2 (loop header): x < 5 ?
   succ: B3 (true/body), B4 (false/exit)   pred: {B1, B3-continue-path}

B3: x++; if (x == 3) ?
   succ: B3a (true: continue), B3b (false)   pred: {B2}

B3a: [continue] -> jumps straight back to B2
   succ: B2                          pred: {B3}

B3b: y++;  -> falls through, back edge to B2
   succ: B2  (BACK EDGE: B3b -> B2, B2 dominates B3b)
                                      pred: {B3}

B4 (loop exit): [falls through to merge]
   succ: B6                          pred: {B2}

B5 (else): y = -10;
   succ: B6                          pred: {B0}

B6 (merge/return): return y;
   succ: {} (Exit)                   pred: {B4, B5}
```

- **Loop header** = B2. **Back edges** = `B3a -> B2` and `B3b -> B2`.
- **Join points** = B2 (two predecessors: B1 and the loop body paths)
  and B6 (two predecessors: B4 and B5).
- **Dominance**: B0 dominates everything. B6 (`return`) is dominated by
  B0 only — both B4 and B5 reach it, so nothing *between* B0 and B6
  strictly dominates B6.
- **PHI nodes required**: at **B2**, a PHI for `x` (incoming from B1 and
  from B3a/B3b); at **B6**, a PHI for `y` (incoming from B4 and B5) —
  exactly at the join points identified above.