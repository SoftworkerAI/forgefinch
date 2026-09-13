---
name: workpackage-planning
description: Plan durable schema-v6 workpackage YAML records and colocated specs with exactly four slices, testing, implementation, documentation, and delivery, where only delivery runs anything. Retain historical records without rewriting them.
---

# Workpackage Planning

Read the repository `AGENTS.md`, process documentation, nearby implementation,
tests, and the applicable command profile before planning.

## Workflow

1. Define a one-sentence goal in this form: `<objective end state>, verified by
   <evidence/checks/artifacts>, while preserving <constraints/boundaries>.`
2. Put compact execution state in YAML and feature/architecture context in a
   colocated `.spec.md` file.
3. Create exactly four slices in this order: `testing`, `implementation`,
   `documentation`, and `delivery`.
4. Prefix slice IDs with the workpackage ID and acceptance IDs with the slice
   ID. Write the acceptance criteria in the three producing slices, each
   criterion beside the artifact that realizes it and each with an empty
   `proof`; give every slice questions, notes, and completion fields.
5. Give each producing slice its `compile` entry from the project profile
   (the Rust compile for testing and implementation, the docs compile for
   documentation) and nothing else; producing slices never carry checks.
6. Give the delivery slice the project's static gate, its unit tier, its integration tier, and
   the live and destructive proofs the goal needs, plus an empty `review`.
   That live-proof list is the only check decision a package makes. Read
   [project profiles](references/project-profiles.md) for the supported
   project commands.
7. Run the repository's workpackage validator.

The complete schema and state invariants are in
[schema v6](references/schema-v6.md). Reusable files live in `assets/`; start
from `workpackage-v6.yaml`.

Nothing runs before delivery: a producing slice is done when its artifact
compiles, and a criterion is done only when delivery proved it.

Historical schema-v2 through schema-v5 records remain valid and are not
upgraded merely for consistency. New durable records use schema v6.
