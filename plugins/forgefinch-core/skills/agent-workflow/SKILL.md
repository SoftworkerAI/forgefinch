---
name: agent-workflow
description: Coordinate multi-step development, reviews, dependency changes, skill maintenance, and completion reporting in software repositories. Use with the applicable product plugin; do not use as a substitute for product architecture guidance.
---

# Development Workflow

Repository instructions own architecture, tooling, security, and completion
commands. This skill only describes the order of work around them.

## Workflow

1. Read the repository `AGENTS.md` first and select the smallest applicable
   set of product skills.
2. Inspect the current repository state, the relevant implementation, and its
   tests before changing files.
3. For broad work, meaning work that spans sessions or people, read the
   workpackage spec if one exists, or write one with `$spec-writing` before
   implementing. A small single-session change needs only a plan in the
   current task.
4. Do the work within the repository's boundaries. When the plan changes,
   update the spec in place.
5. Build and check with the repository's own commands, and follow its rules
   about how often to build and which checks to run when.
6. Report what changed, what was run and its result, and what was not
   verified, with the reason.

## Invariants

- Do not claim a check passed unless it was executed and passed.
- A check that could not run is reported as not run, never as passed or
  silently dropped.
- Do not copy build or check commands from another project; use the ones this
  repository defines.
