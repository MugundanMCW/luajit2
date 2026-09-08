Here is a complete breakdown of what the CI workflows do for building and publishing wheels:

---

## Wheel Building

### `.github/workflows/test-rust.yml` — "LiteLLM Rust" (the primary wheel-build workflow)

**Trigger:** `push` or `pull_request` on paths touching `litellm-rust/**`, `pyproject.toml`, `rust-toolchain.toml`, or related scripts.

**What it does in the `rust-test` job:**
1. Runs `cargo test` across the workspace
2. **`uv build --wheel --out-dir dist`** — builds the main native wheel. `uv build` delegates to **maturin** (the build backend declared in `pyproject.toml`) which compiles the `litellm-python-bridge` Rust crate into a `.whl` file.
3. Verifies the wheel: `python .github/scripts/verify_linux_native_wheel.py dist/*.whl`
4. Runs wheel integration tests: `python tests/test_litellm/rust_bridge/native_route_wheel_test.py dist/*.whl`
5. Runs pytest against the compiled extension: `make test-rust-extension`
6. Builds a second "panic-test" wheel: `uv build --wheel --out-dir panic-dist --config-setting "maturin.build-args=--features panic-test,extension-module"`
7. Smoke-tests it: `python .github/scripts/smoke_test_native_wheel.py panic-dist/*.whl`

This is a **CI validation workflow only** — the wheels are built and tested but not published anywhere.

### `.github/workflows/codspeed.yml` — "CodSpeed Benchmarks"

**Trigger:** `push`/`pull_request` to `main`/`litellm_internal_staging` on paths touching `litellm/**`, `tests/benchmarks/**`, `pyproject.toml`, or `uv.lock`.

Builds the wheel implicitly via `uv run --frozen` (which triggers maturin to compile the Rust extension as part of the editable install). The comment in the file explicitly notes this was moved out of the CodSpeed runner because the maturin build took 42 minutes inside `codspeed run` vs. under 3 minutes as a plain step. This is for **benchmarking only**, not distribution.

---

## Wheel Publishing

**There is no workflow that publishes wheels to PyPI.** A full scan of all 50 workflow files found zero occurrences of `pypi`, `twine upload`, `PYPI_TOKEN`, `pypi.org`, `uv publish`, or any trusted-publisher configuration. PyPI publishing is not automated through GitHub Actions in this repository.

---

## GitHub Release (not wheel publishing)

### `.github/workflows/create-release.yml` — "Create Release"

**Trigger:** Manual `workflow_dispatch` with a tag and a 40-char commit SHA.

Creates a GitHub release (git tag + auto-generated release notes + cosign Docker image verification section). It does **not** build or publish any wheels or packages. After creating the release it calls `create-release-branch.yml` to create a release branch.

---

## Summary

| Workflow | Builds wheel? | Publishes wheel? | Tool used |
|---|---|---|---|
| `test-rust.yml` | ✅ Yes (CI validation) | ❌ No | `uv build --wheel` → maturin |
| `codspeed.yml` | ✅ Implicitly (benchmarks) | ❌ No | `uv run --frozen` → maturin |
| `create-release.yml` | ❌ No | ❌ No | GitHub API only |
| All others | ❌ No | ❌ No | — |

The build tool is **`uv build --wheel`** backed by **maturin** (the build backend configured in `pyproject.toml` for the Rust extension). There is currently no automated PyPI publish step in any workflow.
