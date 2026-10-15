Done. Nothing was built here (this machine is x64 and has no MSYS2 install at `C:\msys64`); the output is documentation + an automation script to run on the ARM64 box.

## What the reference link actually contains

`https://filezilla-project.org/sourcecode.php` serves its body as AES-CBC ciphertext decrypted by inline JS. I fetched and decrypted it; the relevant content:

- Repository: `https://svn.filezilla-project.org/svn/FileZilla3`
- Latest source (trunk): `svn co https://svn.filezilla-project.org/svn/FileZilla3/trunk filezilla`
- Tags: `svn co https://svn.filezilla-project.org/svn/FileZilla3/tags/<version> ...`
- Compile instructions point to the wiki, which I also pulled:
  - `Client_Compile` → deps: libfilezilla, wxWidgets, GnuTLS, libidn, gettext, libdbus; plus Perl/libtool/autoconf/automake for SVN checkouts, then `autoreconf -i`
  - `Compiling_FileZilla_3_under_Windows` → full MSYS2 pipeline (GMP, Nettle, zlib, GnuTLS, SQLite, wxWidgets, libfilezilla, fzssh, then FileZilla). The wiki only documents **MINGW64/GCC**; I retargeted it to CLANGARM64.

## Deliverables

**`BUILD-FileZilla-trunk-msys2-clangarm64.md`** — step-by-step guide:
1. Prerequisites + verify `MSYSTEM=CLANGARM64`, `MINGW_PREFIX=/clangarm64`
2. `pacman -Syu` (repeat until clean)
3. `mingw-w64-clang-aarch64-toolchain`, autotools, meson/ninja, svn
4. Deps as native ARM64 packages (`mingw-w64-clang-aarch64-{gmp,nettle,gnutls,zlib,sqlite3,libidn2,pugixml,gettext-tools,wxwidgets3.2-msw}`) instead of hand-building
5. `PATH`/`PKG_CONFIG_PATH`/`CPPFLAGS`/`LDFLAGS` for `~/prefix`, `CC=clang`, `CXX=clang++`
6. libfilezilla trunk: `autoreconf -i` → `./configure --build=aarch64-w64-mingw32 --host=aarch64-w64-mingw32 --prefix=$HOME/prefix --enable-shared --disable-static` → `make && make install`
7. fzssh (meson/ninja) for `fzsftp.exe` / `fzputtygen.exe`
8. FileZilla trunk checkout/update, `autoreconf -i`, `./configure --build/--host=aarch64-w64-mingw32 --with-pugixml=builtin --with-wx-config=...`, `make -j$(nproc)`
9. ARM64-specific caveats: `src/fzshellext/32` cannot be built (no i686 compiler in CLANGARM64) — build `src/engine` + `src/interface` instead; stale `config.sub`/`config.guess` must be refreshed for the `aarch64-w64-mingw32` triple
10. `llvm-strip`, DLL collection for redistribution, troubleshooting table

**`build-filezilla-clangarm64.sh`** — runs the whole thing on the ARM64 machine:
```bash
# in the "MSYS2 CLANGARM64" shell
bash build-filezilla-clangarm64.sh
# existing checkout:   FZ_SRC=~/filezilla SKIP_PACMAN=1 bash build-filezilla-clangarm64.sh
```
It aborts unless `MSYSTEM=CLANGARM64`, installs/verifies deps via pkg-config, auto-detects `wx-config-3.2`, refreshes `config.sub`/`config.guess`, builds+installs libfilezilla trunk, `svn update`s (or checks out) FileZilla trunk, only passes `--disable-autoupdatecheck`/`--disable-shellext` if `configure --help` advertises them, falls back to `make -C src/engine && make -C src/interface` when the shell-extension dir breaks the full build, and finally reports `src/interface/.libs/filezilla.exe`.

Note on expectations: the FileZilla project does not test or support CLANGARM64; the pacman ARM64 package set (notably wxWidgets 3.2) is what makes it feasible, and the 32-bit Explorer shell extension is intentionally out of scope on ARM64.

Checklist:
- [x] Read reference page https://filezilla-project.org/sourcecode.php (AES/JS-encrypted body decrypted)
- [x] Extract official trunk SVN URLs (FileZilla3 + libfilezilla)
- [x] Read official wiki compile docs (Client_Compile + Compiling under Windows/MSYS2)
- [x] Write MSYS2 CLANGARM64 build guide (BUILD-FileZilla-trunk-msys2-clangarm64.md)
- [x] Write automated build script (build-filezilla-clangarm64.sh)
- [x] Confirm no build is executed on this x64 machine
- [x] Clean up temporary scraping artifacts
