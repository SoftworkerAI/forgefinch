---
name: slice-execution
description: Build one selected producing slice of a schema-v6 workpackage, testing, implementation, or documentation, against its criteria and project boundaries, recording only that it compiles.
---

# Slice Execution

1. Read the active YAML/spec, repository instructions, applicable product
   skills, and nearby source/tests.
2. Confirm the selected slice is the next one in order (testing, then
   implementation, then documentation) and has criteria.
3. Build the artifact the criteria describe inside the correct boundary: the
   tests that state each criterion, the code that satisfies them, or the
   documentation and contracts that explain them. Use inner-loop narrowing (a
   single-package test, a single-crate check) freely while editing; none of it
   is recorded.
4. Run the slice's `compile` recipe once and record its result in the slice's
   compile entry. Do not run the test suite; correctness is proven in
   delivery.
5. Mark the slice `done` only when the compile passed and no question is open.
   Leave every criterion `todo` with its proof empty.
6. Record changed files, the compile result, and open questions in YAML. Do not
   put status evidence in the descriptive spec.

Delivery belongs to `$verification`. If delivery later reopens this slice
with `[defect-open]`, fix the owning artifact and record the new compile.
