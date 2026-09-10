---
name: verification
description: Run and record slice or complete-goal verification for workpackage slices, including failures, blocked checks, skipped checks, changed files, and residual risk.
---

# Development Verification

Use the selected slice, acceptance criteria, workpackage spec, repository
commands, and applicable product skills to select evidence.

- Run the fixed checks of an implementation slice: the static gate and the
  workspace suite.
- For quality review, report findings before summaries and run the static
  gate on the reviewed delta.
- Start final verification only after implementation and quality review are
  done. Run the static gate and the workspace suite again on the reviewed
  delta, then the live and destructive proofs the slice names, covering the
  complete goal, named constraints, integrations, negative paths, and
  persistence/restart when relevant.
- Record exact commands and results with executed counts, skipped counts,
  seconds, and a run reference. Required unavailable checks are blocked;
  optional checks may be skipped only with the unavailable capability named.
- A behavior defect reopens implementation with `[defect-open]` and resets
  closure slices.

Do not substitute a broad end-to-end check for the workspace suite, and never
report an unexecuted check as passed.
