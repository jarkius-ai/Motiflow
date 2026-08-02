# Plan-to-Evidence Traceability Matrix

**Status:** Operational delivery control; promoted by the accountable owner (Jarkius) 2026-07-26
**Owner:** Jarkius — Chief Architect and Delivery
**Scope:** Trace current Motiflow plans from authority through evidence and decision state
**Last reviewed:** 2026-07-26

## Purpose

Give contributors one place to determine what controls each delivery concern,
which plan operationalizes it, what evidence proves progress, and whether the
decision is accepted, proposed, or blocked. This matrix routes to source
documents; it does not replace them or promote pending decisions.

## Traceability rules

- Product and architecture authority control delivery plans, not the reverse.
- Accepted ADRs control architecture-significant decisions within their scope.
- A proposed plan or ADR may guide review but cannot authorize implementation.
- Evidence records observed results; templates and simulations remain preparation evidence.
- A score cannot promote a failed mandatory gate.

## Current matrix

| Concern | Controlling authority | Operational plan or contract | Required evidence | Current state |
|---|---|---|---|---|
| Product identity and boundary | `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md` | `docs/PRD.md` | accepted scope and explicit exclusions | Foundation accepted; PRD review-ready |
| Decisive MVP slice | `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md` | `docs/01-product/MVP_VALIDATION_PLAN.md`, `docs/ROADMAP.md` | solo-round session outcomes and product-owner decision (scope revised 2026-07-26) | Sessions pending under the recorded solo scope |
| Ten-artifact vocabulary | `MASTER_CONTEXT.md` | `docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md` C-01 | recorded disposition and reconciled contracts | `ACCEPT` recorded 2026-07-26 |
| Two human approval gates | `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md` | `docs/02-architecture/WORKFLOW_STATE_MACHINE.md`, acceptance C-02 and C-04 | gate-comprehension evidence and accepted contract | Product requirement accepted; contract details pending |
| Canonical artifact envelope | accepted ADR when available | `docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md`, acceptance C-03 | accepted ADR and corrected controlling contracts | ADR-0003 `Accepted` 2026-07-26; contract-doc reconciliation carried by the evidence/sign-off commit |
| Schema and unknown-field policy | architecture contracts and accepted ADR | acceptance C-05, `docs/02-architecture/VERSIONING_AND_COMPATIBILITY.md` | accepted dialect/version policy and schema tests | C-05 `ACCEPT` recorded 2026-07-26; schema tests await Task 001 |
| Validator and dependency boundary | accepted C-06 decision | `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md` | approved toolchain, lockfile, command transcript, CI result | C-06 `ACCEPT` 2026-07-26: Python 3.12+/`jsonschema` per ADR-0005; transcript and CI await Task 001 |
| Validation protocol | `docs/01-product/MVP_VALIDATION_PLAN.md` | case catalog, session instruments, artifact worksheets | run sheets, stop records, aggregates, decision | Prepared; participant execution pending |
| Task readiness | `MEOS/06_DEFINITION_OF_READY.md` | `docs/03-delivery/PENDING_WORK_TO_READY.md`, Task 001 | completed readiness report with no blocking item | Task 001 blocked on solo-round session evidence and final DoR (46/100) |
| Autonomous agent execution | `MEOS/02_AI_CONSTITUTION.md`, `MEOS/19_AI_WORKFORCE_CHARTER.md` | `docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md` | role-separated handoffs, tests, reviews, escalation records | Proposed operating model; protected authority unchanged |
| Implementation sequence | accepted tasks and architecture | `docs/03-delivery/UPDATED_PHASE_ROADMAP.md`, `AI_EXECUTION_IMPLEMENTATION_PLAN.md` | accepted task outputs and quality-gate evidence | Review-ready; Task 001 is first proposed build |
| Staging and release | `MEOS/10_QUALITY_GATE.md`, `MEOS/15_GOLDEN_PATH.md` | `docs/03-delivery/RELEASE_AND_STAGING_DECISION_PLAN.md` | release packet, rollback proof, monitoring plan, authorization | Plan ready; no releasable product exists |
| Documentation and planning quality | `MEOS/RELEASE_1.0_READINESS.md`, documentation checklist | `docs/03-delivery/DOCUMENTATION_AND_PLANNING_QUALITY_REVIEW.md` | link, metadata, routing, authority, and consistency checks | 100/100 documentation-plan assessment; docs-check tooling enforced |

## Critical path

```text
Prepared validation packet
  -> solo-round session evidence (scope revised 2026-07-26)
  -> product-owner decision
  -> C-01 through C-06 acceptance          [DONE 2026-07-26]
  -> ADR-0003 acceptance                   [DONE 2026-07-26; reconciliation lands with the evidence/sign-off commit]
  -> post-session evidence/sign-off commit [PENDING; follows the sessions and product-owner decision]
  -> Task 001 Definition of Ready
  -> schemas, fixtures, validator, and CI
  -> independent verification and Quality Gate
```

Any contributor encountering a different immediate implementation sequence must
stop and reconcile it against `START_HERE.md`, `CONTEXT_INDEX.yaml`, and this
matrix before proceeding.
