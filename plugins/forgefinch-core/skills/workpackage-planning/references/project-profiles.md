# Project Command Profiles

Select commands from the repository being changed. Read `AGENTS.md`, the root
task runner, package scripts, and CI configuration; never copy a command from
an unrelated example.

Every project profile names three fixed recipes plus its live proofs:

- Static gate: the one recipe that runs every formatter, linter, validator,
  contract, SDK, and supply-chain check. It is the `static` check of every
  slice and the quality-review slice's only check.
- Workspace suite: the one recipe that runs the whole test suite, unit and
  real-substrate integration together. It is the `workspace` check of every
  implementation and verification slice.
- Live proofs: the recipes that exercise a running backend or a disposable
  stack. The verification slice names the ones that prove the package goal.
- Workpackage validation: the repository-owned schema check, which the static
  gate includes.

Example: the Softworker platform names `just check`, `just test`, and live
recipes such as `just test-http-api-playwright` and `just dev-smoke`, with
`just verify` as the human shortcut for the first two plus the disposable HTTP
journey. Examples are not defaults. If a project has no single static gate or
no single workspace suite, creating them is the first slice of the first
package that needs them; do not substitute a hand-picked list.
