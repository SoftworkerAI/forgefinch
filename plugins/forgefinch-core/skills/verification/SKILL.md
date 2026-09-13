---
name: verification
description: Run the delivery slice of a schema-v6 workpackage, the findings-first review, every tier of test, and the proof of every criterion, and record it honestly.
---

# Delivery Verification

Use the delivery slice, every criterion in the three producing slices, the
workpackage spec, repository commands, and applicable product skills.

- Start only after the testing, implementation, and documentation slices are
  `done`, which means each compiled with no open question. Delivery is the
  package's pull request; the main branch receives the package only when
  delivery is `done`.
- Record the findings-first review of the complete delta in the delivery
  slice's `review` before running any check. A material finding marks
  `[defect-open]`, reopens the producing slice that owns the criterion, and
  returns delivery to `todo`.
- Run the static gate, the unit tier, the integration tier, and the live and destructive
  proofs the slice names. Record exact commands and results with executed
  counts, skipped counts, seconds, and a run reference. Required unavailable
  checks are blocked; optional checks may be skipped only with the unavailable
  capability named.
- Close each criterion with a `proof` naming the delivery check that
  established it or the executed test or run that check produced. A criterion
  a check did not establish stays `todo`, and a failing proof is a defect.
- Mark delivery `done` only when the review is recorded, every check is
  resolved with evidence, and every criterion in every slice is `done` with
  proof.

Never report an unexecuted check as passed, and never close a criterion
without naming what proved it.
