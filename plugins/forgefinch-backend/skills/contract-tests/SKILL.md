---
name: contract-tests
description: Use for integration and contract tests for external services and adapters.
---

# contract-tests

## Purpose

Support integration and contract tests for external services and adapters.

## Use This Skill When

- The current work touches integration and contract tests for external services and adapters.
- A local check, review, or design choice needs this specialty.

## Workflow

1. Read `AGENTS.md`, the relevant architecture docs, and nearby code, including existing boundaries, contracts, tests, and local service config.
2. If a spec exists for this work, read it.
3. For REST API work that touches external services or adapters, use
   Testcontainers or Compose for real local substrates where practical.
4. Public HTTP product scenarios must be proven through Playwright only; keep
   SDK and CLI checks at their unit/request and command-output layers.
5. Do the work within the repository's boundaries.
6. Run the repository's checks that apply and report what ran.

## Required Output

- Affected files, crates, services, schemas, policies, prompts, or docs.
- External service test boundary: real substrate, outbound mock, or readiness
  check, with skipped layers and reasons.
- Local checks run, skipped with reason, or still needed.
- Open questions.

## Guardrails

- Keep application semantics inside application-owned code and schemas.
- Keep external services behind ports, adapters, typed config, and local checks.
- Keep security, identity, data ownership, and audit boundaries explicit when they are relevant.
- Do not add later-environment planning unless the user asks for it.

## Done Means

- The behavior is present or the review finding is explicit.
- Required local checks are named and results are recorded.
- Architecture docs are updated when architecture truth changes.
- The report shows what changed and what remains.
