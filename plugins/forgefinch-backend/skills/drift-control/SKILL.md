---
name: drift-control
description: Use for alignment between service matrix, routing, runbooks, infra, and skills.
---

# drift-control

## Purpose

Support alignment between service matrix, routing, runbooks, infra, and skills.

## Use This Skill When

- The current work touches alignment between service matrix, routing, runbooks, infra, and skills.
- A local check, review, or design choice needs this specialty.

## Workflow

1. Read `AGENTS.md`, the relevant architecture docs, and nearby code, including existing boundaries, contracts, tests, and local service config.
2. If a spec exists for this work, read it.
3. When a lightweight environment is in scope, compare its application binary,
   router, middleware, identity verification semantics, policy path, schema,
   migrations, seed command, repositories, query services, DTOs, and safe
   errors with the production-shaped local environment.
4. Keep a checked allowlist of differences limited to composition-root external
   adapters or protocol-compatible mock services, and run the same product
   conformance scenarios in both environments.
5. Do the work within the repository's boundaries.
6. Run the repository's checks that apply and report what ran.

## Required Output

- Affected files, crates, services, schemas, policies, prompts, or docs.
- Local checks run, skipped with reason, or still needed.
- Open questions.

## Guardrails

- Keep application semantics inside application-owned code and schemas.
- Keep external services behind ports, adapters, typed config, and local checks.
- Keep security, identity, data ownership, and audit boundaries explicit when they are relevant.
- Treat optional integration packs as extensions of one backend. Do not allow
  route, domain, query, projection, DTO, schema, seed, policy, identity, or
  safe-error forks.
- Do not allow environment-name or mock-mode branches, fixture personas,
  placeholder projections, or deterministic mock values in production product
  modules. Mock values enter through seeds, test fixtures, or external adapter
  protocols.
- Do not let an omitted capability fabricate successful product state; require
  the normal explicit unavailable posture.
- Do not add later-environment planning unless the user asks for it.

## Done Means

- The behavior is present or the review finding is explicit.
- Required local checks are named and results are recorded.
- Architecture docs are updated when architecture truth changes.
- The report shows what changed and what remains.
