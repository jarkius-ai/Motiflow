# Document Authority Standard

**Status:** Proposed foundation standard
**Applies to:** All Motiflow contributors, AI agents, specifications, architecture decisions, implementation tasks, and review evidence.

## Purpose

This standard establishes one authoritative read order and one conflict-resolution model for the repository.

## Canonical read order

1. `START_HERE.md`
2. `PROJECT_CHARTER.md`
3. `MASTER_CONTEXT.md`
4. `CONTEXT_INDEX.yaml`
5. `MEOS/20_PROJECT_BOOTSTRAP.md`
6. Applicable product, architecture, AI, design, engineering, and operational documents
7. Accepted ADRs
8. Current task specification and acceptance criteria
9. Current implementation, tests, and verification evidence

`START_HERE.md` is the navigation entry point. It is not a higher-authority policy document than the Project Charter or Master Context.

The numeric prefixes in `MEOS/` identify governance topics and do not define
the onboarding step number. `MEOS/20_PROJECT_BOOTSTRAP.md` is the designated
MEOS bootstrap entry point; task routing determines which other MEOS documents
are required.

## Authority levels

### Level 1 — Project direction

- `PROJECT_CHARTER.md`
- `MASTER_CONTEXT.md`

These define product identity, mission, strategic boundaries, architecture identity, and foundational principles.

### Level 2 — Accepted decisions and controlling standards

- accepted ADRs
- MEOS constitutions and standards
- canonical terminology, repository structure, contracts, and schema standards

### Level 3 — Domain specifications

- product requirements
- system design
- data and API contracts
- AI engine specifications
- UX and design specifications
- security and operational specifications

### Level 4 — Delivery artifacts

- task specifications
- implementation plans
- source code
- tests
- review reports
- release evidence

## Conflict resolution

When two sources conflict:

1. Prefer the higher authority level.
2. At the same authority level, prefer an accepted document over a draft.
3. At the same status, prefer the newer explicitly versioned document only when it states what it supersedes.
4. An accepted ADR may change architecture or terminology only within its stated scope.
5. Never resolve a material conflict silently. Record the conflict and required decision.

## Supersession rule

A document that changes an established decision must include:

- the superseded document or section
- the replacement decision
- effective date or version
- compatibility and migration impact
- related ADR when architecture-significant

## Documentation rule

Documents must reference canonical concepts rather than redefine them. Product identity belongs in the Project Charter and Master Context. Engineering process belongs in MEOS. Domain details belong in their corresponding `docs/` area.
