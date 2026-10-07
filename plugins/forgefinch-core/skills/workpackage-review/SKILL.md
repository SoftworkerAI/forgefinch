---
name: workpackage-review
description: Review workpackage YAML/spec completeness, slice state, acceptance criteria and their proofs, the delivery review, evidence, boundaries, and completion claims.
---

# Workpackage Review

Report findings first, ordered by severity and supported with file references.

Check that:

- The filename, workpackage ID, `spec_ref`, goal, scope, slice IDs, and
  acceptance IDs are consistent.
- The spec describes the same target and strategy without carrying execution
  status.
- Schema-v6 packages have exactly four slices, testing, implementation,
  documentation, and delivery; the producing slices carry criteria and a
  compile entry and no checks, and delivery carries the static gate, the
  unit and integration tiers, the live proofs, and the review.
- No criterion is `done` without a proof naming a done delivery check, and no
  producing slice is `done` without a done compile.
- Started closure slices satisfy their prerequisites.
- Done slices have resolved acceptance, required checks, optional checks,
  questions, and findings.
- Product architecture, security, privacy, accessibility, contract, and test
  boundaries are covered where applicable.
- No open `[defect-open]` marker is hidden by a completion claim.
- When the repository keeps a product backlog, the backlog items the package
  claims are listed and carry the package as their delivering workpackage,
  deferred product scope is recorded as backlog items, and a complete package
  has closed its items.

Do not call a package complete when required evidence is missing or a product
boundary has not been proven.
