# Shared Forgefinch Development Workflow

Install `forgefinch-core` and the optional plugin appropriate for this
repository. Plugin installation does not merge this template into a project's
`AGENTS.md`; repository owners must adopt and tailor it explicitly.

## How We Plan Work

- Work that spans sessions or people gets a workpackage: one free-form
  Markdown spec at `docs/workpackages/WP-NNNN-short-title.spec.md` that says
  what will be built and how it will be checked.
- The spec has no required headings and no separate record. Keep one current
  version and edit it in place when the plan changes.
- Small single-session changes do not need a spec.
- Use this repository's own build and check commands; do not copy commands
  from another project.
- Do not claim a check passed unless it ran and passed. Report what changed,
  what was run, and what was not verified.

Keep product architecture, security, testing, and completion-report rules in
the owning repository's `AGENTS.md`.
