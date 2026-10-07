---
name: agent-workflow
description: Coordinate multi-step development, reviews, dependency changes, skill maintenance, and completion reporting in software repositories. Use with the applicable product plugin; do not use as a substitute for product architecture guidance.
---

# Development Workflow

Read the repository `AGENTS.md` first and select the smallest applicable set of
product skills. Repository instructions own architecture, tooling, security,
and completion commands; this skill owns the shared delivery sequence.

## Workflow

1. Inspect the current repository state, instructions, relevant implementation,
   and tests before changing files.
2. For broad work, create or select a schema-v6 workpackage and run definition
   before implementation. A small single-session change may keep an equivalent
   plan in the current task when repository rules allow it.
3. Build the testing, implementation, and documentation slices in order,
   recording only that each compiles; nothing runs before delivery.
4. Perform delivery only after all three are done: record the findings-first
   review, run the static gate, the unit tier, the integration tier, and the live proofs, and
   close every criterion with its proof.
5. A defect found in delivery reopens the producing slice that owns the
   criterion and returns delivery to `todo`.
6. Report changed files, checks actually run, skipped or blocked checks with
   reasons, manual verification, and residual risk.

Use `$workpackage-planning`,
`$workpackage-definition`,
`$slice-execution`, `$workpackage-review`, and
`$verification` for their owning stages.

## Invariants

- Required checks are blocked rather than skipped when unavailable.
- A package lives on one branch: producing slices are commits on it, delivery
  is the pull request, and the main branch receives the package only when
  delivery is done. Never push a producing slice to the main branch.
- Do not start delivery before the testing, implementation, and documentation
  slices are done.
- A behavior defect uses `[defect-open]`, reopens the producing slice that
  owns the criterion, and resets delivery to `todo` until proven again.
- When the repository keeps a product backlog, planning starts from it,
  deferred product scope is added to it, and delivery closes the items the
  package claimed; backlog IDs stay out of product code and commits.
- Do not claim a command passed unless it was executed and passed.
