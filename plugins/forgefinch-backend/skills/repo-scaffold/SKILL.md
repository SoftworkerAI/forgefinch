---
name: repo-scaffold
description: Use for workspace layout, Cargo members, repo directories, and modular-monolith structure.
---

# repo-scaffold

## Purpose

Support workspace layout, Cargo members, repo directories, and modular-monolith structure.

## Use This Skill When

- The current work touches workspace layout, Cargo members, repo directories, and modular-monolith structure.
- A local check, review, or design choice needs this specialty.

## Workflow

1. Read `AGENTS.md`, the relevant architecture docs, and nearby code, including existing boundaries, contracts, tests, and local service config.
2. If a spec exists for this work, read it.
3. For public API work, preserve the client-stack boundary:
   `apps/public CLI -> crates/interfaces/API client ->
   path/to/api-contracts`.
4. Runtime calls still go to the backend server public REST/SSE only.
5. Do the work within the repository's boundaries.
6. Run the repository's checks that apply and report what ran.

## Required Output

- Affected files, crates, services, schemas, policies, prompts, or docs.
- Repo layout and dependency-direction impact for `api-contracts`,
  the API client, TypeScript SDK, and the public CLI when the work changes
  public API behavior.
- Local checks run, skipped with reason, or still needed.
- Open questions.

## Guardrails

- Keep application semantics inside application-owned code and schemas.
- Keep external services behind ports, adapters, typed config, and local checks.
- Keep security, identity, data ownership, and audit boundaries explicit when they are relevant.
- Do not let the public CLI depend on the backend server internals, domain crates,
  database crates, or adapter crates.
- Do not let the API client own domain behavior, persistence, policy
  decisions, audit storage, evidence storage, or projection state.
- Do not add later-environment planning unless the user asks for it.

## Done Means

- The behavior is present or the review finding is explicit.
- Required local checks are named and results are recorded.
- Architecture docs are updated when architecture truth changes.
- The report shows what changed and what remains.
