---
id: MEOS-014
title: Architecture Decision Record Process
status: approved
owner: Chief Architect
version: 1.0
authoritative: true
readers: [architect, reviewer, engineering-leads, ai-agents]
provides: [adr-trigger, adr-lifecycle, decision-authority]
requires: [MEOS-011]
related: [docs/adr/, MEOS/05_TASK_SPECIFICATION.md, MEOS/10_QUALITY_GATE.md]
---

# Architecture Decision Record Process

## Purpose
Make consequential technical decisions explicit, reviewable, durable, and replaceable without relying on memory or chat history.

## When an ADR Is Mandatory
Create or update an ADR when a decision:
- changes a system boundary, runtime topology, or dependency direction;
- adds a strategic framework, database, provider, protocol, queue, or model platform;
- changes a public, persisted, security-sensitive, or cross-team contract;
- introduces a difficult-to-reverse migration;
- creates an exception to an Architecture Rule;
- supersedes an approved architecture decision;
- materially affects reliability, scalability, security, privacy, cost, or operability.

Routine implementation choices within an approved architecture do not require an ADR.

## ADR States
`proposed -> accepted -> implemented -> superseded | deprecated`

- **Proposed:** alternatives and evidence are still under review.
- **Accepted:** the Chief Architect or delegated human authority approved the direction.
- **Implemented:** repository behavior and documentation reflect the decision.
- **Superseded:** a newer ADR replaces it and links back to it.
- **Deprecated:** retained for history but no longer valid for new work.

AI agents may draft and recommend ADRs. They may not mark an ADR `accepted` unless an explicitly authorized human approval is recorded.

## Required ADR Structure
```markdown
# ADR-NNN: Decision title

- Status:
- Date:
- Owners:
- Related task:
- Supersedes:
- Superseded by:

## Context
## Decision Drivers
## Considered Options
## Decision
## Consequences
## Risks and Mitigations
## Migration and Rollback
## Verification
## Approval
```

## Decision Quality Requirements
An ADR must:
- describe the problem independently of the preferred solution;
- identify at least one credible alternative unless only one option is legally or technically possible;
- make trade-offs and irreversible effects explicit;
- distinguish facts, assumptions, and forecasts;
- define how the decision will be verified after implementation;
- identify migration, compatibility, and rollback requirements where applicable.

## Review and Approval
1. The task owner links the proposed ADR from the Task Specification.
2. Required reviewers assess architecture, product, security, data, and operational impact as applicable.
3. The Chief Architect or delegated human authority records acceptance or rejection.
4. Implementation may begin only after acceptance when the decision is blocking.
5. The implementer updates the ADR to `implemented` only after evidence is available.

## Conflict Resolution
When code, documentation, and an accepted ADR conflict:
1. Stop the affected work.
2. Treat the accepted ADR as authoritative unless a newer approved source supersedes it.
3. Correct the implementation or propose a superseding ADR.
4. Record the resolution; do not silently reinterpret the decision.

## Exceptions
Emergency mitigation may temporarily precede an ADR only to limit active production harm. The exception must be documented immediately, reviewed by a human owner, and followed by an ADR or rollback before normal development resumes.