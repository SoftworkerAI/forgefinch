# Workpackage Schema v6

Schema v6 keeps every schema-v5 field and fixes the check set by slice kind,
so definition never selects checks. Each check still declares `tier`, `env`,
Boolean `required`, `status`, `notes`, records `evidence` (`executed`,
`skipped`, `seconds`, `run`) once it has run, and may name another record in
`blocked_by`.

## Tiers

- `static`: the project's single static gate, which runs every formatter,
  linter, validator, contract, SDK, and supply-chain check on the tree.
- `workspace`: the project's whole test suite in one run, covering every unit
  test and every real-substrate integration test.
- `live`: a check that exercises a running backend or a disposable stack.
- `destructive`: a verb that deletes named volumes or rotates roots.

The schema-v5 `unit` and `integration` tiers are not valid in schema v6; the
workspace suite owns both.

## Fixed Check Set

- An implementation slice names exactly the static gate (`static`, `env:
  none`) and the workspace suite (`workspace`, its documented `env`), nothing
  else. Focused single-package test runs are inner-loop tools, never recorded
  checks.
- The quality-review slice names exactly the static gate, run on the reviewed
  delta.
- The verification slice names the static gate, the workspace suite, and at
  least one `live` check, and may add only `live` and `destructive` checks
  beyond them. Those live proofs are the one check decision a package makes.
- Every check names one catalogued recipe of the project's task runner, never
  a raw build-tool command and never a chained command. A planned check may
  name a recipe its own slice will create.

## Evidence And Closure

- A required `workspace` or `live` check is `done` only with at least one
  executed test recorded in its evidence.
- A skipped optional check names the unavailable capability in its notes
  (`Unavailable capability: ...`).
- A required check blocked on a surface another record owns names that record
  in `blocked_by`; the slice and package close once the named record is
  complete, and cycles are rejected.
- A defect found by review or verification reopens the owning implementation
  slice with `[defect-open]` and resets both closure slices, exactly as in
  schema v4.

Schema v2 through v5 records remain valid historical formats and are never
rewritten only to adopt the fixed check set. A schema-v5 check that has run
may keep naming a recipe the project has since retired.
