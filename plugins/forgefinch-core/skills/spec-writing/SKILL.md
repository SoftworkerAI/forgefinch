---
name: spec-writing
description: "Write or update a free-form workpackage spec: one Markdown file that says what will be built and how it will be checked."
---

# Spec Writing

A workpackage is one free-form Markdown spec. It exists so that work spanning
several sessions or several people has one place that says what is being built
and how it will be checked.

## When to write one

Write a spec when the work will not fit in one session, will be picked up by
someone else, or needs decisions agreed before code is written. A small change
that one session can finish does not need a spec; a plan in the task is enough.

## Where it lives

- One file per workpackage in the consuming repository:
  `docs/workpackages/WP-NNNN-short-title.spec.md`.
- `NNNN` is the next unused four-digit number in that directory. The title is
  a few lowercase, hyphenated words.
- If the repository's `AGENTS.md` names a different location or naming rule,
  follow the repository.

## What goes in it

The spec is free-form. No heading is required and no section has a fixed
shape. Include whatever helps the next reader, usually some of:

- What will be built and why.
- The current state, with references to the files that matter.
- Decisions taken and the reasons for them.
- The work, in the order it will be done.
- How the result will be verified.
- Risks, non-goals, and open questions.

## Keeping it useful

- Keep one current version. Edit the text in place when the plan changes; do
  not add history, changelog, or dated amendment sections.
- Reference existing architecture docs, contracts, and code instead of
  restating them.
- There is no YAML record, no slice list, and no status record. The spec file
  is the whole workpackage; progress lives in the code and its commits.
