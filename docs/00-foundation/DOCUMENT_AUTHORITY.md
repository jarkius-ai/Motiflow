# Document Authority Standard

**Status:** Accepted foundation standard (accepted by Jarkius, 2026-07-26)
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

## What belongs in MEOS/ versus docs/

This is the normative placement rule. Two concerns live in this repository and
they must not blur:

- **`MEOS/` — how we build.** The engineering operating system: constitutions,
  standards, quality gates, review and readiness rules, role registry, ADR
  process, bootstrap/continuation procedure, and task specifications
  (`MEOS/tasks/`). MEOS documents govern how work is specified, reviewed,
  verified, and released. They never define product behavior.
- **`docs/` — the product we build.** Product intent, personas, journeys,
  validation evidence, architecture contracts, ADR decisions, AI evaluation,
  and design material. `docs/` documents define what Motiflow is and how it
  behaves. They never redefine engineering process.

Declared exceptions, with rationale:

- `docs/03-delivery/` holds delivery *planning* artifacts (roadmaps, readiness
  reviews, traceability, release plans). They sequence product work, so they
  read as product-adjacent, but they are controlled by MEOS standards
  (Definition of Ready, Quality Gate). They stay in `docs/` because they are
  audience-facing plans about the product's delivery, while their control
  rules remain in `MEOS/`. Task specifications remain in `MEOS/tasks/` because
  a task is a unit of governed work, not a product statement.
- `docs/05-governance/CONTRIBUTING.md` is contributor-facing guidance owned by
  MEOS maintainers; it stays in `docs/` as an entry-point convention and must
  defer to `MEOS/` standards on any conflict.

When placing a new document, ask: does it change what the product is
(`docs/`), or how work on it is governed (`MEOS/`)? If genuinely both, split
it. On conflict, this section is controlled by the authority levels above.
