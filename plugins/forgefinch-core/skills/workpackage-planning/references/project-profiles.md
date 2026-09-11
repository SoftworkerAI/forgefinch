# Project Command Profiles

Select commands from the repository being changed. Read `AGENTS.md`, the root
task runner, package scripts, and CI configuration; never copy a command from
an unrelated example.

Every project profile names these recipes:

- Compile: the recipes that build an artifact without executing anything. The
  testing and implementation slices record the code compile; the documentation
  slice records the docs compile.
- Static gate: the one recipe that runs every formatter, linter, validator,
  contract, SDK, and supply-chain check. Delivery's first check.
- Workspace suite: the one recipe that runs the whole test suite, unit and
  real-substrate integration together. Delivery's second check.
- Live proofs: the recipes that exercise a running backend or a disposable
  stack. Delivery names the ones that prove the package goal.
- Workpackage validation: the repository-owned schema check, which the static
  gate includes.

Example: the Softworker platform names `just compile` and `just compile-docs`
for the producing slices, `just check` and `just test` for delivery, and live
recipes such as `just test-http-api-playwright` and `just dev-smoke`. Examples
are not defaults. If a project has no single static gate or no single
workspace suite, creating them is the first package that needs them; do not
substitute a hand-picked list.
