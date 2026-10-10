---
name: rust-development
description: Use for writing, refactoring, or reviewing Rust code - crate and workspace layout, public API design, errors, async and performance, unsafe and FFI, docs, tests, and linting.
---

# rust-development

Rust guidance for any repository. Read the repository's `AGENTS.md` first: its
rules about crate boundaries, build commands, and how often to build win over
anything here.

## Pick The Reference

Read only the files the change needs.

| When the work is about | Read |
| --- | --- |
| Any Rust change: ownership, types, traits, error handling style | [core-rust-principles.md](references/core-rust-principles.md) |
| Workspace layout, crates, features, modules, dependencies | [cargo-workspace-and-crates.md](references/cargo-workspace-and-crates.md) |
| A reusable crate or public API: naming, builders, library errors, interoperability | [library-api-design.md](references/library-api-design.md) |
| A binary or service: runtime setup, app-level errors, logging | [application-runtime-and-errors.md](references/application-runtime-and-errors.md) |
| Hot paths, allocation, throughput, async tasks, blocking work | [performance-and-async.md](references/performance-and-async.md) |
| `unsafe`, soundness, FFI, raw pointers, platform calls | [safety-unsafe-and-ffi.md](references/safety-unsafe-and-ffi.md) |
| Rustdoc, crate and module docs, examples | [documentation-and-examples.md](references/documentation-and-examples.md) |
| Tests, Clippy, formatting, verification commands | [testing-linting-and-verification.md](references/testing-linting-and-verification.md) |
| Reviewing Rust code or a risky change | [rust-review-checklist.md](references/rust-review-checklist.md) |

Where the guidance comes from: [source-attribution.md](references/source-attribution.md).

## Working Rules

- Match the surrounding code: its error types, module layout, naming, and
  test style.
- Keep external systems behind the repository's ports and adapters; do not
  reach around a boundary to make a change smaller.
- When a change adds or alters public HTTP behavior, update the API contract,
  the client SDK, and the CLI in the same change if the repository has them.
- Compile and test with the repository's own commands, as often as it allows
  and no more. Say what ran and what was not verified.
