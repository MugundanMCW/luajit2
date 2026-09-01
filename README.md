# CFG Learning Deck

A 30-slide beginner-friendly Markdown presentation that teaches **Control
Flow Graphs (CFGs)** from first principles up through LLVM IR, dominance,
loops, and SSA/PHI nodes.

File: [`CFG-Learning-Deck.md`](./CFG-Learning-Deck.md)

The deck is written as a [Marp](https://marp.app/) Markdown deck (slides are
separated by `---`, with a YAML frontmatter block at the top configuring the
theme). It renders equally well as plain Markdown if you just want to read
it top to bottom.

## Rendering the deck

### Option 1: Marp CLI (recommended — HTML or PDF slides)

```bash
npm install -g @marp-team/marp-cli

# Render to a self-contained HTML slideshow
marp CFG-Learning-Deck.md -o deck.html

# Render to PDF
marp CFG-Learning-Deck.md -o deck.pdf --allow-local-files

# Live preview while editing
marp -s CFG-Learning-Deck.md
```

### Option 2: VS Code

Install the **Marp for VS Code** extension, open
`CFG-Learning-Deck.md`, and use the built-in preview pane (it renders slide
boundaries and diagrams live).

### Option 3: Pandoc (reveal.js HTML)

```bash
pandoc CFG-Learning-Deck.md -t revealjs -s -o deck-revealjs.html \
  --slide-level=2
```

> Note: pandoc doesn't understand the Marp `<!-- Slide N -->` comments or
> frontmatter styling; the `---` separators still split slides correctly,
> but rendering will look plainer than with Marp.

## Content overview

| Section | Slides | Topics |
|---|---|---|
| 1. Why CFG exists | 1–3 | Motivation, control flow, CFG definition |
| 2. Basic Blocks | 4–6 | Basic block rules, leaders, building a CFG |
| 3. CFG terminology | 7–8 | Vocabulary, predecessors/successors |
| 4. Real-program CFGs | 9–16 | if/else, while, for, do-while, break/continue, switch, return/unreachable |
| 5. LLVM IR level | 17–19 | IR basic blocks, terminators, `dot-cfg`/`viewCFG` |
| 6. Dominance | 20–23 | Dominates, immediate dominator, dominator tree, dominance frontier |
| 7. Loops | 24–25 | Back edges, natural loops, nested loops |
| 8. CFG → SSA | 26–27 | PHI nodes, big-picture diagram |
| 9. LLVM backend | 28 | `BasicBlock` vs `MachineBasicBlock`, `DominatorTree` vs `MachineDominatorTree` |
| 10. Practical mastery | 29–30 | Universal CFG-drawing checklist, solved final challenge |

Every important term from the terminology checklist (control flow, CFG,
basic block, leader, entry/exit block, node, edge, predecessor, successor,
terminator, fall-through, conditional/unconditional branch, join/merge,
branch point, reachability, unreachable block, back edge, loop
header/body/exit, natural loop, nested loop, dominance, strict dominance,
immediate dominator, dominator tree, dominance frontier, SSA, PHI node,
`BasicBlock`, `MachineBasicBlock`, `DominatorTree`, `MachineDominatorTree`)
is explicitly introduced and explained with a worked example.