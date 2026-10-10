---
name: ci-quality
description: Use for CI checks, local quality commands, dependency checks, and service config validation.
---

# ci-quality

## Purpose

Support CI checks, local quality commands, dependency checks, and service config validation.

## Use This Skill When

- The current work touches CI checks, local quality commands, dependency checks, and service config validation.
- A local check, review, or design choice needs this specialty.

## Workflow

1. Read `AGENTS.md`, the relevant architecture docs, and nearby code, including existing boundaries, contracts, tests, and local service config.
2. If a spec exists for this work, read it.
3. Do the work within the repository's boundaries.
4. Run the repository's checks that apply and report what ran.
5. For JavaScript or TypeScript quality checks, pin exact dependency versions,
   commit the lockfile, avoid browser downloads unless the work explicitly
   needs UI coverage, and expose repeatable commands through `Justfile` or the
   package scripts.

## Required Output

- Affected files, crates, services, schemas, policies, prompts, or docs.
- Local checks run, skipped with reason, or still needed.
- Open questions.

## Guardrails

- Keep application semantics inside application-owned code and schemas.
- Keep external services behind ports, adapters, typed config, and local checks.
- Keep security, identity, data ownership, and audit boundaries explicit when they are relevant.
- Do not add later-environment planning unless the user asks for it.
- Do not add unpinned Node dependencies, floating package ranges, or Playwright
  browser installs for APIRequest-only checks.

## Done Means

- The behavior is present or the review finding is explicit.
- Required local checks are named and results are recorded.
- Architecture docs are updated when architecture truth changes.
- The report shows what changed and what remains.
