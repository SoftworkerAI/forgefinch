---
name: testcontainers
description: Use for Rust integration tests with Testcontainers and service wait strategies.
---

# testcontainers

## Purpose

Support Rust integration tests with Testcontainers and service wait strategies.

## Use This Skill When

- The current work touches Rust integration tests with Testcontainers and service wait strategies.
- A local check, review, or design choice needs this specialty.

## Workflow

1. Read `AGENTS.md`, the relevant architecture docs, and nearby code, including existing boundaries, contracts, tests, and local service config.
2. If a spec exists for this work, read it.
3. For REST API integration tests, use Testcontainers when behavior needs real
   Postgres or service substrates and prefer explicit wait strategies over
   sleeps.
4. Keep public API assertions on the backend server flowing through
   the API client or the public CLI even when dependencies are containerized.
5. Do the work within the repository's boundaries.
6. Run the repository's checks that apply and report what ran.

## Required Output

- Affected files, crates, services, schemas, policies, prompts, or docs.
- Containerized dependency and wait-strategy choices for REST API checks.
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
