---
id: MEOS-011
title: Architecture Rules
status: approved
owner: Chief Architect
version: 1.0
authoritative: true
readers: [all-contributors]
provides: [architecture-boundaries, dependency-rules, change-classification]
requires: [MEOS-001, MEOS-002, MEOS-005]
related: [MEOS/14_ADR_PROCESS.md, MEOS/10_QUALITY_GATE.md, docs/02-architecture/]
---

# Architecture Rules

## Purpose
Protect Motiflow from accidental coupling, undocumented structural change, and locally convenient decisions that weaken the system.

## Non-Negotiable Rules
1. Business behavior must be expressed through explicit domain or application contracts, not hidden framework behavior.
2. Dependencies must point inward toward stable business abstractions. Domain logic must not depend on delivery, storage, vendor, or UI details.
3. UI, API, workflow, data, event, prompt, and artifact boundaries must have explicit contracts when consumed by more than one component or role.
4. Cross-layer access that bypasses an approved interface is prohibited.
5. Shared logic must have one authoritative implementation; copy-and-diverge duplication is prohibited.
6. External services, model providers, storage engines, and frameworks must be isolated behind replaceable adapters where practical.
7. State transitions, retries, timeouts, failure behavior, and idempotency must be explicit for asynchronous or distributed work.
8. Security and privacy boundaries must be designed before implementation for sensitive data or privileged operations.
9. Backward compatibility, migration, and rollback must be considered before changing a public or persisted contract.
10. Architecture must remain understandable from repository artifacts; undocumented architecture is not approved architecture.

## Layer Boundaries
- Product requirements define outcomes and acceptance criteria.
- Domain and application layers define business meaning and orchestration.
- Interfaces define contracts between components.
- Infrastructure implements interfaces and may not redefine business rules.
- Delivery layers translate external requests and responses without owning domain behavior.
- Tests verify contracts and behavior at the appropriate boundary.

## Changes Requiring Architecture Review
Architecture review is mandatory when a task:
- adds or removes a subsystem, service, engine, or persistent store;
- changes a public API, event, schema, workflow, prompt, or artifact contract;
- introduces a new cross-cutting dependency;
- changes trust boundaries, authentication, authorization, privacy, or secrets handling;
- changes deployment topology or runtime responsibility;
- creates a migration that is difficult to reverse;
- intentionally violates or replaces an existing architecture decision.

## Prohibited Shortcuts
- Direct database access from presentation code.
- Business rules embedded only in prompts, controllers, components, migrations, or deployment scripts.
- Silent schema or contract changes.
- Provider-specific objects escaping their adapter boundary.
- Global mutable state without explicit ownership and lifecycle.
- Catch-and-ignore error handling.
- Unbounded retries or background work without idempotency controls.
- Architecture approval inferred from code merge alone.

## Required Evidence
Architecture-sensitive tasks must provide:
- affected boundaries and contracts;
- dependency-direction assessment;
- failure and recovery behavior;
- security and data-impact assessment;
- compatibility and migration plan;
- ADR reference when required;
- tests that verify the changed boundary.

## Enforcement
A reviewer must return `BLOCKED` when required architecture evidence or approval is missing. A known violation cannot be accepted through a quality score or implementation success alone.