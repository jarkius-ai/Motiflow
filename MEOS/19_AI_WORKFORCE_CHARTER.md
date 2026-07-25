---
id: MEOS-019
title: AI Workforce Charter
status: approved
owner: Chief Architect
version: 1.0
authoritative: true
readers: [all-contributors]
provides: [collaboration-model, handoff-rules, separation-of-duties]
requires: [MEOS-002, MEOS-003, MEOS-005, MEOS-010]
related: [MEOS/roles.yaml, CONTEXT_INDEX.yaml]
---

# AI Workforce Charter

## Purpose
Define how human and AI roles collaborate so that speed never replaces accountability, independent review, or evidence.

## Operating Model
`Product Owner -> Architect -> Implementer -> Reviewer -> QA/Security -> Release Manager -> Human Authority`

Roles may execute in parallel only when their inputs are stable and their outputs do not create circular approval. Every handoff must carry the task state, context manifest, decisions, artifacts, evidence, unresolved risks, and next owner.

## Separation of Duties
- An implementer may not approve its own work.
- An agent that authored an architecture-sensitive proposal may not be its sole reviewer.
- QA verifies acceptance criteria independently from implementation claims.
- Security-sensitive work requires a security reviewer independent of the implementer.
- Release approval requires completed evidence, not confidence statements.
- Human authority retains approval for architecture acceptance, product scope, security exceptions, irreversible migrations, and production release.

## Collaboration Rules
1. Each task has exactly one accountable human owner and one active execution owner.
2. Agents act only within the authority declared in `roles.yaml` and the Task Specification.
3. Agents must consume the minimum complete context defined by `CONTEXT_INDEX.yaml`.
4. Handoffs must be explicit; silently transferring assumptions is prohibited.
5. Reviewer findings return to the responsible implementer through `LOOP` unless blocked by missing authority, context, or decision.
6. Contract or architecture changes return to the Chief Architect.
7. Product ambiguity returns to the Product Owner.
8. Unsafe, privacy-sensitive, or compliance-sensitive uncertainty returns to the Security Reviewer and human authority.
9. Repeated loops with no measurable improvement must stop and escalate.
10. Every final claim must point to verifiable evidence.

## Standard Task States
- `PROPOSED`: outcome and scope are being defined.
- `READY`: Definition of Ready is satisfied.
- `IN_PROGRESS`: assigned role is executing.
- `REVIEW`: implementation and evidence are available.
- `LOOP`: changes are required and ownership is explicit.
- `BLOCKED`: missing context, decision, environment, or authority prevents progress.
- `ACCEPTED`: all mandatory gates passed.
- `RELEASED`: approved artifact reached its intended environment.

## Handoff Contract
Each handoff must include:
```yaml
task_id:
from_role:
to_role:
state:
context_manifest:
decisions:
artifacts:
acceptance_evidence:
tests_and_results:
quality_gate_status:
unresolved_risks:
requested_action:
```

A receiver must reject an incomplete handoff rather than reconstructing missing facts through guesswork.

## Human Authority
Human approval is mandatory for:
- accepting or superseding an ADR;
- changing product scope or acceptance criteria after execution begins;
- security, privacy, or compliance exceptions;
- destructive or irreversible migration;
- production deployment or release authorization;
- waiving a mandatory quality gate.

A waiver must identify the owner, reason, expiry, risk, and remediation task. A quality score cannot conceal a waived mandatory gate.

## Success Standard
The workforce is effective when a new qualified agent can enter through the bootstrap, obtain its role and minimum context, complete a ready task, provide evidence, and hand off without inventing requirements or relying on hidden conversation history.