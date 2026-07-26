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
| Transitional navigation summary | [`docs/DOCUMENTATION_MAP.md`](../DOCUMENTATION_MAP.md) |
| Product manifesto | [`MANIFESTO.md`](MANIFESTO.md) |
| Product principles | [`PRODUCT_PRINCIPLES.md`](PRODUCT_PRINCIPLES.md) |
| Migration Phase 2 completion record | [`PHASE_2_COMPLETION.md`](PHASE_2_COMPLETION.md) |
| Archive policy and historical material | [`docs/archive/README.md`](../archive/README.md) |

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
| Success metrics | [`docs/01-product/SUCCESS_METRICS.md`](../01-product/SUCCESS_METRICS.md) |
| Content and visual review workspace | [`docs/01-product/CONTENT_VISUAL_REVIEW_WORKSPACE.md`](../01-product/CONTENT_VISUAL_REVIEW_WORKSPACE.md) |

Product documents may expand the charter but must not redefine Motiflow, ACDS, MEOS, or canonical component boundaries.

## Delivery planning status

`docs/03-delivery/` contains supporting delivery-planning and implementation-sequencing artifacts. Unless a document there is explicitly promoted through human approval, treat it as proposed or review-ready rather than as accepted product or architecture authority (the delivery-control set and quality review were explicitly promoted 2026-07-26).

Current delivery-planning artifacts include:

