# Workpackage Schema v6

Schema v6 keeps every schema-v5 field and fixes the slice shape: every package
has exactly four slices, and only the last one runs anything.

## Slices

1. `testing`: the tests that state each criterion as an executable assertion.
2. `implementation`: the code that satisfies them.
3. `documentation`: the docs, contracts, and runbooks that describe them.
4. `delivery`: the findings-first review, every tier of test, and the proof of
   every criterion.

The three producing slices carry the acceptance criteria and a `compile`
entry (`cmd`, `status`, `notes`) naming the project's compile recipe: the Rust
compile for testing and implementation, the docs compile for documentation.
They never carry `checks`. A producing slice is `done` when its compile is
`done` and it has no open question; its criteria stay `todo`, because done
means built, never proven.

The delivery slice carries `checks` and `review` and no criteria of its own.
Its checks are the project's static gate, its unit tier (every test needing no
substrate, with no running environment), its integration tier (every
real-substrate test against the one running local environment), and at least
one `live` check, with only `live` and `destructive` checks beyond them. `review` holds the
findings-first review of the complete delta and is recorded before any check
is `done`. Delivery starts only after all three producing slices are `done`.

## Criteria And Proof

Every criterion carries `proof`, empty until delivery closes it. A criterion
is `done` only while delivery is under way, only after its slice compiled, and
only with a non-empty proof naming a delivery check that is itself `done` or
the executed test or run that check produced. Delivery is `done` when the
review is recorded, every check is resolved with evidence, and every criterion
in every slice is `done` with proof.

## Evidence And Closure

- A required `integration` or `live` check is `done` only with at least one
  executed test recorded in its evidence.
- A skipped optional check names the unavailable capability in its notes
  (`Unavailable capability: ...`).
- A required check blocked on a surface another record owns names that record
  in `blocked_by`; the slice and package close once the named record is
  complete, and cycles are rejected.
- A defect found by delivery marks `[defect-open]`, reopens the producing slice
  that owns the criterion, and returns delivery to `todo`.
- Every check names one catalogued recipe of the project's task runner, never
  a raw build-tool command and never a chained command; focused single-package
  test runs are inner-loop tools while implementing, not recorded checks.

Schema v2 through v5 records, and earlier schema-v6 records with
implementation, quality-review, and verification slices, remain valid
historical formats and are never rewritten only to adopt this shape.
