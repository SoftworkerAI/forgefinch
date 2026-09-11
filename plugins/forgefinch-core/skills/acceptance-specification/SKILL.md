---
name: acceptance-specification
description: Write or review testable acceptance criteria, negative cases, done conditions, and check mappings for a selected workpackage slice.
---

# Acceptance Specification

Use the active workpackage YAML, its spec, applicable product skills, and nearby
implementation and tests.

## Rules

- Prefix each criterion ID with its slice ID, such as `WP-0001-S1-AC1`.
- State observable behavior, evidence, and important negative cases rather than
  implementation activities.
- Write each criterion in the producing slice that realizes it, testing,
  implementation, or documentation, with an empty `proof`; delivery fills the
  proof in.
- Cover relevant contracts, security, privacy, accessibility, persistence,
  failure behavior, and architecture boundaries identified by product guidance.
- The delivery slice carries no criteria of its own; its review and its live
  proofs are what close the criteria above.

Done means criteria are concrete, testable, correctly prefixed, placed in the
slice that realizes them, and closable by a delivery check.
