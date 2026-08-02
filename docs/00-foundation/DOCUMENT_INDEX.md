# Motiflow Document Index

**Status:** Authoritative navigation index
**Owner:** Documentation and Chief Architect
**Applies to:** Repository documentation

## Purpose

This index identifies the canonical home of each major concern. It is a navigation document, not a replacement for the documents it references.

## Canonical bootstrap

1. [`START_HERE.md`](../../START_HERE.md) — sole onboarding router.
2. [`PROJECT_CHARTER.md`](../../PROJECT_CHARTER.md) — vision, mission, scope, principles, and product pillars.
3. [`MASTER_CONTEXT.md`](../../MASTER_CONTEXT.md) — stable system-wide product and architecture context.
4. [`CONTEXT_INDEX.yaml`](../../CONTEXT_INDEX.yaml) — machine-readable role and task routing.
5. [`MEOS/20_PROJECT_BOOTSTRAP.md`](../../MEOS/20_PROJECT_BOOTSTRAP.md) — current engineering state and delivery continuation.

## Foundation governance

| Concern | Canonical document |
|---|---|
| Document authority and conflict resolution | [`DOCUMENT_AUTHORITY.md`](DOCUMENT_AUTHORITY.md) |
| Canonical terminology | [`TERMINOLOGY.md`](TERMINOLOGY.md) |
| Repository target structure | [`REPOSITORY_STRUCTURE.md`](REPOSITORY_STRUCTURE.md) |
| Repository migration sequencing | [`MIGRATION_PLAN.md`](MIGRATION_PLAN.md) |
| Documentation review criteria | [`DOCUMENTATION_QUALITY_CHECKLIST.md`](DOCUMENTATION_QUALITY_CHECKLIST.md) |
| Documentation inventory and normalization findings | [`NORMALIZATION_REPORT.md`](NORMALIZATION_REPORT.md) |
| Repository glossary | [`GLOSSARY.md`](GLOSSARY.md) |

## Product authority

| Concern | Canonical location |
|---|---|
| Product charter | `PROJECT_CHARTER.md` |
| Product vision | [`docs/VISION.md`](../VISION.md) pending focused structural migration |
| Product requirements | [`docs/PRD.md`](../PRD.md) pending focused structural migration |
| Personas and jobs | [`docs/01-product/PERSONAS.md`](../01-product/PERSONAS.md) |
| User journeys and current UX behavior | [`docs/01-product/USER_JOURNEYS.md`](../01-product/USER_JOURNEYS.md) and other applicable `docs/01-product/` specifications; `docs/05-design/` when implemented |
| Review-ready product roadmap | [`docs/ROADMAP.md`](../ROADMAP.md) pending focused structural migration |
| Human-accepted implementation sequencing | An explicitly approved roadmap or task specification |
| MVP validation plan | [`docs/01-product/MVP_VALIDATION_PLAN.md`](../01-product/MVP_VALIDATION_PLAN.md) |
| Current MVP validation evidence | [`docs/01-product/validation/2026-07-25-mvp-validation-report.md`](../01-product/validation/2026-07-25-mvp-validation-report.md) |
| Prepared validation cases | [`docs/01-product/validation/VALIDATION_CASE_CATALOG.md`](../01-product/validation/VALIDATION_CASE_CATALOG.md) |
| Validation session instruments | [`docs/01-product/validation/VALIDATION_SESSION_INSTRUMENTS.md`](../01-product/validation/VALIDATION_SESSION_INSTRUMENTS.md) |
| Validation artifact worksheets | [`docs/01-product/validation/VALIDATION_ARTIFACT_WORKSHEETS.md`](../01-product/validation/VALIDATION_ARTIFACT_WORKSHEETS.md) |
| Validation instrument dry run | [`docs/01-product/validation/2026-07-26-validation-instrument-dry-run.md`](../01-product/validation/2026-07-26-validation-instrument-dry-run.md) |

Product documents may expand the charter but must not redefine Motiflow, ACDS, MEOS, or canonical component boundaries.

## Target platform and phased expansion

These documents describe the complete future-state platform and the controlled path from the focused creative MVP to later capabilities. They do not replace current product authority, accepted contracts, MEOS, ready tasks, or implementation evidence.

