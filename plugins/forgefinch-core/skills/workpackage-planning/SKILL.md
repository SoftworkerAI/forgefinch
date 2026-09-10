---
name: workpackage-planning
description: Plan durable schema-v6 workpackage YAML records and colocated specs with implementation, mandatory quality-review, and final verification slices whose checks are fixed by slice kind. Retain historical schema-v2 through v5 records without rewriting them.
---

# Workpackage Planning

Read the repository `AGENTS.md`, process documentation, nearby implementation,
tests, and the applicable command profile before planning.

## Workflow

1. Define a one-sentence goal in this form: `<objective end state>, verified by
   <evidence/checks/artifacts>, while preserving <constraints/boundaries>.`
2. Put compact execution state in YAML and feature/architecture context in a
   colocated `.spec.md` file.
3. Create one or more `implementation` slices, exactly one penultimate
   `quality_review` slice, and exactly one final `verification` slice.
4. Prefix slice IDs with the workpackage ID and acceptance IDs with the slice
   ID. Give every slice acceptance criteria, questions, notes, and completion
   fields.
5. Copy the fixed check set for each slice kind from the project profile; do
   not select checks per slice. An implementation slice names the project's
   static gate and its workspace suite, the quality-review slice names the
   static gate, and the verification slice names both plus the live and
   destructive proofs the goal needs. Mark every check `required: true` or
   `required: false`. Read [project profiles](references/project-profiles.md)
   for the supported project commands.
6. Spend planning effort on the goal, scope, acceptance criteria, and the
   verification slice's live proofs; the only check decision a package makes
   is which live and destructive recipes prove its goal.
7. Run the repository's workpackage validator.

The complete schema and state invariants are in
[schema v6](references/schema-v6.md), which extends
[schema v5](references/schema-v5.md) by fixing the check set per slice kind.
Reusable files live in `assets/`; start from `workpackage-v6.yaml`.

Place checks by tier, never by duration: live and destructive checks belong
only to the final verification slice, and no justification moves one earlier.

Historical schema-v2 through schema-v5 records remain valid and are not
upgraded merely for consistency. New durable records use schema v6.
