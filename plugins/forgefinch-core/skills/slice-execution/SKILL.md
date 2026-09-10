---
name: slice-execution
description: Implement or review one selected schema-v6 workpackage slice against its acceptance criteria, project boundaries, and its fixed checks.
---

# Slice Execution

1. Read the active YAML/spec, repository instructions, applicable product
   skills, and nearby source/tests.
2. Confirm the selected slice exists, is decision-ready, and has acceptance
   criteria and its fixed checks.
3. Use inner-loop narrowing while editing (a single-package test, a single
   crate check), then run the slice's recorded checks once: the static gate
   and the workspace suite for an implementation slice.
4. For `quality_review`, confirm all implementation slices are resolved. Review
   the complete delta independently with findings first, then run the static
   gate.
5. For `verification`, confirm implementation and quality review are resolved
   before proving the complete goal with the static gate, the workspace suite,
   and the named live proofs.
6. Implement or review only the selected slice and record honest results and
   completion evidence in YAML.

If review or verification exposes a behavior defect, add `[defect-open]`,
reopen the owning implementation slice, and reset both closure slices to
`todo`. Do not put status evidence in the descriptive spec.
