---
name: workpackage-definition
description: Turn a planned workpackage into a development-ready package by reconciling architecture, contracts, security, the criteria of its four slices, and the live proofs delivery needs.
---

# Workpackage Definition

Definition happens after planning and before the testing slice begins.

1. Read the workpackage YAML/spec, repository instructions, relevant product
   skills, implementation, tests, and current contracts.
2. Reconcile the goal and scope with actual architecture and identify product
   boundaries, data/contracts, policy/security, failure modes, observability,
   and verification surfaces.
3. Write every promise as a criterion in the slice that realizes it: what the
   tests must assert in `testing`, what the code must do in `implementation`,
   what the docs and contracts must say in `documentation`. Every criterion
   starts with an empty `proof`.
4. Refine summaries, open questions, and non-goals. Do not hide a blocking
   decision in narrative notes. Do not add checks to a producing slice; each
   carries only its compile entry. The only check decision is which live and
   destructive recipes the delivery slice names to prove the goal.
5. Confirm the delivery slice names the project's static gate, its workspace
   suite, and those live proofs, with an empty `review`.
6. When the repository keeps a product backlog, as defined by its process
   docs, add each wanted product behavior that definition defers or moves to
   the non-goals as a backlog item with this package as origin, or link it to
   the item that covers it. Never put backlog IDs in product code.
7. Run the repository workpackage validator.

Do not implement product behavior during definition. Mark the package blocked
when an unresolved decision prevents a safe testing slice.