- `docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md`
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
| Architecture dependency direction | [`docs/02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md`](../02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md) |
| Data and artifact contracts | `docs/02-architecture/DATA_CONTRACTS.md` |
| Decisive-slice contract acceptance | [`docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) |
| Runtime execution contracts | [`docs/02-architecture/RUNTIME_CONTRACTS.md`](../02-architecture/RUNTIME_CONTRACTS.md) |
| Two-gate workflow state machine | [`docs/02-architecture/WORKFLOW_STATE_MACHINE.md`](../02-architecture/WORKFLOW_STATE_MACHINE.md) |
| Versioning and compatibility policy | [`docs/02-architecture/VERSIONING_AND_COMPATIBILITY.md`](../02-architecture/VERSIONING_AND_COMPATIBILITY.md) |
| Creative Kernel specification | [`docs/02-architecture/CREATIVE_KERNEL.md`](../02-architecture/CREATIVE_KERNEL.md) |
| Workflow Orchestrator specification | [`docs/02-architecture/WORKFLOW_ORCHESTRATOR.md`](../02-architecture/WORKFLOW_ORCHESTRATOR.md) |
| Engine catalog | [`docs/02-architecture/ENGINE_CATALOG.md`](../02-architecture/ENGINE_CATALOG.md) |
| AI execution layer architecture | [`docs/02-architecture/AI_EXECUTION_LAYER.md`](../02-architecture/AI_EXECUTION_LAYER.md) |
| Publication package contract | [`docs/02-architecture/PUBLICATION_PACKAGE_CONTRACT.md`](../02-architecture/PUBLICATION_PACKAGE_CONTRACT.md) |
| Article ingestion and editorial pipeline | [`docs/02-architecture/ARTICLE_INGESTION_AND_EDITORIAL_PIPELINE.md`](../02-architecture/ARTICLE_INGESTION_AND_EDITORIAL_PIPELINE.md) |
| Engineering architecture (stack and platform direction) | [`docs/02-architecture/ENGINEERING_ARCHITECTURE.md`](../02-architecture/ENGINEERING_ARCHITECTURE.md) |
| Architecture decisions | `docs/adr/` |
| Terminology decision | [`docs/adr/ADR-0001-product-architecture-and-governance-terminology.md`](../adr/ADR-0001-product-architecture-and-governance-terminology.md) |
| Provider-neutral AI gateway decision (proposed) | [`docs/adr/ADR-0002-provider-neutral-ai-gateway.md`](../adr/ADR-0002-provider-neutral-ai-gateway.md) |
| Canonical artifact-envelope decision | [`docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md`](../adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md) |
| Hybrid DAG execution decision | [`docs/adr/ADR-0004-hybrid-dag-execution.md`](../adr/ADR-0004-hybrid-dag-execution.md) |
| Backend and frontend stack decision | [`docs/adr/ADR-0005-python-backend-and-react-typescript-stack.md`](../adr/ADR-0005-python-backend-and-react-typescript-stack.md) |
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

| Concern | Canonical document |
|---|---|
| Non-negotiable engineering rules | [`MEOS/01_ENGINEERING_CONSTITUTION.md`](../../MEOS/01_ENGINEERING_CONSTITUTION.md) |
| AI behavior, evidence, and escalation boundaries | [`MEOS/02_AI_CONSTITUTION.md`](../../MEOS/02_AI_CONSTITUTION.md) |
| Minimum-complete context selection | [`MEOS/03_CONTEXT_STRATEGY.md`](../../MEOS/03_CONTEXT_STRATEGY.md) |
| Canonical task specification format | [`MEOS/05_TASK_SPECIFICATION.md`](../../MEOS/05_TASK_SPECIFICATION.md) |
| Implementation entry criteria | [`MEOS/06_DEFINITION_OF_READY.md`](../../MEOS/06_DEFINITION_OF_READY.md) |
| Quality gate outcomes and evidence | [`MEOS/10_QUALITY_GATE.md`](../../MEOS/10_QUALITY_GATE.md) |
| Architecture rules and dependency direction | [`MEOS/11_ARCHITECTURE_RULES.md`](../../MEOS/11_ARCHITECTURE_RULES.md) |
| Coding standard | [`MEOS/12_CODING_STANDARD.md`](../../MEOS/12_CODING_STANDARD.md) |
| Independent review standard | [`MEOS/13_REVIEW_STANDARD.md`](../../MEOS/13_REVIEW_STANDARD.md) |
| ADR process and lifecycle | [`MEOS/14_ADR_PROCESS.md`](../../MEOS/14_ADR_PROCESS.md) |
| Golden Path from idea to production | [`MEOS/15_GOLDEN_PATH.md`](../../MEOS/15_GOLDEN_PATH.md) |
| AI workforce roles and separation of duties | [`MEOS/19_AI_WORKFORCE_CHARTER.md`](../../MEOS/19_AI_WORKFORCE_CHARTER.md) |
| Current engineering state and continuation | [`MEOS/20_PROJECT_BOOTSTRAP.md`](../../MEOS/20_PROJECT_BOOTSTRAP.md) |
| Machine-readable role registry | [`MEOS/roles.yaml`](../../MEOS/roles.yaml) |
| MEOS 1.0 release readiness record | [`MEOS/RELEASE_1.0_READINESS.md`](../../MEOS/RELEASE_1.0_READINESS.md) |

Use `CONTEXT_INDEX.yaml` to select the minimum complete MEOS context for a task.

## AI and creative-system specifications

| Concern | Canonical location |
|---|---|
| Engine contracts and behavior | `docs/04-ai/` |
| Evaluation framework and critic rubric baseline | [`docs/04-ai/EVALUATION_FRAMEWORK.md`](../04-ai/EVALUATION_FRAMEWORK.md) |
| Contribution and engineering-governance guidance | [`docs/05-governance/CONTRIBUTING.md`](../05-governance/CONTRIBUTING.md) |
| Evaluation and critic specifications | `docs/04-ai/` and `evaluations/` when implemented |
| Prompt assets | `prompts/` |
| Reusable knowledge | `knowledge/` |
| Workflow definitions | `packages/workflows/` when implemented |
| Canonical schemas | `packages/schemas/` when implemented |

## Implementation evidence

Implementation code, tests, generated artifacts, build output, and operational evidence are authoritative only for the behavior they directly demonstrate. They cannot silently supersede accepted product requirements, architecture contracts, or ADRs.

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