| Concern | Canonical location |
|---|---|
| Complete target-state capability architecture | [`docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`](../02-architecture/TARGET_PLATFORM_BLUEPRINT.md) |
| Current and future capability states | [`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md) |
| Mapping of broad blueprint concepts to repository authority | [`docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`](../03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md) |
| Connected vertical-slice phases and activation gates | [`docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`](../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md) |
| Proposed blueprint authority and phased-expansion decision | [`docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](../adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md) |

Use `CONTEXT_INDEX.yaml` to load these documents only for target-capability planning, architecture expansion, reconciliation, or phase activation. Their presence does not mean a future capability is implemented or ready.

## Delivery planning status

`docs/03-delivery/` contains supporting delivery-planning and implementation-sequencing artifacts. Unless a document there is explicitly promoted through human approval, treat it as proposed or review-ready rather than as accepted product or architecture authority.

Current delivery-planning artifacts include:

- `docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md`
- `docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`
- `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- `docs/03-delivery/DOCUMENTATION_AND_PLANNING_QUALITY_REVIEW.md`
- `docs/03-delivery/PLAN_TO_EVIDENCE_TRACEABILITY_MATRIX.md`
- `docs/03-delivery/PENDING_WORK_TO_READY.md`
- `docs/03-delivery/RELEASE_AND_STAGING_DECISION_PLAN.md`
- `docs/03-delivery/UPDATED_PHASE_ROADMAP.md`
- `docs/03-delivery/AI_EXECUTION_IMPLEMENTATION_PLAN.md`
- `docs/03-delivery/PRE_IMPLEMENTATION_READINESS_REVIEW.md`

The first proposed implementation story is
[`MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`](../../MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md).
It remains blocked until its evidence and human-acceptance prerequisites pass.

## Architecture authority

| Concern | Canonical location |
|---|---|
| Stable architecture context | `MASTER_CONTEXT.md` |
| Reference system design | [`docs/SYSTEM_DESIGN.md`](../SYSTEM_DESIGN.md) pending focused structural migration |
| Detailed architecture specifications | `docs/02-architecture/` |
| Target-state platform architecture | [`docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`](../02-architecture/TARGET_PLATFORM_BLUEPRINT.md) |
| Target capability state | [`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md) |
| Architecture dependency direction | [`docs/02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md`](../02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md) |
| Data and artifact contracts | `docs/02-architecture/DATA_CONTRACTS.md` |
| Decisive-slice contract acceptance | [`docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) |
| Architecture decisions | `docs/adr/` |
| Proposed canonical artifact-envelope decision | [`docs/adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md) |
| Proposed target-blueprint and phased-expansion decision | [`docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](../adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md) |
| Security architecture | `docs/02-architecture/` and relevant ADRs |

## Engineering governance

The `MEOS/` directory contains the authoritative engineering operating system. Its documents govern how work is specified, reviewed, verified, and released; they do not redefine the product or runtime architecture.

Key areas include:

- engineering and AI constitutions;
- context strategy and role routing;
- task specification and Definition of Ready;
- quality gates and review standards;
- architecture rules and ADR process;
- Golden Path and release evidence;
- AI workforce roles and responsibilities;
- current project bootstrap.

Use `CONTEXT_INDEX.yaml` to select the minimum complete MEOS context for a task.

## AI and creative-system specifications

| Concern | Canonical location |
|---|---|
| Engine contracts and behavior | `docs/04-ai/` |
| Evaluation and critic specifications | `docs/04-ai/` and `evaluations/` when implemented |
| Prompt assets | `prompts/` |
| Reusable knowledge | `knowledge/` |
| Workflow definitions | `packages/workflows/` when implemented |
| Canonical schemas | `packages/schemas/` when implemented |

## Implementation evidence

Implementation code, tests, generated artifacts, build output, and operational evidence are authoritative only for the behavior they directly demonstrate. They cannot silently supersede accepted product requirements, architecture contracts, ADRs, or capability-state rules.

## Document classes

- **Authoritative:** controls decisions within a declared concern.
- **Supporting:** explains or illustrates an authoritative source.
- **Operational:** records current task, run, release, or verification state.
- **Historical:** preserves superseded context for traceability.
- **Generated:** produced from another canonical source and must identify that source.

## Required metadata for new authoritative documents

Each new authoritative document should state:

- title;
- status;
- owner;
- scope;
- related authority;
- superseded or superseding documents, when applicable;
- last material review date.
