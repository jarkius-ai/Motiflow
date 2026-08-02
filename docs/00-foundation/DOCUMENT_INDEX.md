# Motiflow Document Index

- **Status:** Authoritative navigation index
- **Owner:** Documentation and Chief Architect
- **Responsibility:** Identify the canonical owner and location of each major concern
- **Does not own:** The detailed content of the documents it indexes

## 1. Canonical bootstrap

1. [`START_HERE.md`](../../START_HERE.md) — sole onboarding router.
2. [`PROJECT_CHARTER.md`](../../PROJECT_CHARTER.md) — product purpose, durable scope, principles, and value.
3. [`MASTER_CONTEXT.md`](../../MASTER_CONTEXT.md) — stable ACDS architecture, canonical creative spine, and component boundaries.
4. [`CONTEXT_INDEX.yaml`](../../CONTEXT_INDEX.yaml) — machine-readable minimum-context routing.
5. [`MEOS/20_PROJECT_BOOTSTRAP.md`](../../MEOS/20_PROJECT_BOOTSTRAP.md) — verified current delivery state and next approved work.

## 2. Foundation governance

| Concern | Canonical document |
|---|---|
| Document authority and conflict resolution | [`DOCUMENT_AUTHORITY.md`](DOCUMENT_AUTHORITY.md) |
| One canonical owner per information class | [`DOCUMENT_RESPONSIBILITY_MODEL.md`](DOCUMENT_RESPONSIBILITY_MODEL.md) |
| Architecture and capability change gate | [`ARCHITECTURE_CHANGE_GATE.md`](ARCHITECTURE_CHANGE_GATE.md) |
| Canonical terminology | [`TERMINOLOGY.md`](TERMINOLOGY.md) |
| Repository structure rules | [`REPOSITORY_STRUCTURE.md`](REPOSITORY_STRUCTURE.md) |
| Repository migration sequencing | [`MIGRATION_PLAN.md`](MIGRATION_PLAN.md) |
| Documentation quality criteria | [`DOCUMENTATION_QUALITY_CHECKLIST.md`](DOCUMENTATION_QUALITY_CHECKLIST.md) |
| Documentation inventory/normalization history | [`NORMALIZATION_REPORT.md`](NORMALIZATION_REPORT.md) |
| Glossary | [`GLOSSARY.md`](GLOSSARY.md) |

## 3. Product authority

| Concern | Canonical location |
|---|---|
| Durable product vision, mission, scope, principles, and success | [`PROJECT_CHARTER.md`](../../PROJECT_CHARTER.md) |
| Detailed product requirements | [`docs/PRD.md`](../PRD.md) pending focused migration |
| Personas and jobs | [`docs/01-product/PERSONAS.md`](../01-product/PERSONAS.md) |
| User journeys | [`docs/01-product/USER_JOURNEYS.md`](../01-product/USER_JOURNEYS.md) |
| MVP validation plan | [`docs/01-product/MVP_VALIDATION_PLAN.md`](../01-product/MVP_VALIDATION_PLAN.md) |
| Current MVP validation evidence | [`docs/01-product/validation/2026-07-25-mvp-validation-report.md`](../01-product/validation/2026-07-25-mvp-validation-report.md) |
| Validation cases and instruments | `docs/01-product/validation/` |

Product documents may refine user outcomes and requirements but must not redefine Motiflow, ACDS, MEOS, or accepted architecture without the appropriate authority and ADR.

## 4. Stable and target architecture

| Concern | Canonical location |
|---|---|
| Stable product/runtime context | [`MASTER_CONTEXT.md`](../../MASTER_CONTEXT.md) |
| Detailed current architecture specifications | `docs/02-architecture/` |
| Architecture dependency direction | [`ARCHITECTURE_DEPENDENCY_MAP.md`](../02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md) |
| Complete future destination and expansion seams | [`TARGET_PLATFORM_BLUEPRINT.md`](../02-architecture/TARGET_PLATFORM_BLUEPRINT.md) |
| Evidence-based current capability state | [`TARGET_PLATFORM_CAPABILITY_MAP.md`](../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md) |
| Data and artifact contracts | [`DATA_CONTRACTS.md`](../02-architecture/DATA_CONTRACTS.md) |
| Decisive-slice contract acceptance | [`DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) |
| Publication Package contract | [`PUBLICATION_PACKAGE_CONTRACT.md`](../02-architecture/PUBLICATION_PACKAGE_CONTRACT.md) |
| Architecture decisions | `docs/adr/` |

## 5. Target-platform reconciliation and delivery

| Concern | Canonical location |
|---|---|
| Adopt/adapt/defer/reject mapping | [`BLUEPRINT_RECONCILIATION_MATRIX.md`](../03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md) |
| Section-level source-blueprint review | [`BLUEPRINT_RECONCILIATION_REVIEW.md`](../03-delivery/BLUEPRINT_RECONCILIATION_REVIEW.md) |
| Structural reconciliation validation | [`BLUEPRINT_RECONCILIATION_VALIDATION.md`](../03-delivery/BLUEPRINT_RECONCILIATION_VALIDATION.md) |
| Complete 193-file source-manifest disposition | [`BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`](../03-delivery/BLUEPRINT_FILE_MANIFEST_DISPOSITION.md) and linked appendices |
| Responsibility migration record | [`DOCUMENT_RESPONSIBILITY_MIGRATION_REPORT.md`](../03-delivery/DOCUMENT_RESPONSIBILITY_MIGRATION_REPORT.md) |
| Connected Phase 0–8 expansion sequence | [`CAPABILITY_EXPANSION_ROADMAP.md`](../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md) |
| Accepted blueprint responsibility and phased-expansion decision | [`ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](../adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md) |

The roadmap and blueprint do not authorize implementation. Phase activation requires accepted decisions, applicable evidence, ready tasks, and MEOS verification.

## 6. Current implementation readiness

| Concern | Canonical location |
|---|---|
| Current delivery status and blockers | [`MEOS/20_PROJECT_BOOTSTRAP.md`](../../MEOS/20_PROJECT_BOOTSTRAP.md) |
| Pending work ordered toward readiness | [`PENDING_WORK_TO_READY.md`](../03-delivery/PENDING_WORK_TO_READY.md) |
| Current readiness review and score | [`PRE_IMPLEMENTATION_READINESS_REVIEW.md`](../03-delivery/PRE_IMPLEMENTATION_READINESS_REVIEW.md) |
| Current first task | [`MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`](../../MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md) |
| Blocking artifact-envelope decision | [`ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md) |

Task 001 remains blocked until its product, contract, architecture, toolchain, reviewer, QA, and Definition of Ready prerequisites pass.

## 7. Engineering governance

The `MEOS/` directory is the only engineering operating system. It owns:

- engineering and AI constitutions;
- role and context routing;
- task specification;
- Definition of Ready;
- coding and architecture standards;
- review independence;
- Quality Gate;
- ADR process;
- Golden Path and release evidence;
- current project bootstrap.

MEOS governs how work is done; it does not redefine product scope or target architecture.

## 8. AI and creative-system assets

| Concern | Canonical location |
|---|---|
| Engine and AI contracts | `docs/04-ai/` |
| Evaluation specifications | `docs/04-ai/` and `evaluations/` when implemented |
| Prompt assets | `prompts/` |
| Reusable approved knowledge | `knowledge/` |
| Workflow definitions | `packages/workflows/` when implemented |
| Canonical schemas | `packages/schemas/` when implemented |

These paths are introduced only when accepted contracts or ready tasks require them.

## 9. Implementation truth

Code, schemas, tests, fixtures, generated artifacts, CI output, review reports, deployment evidence, and other observed records are authoritative only for behavior they directly demonstrate.

They cannot silently supersede the Charter, Master Context, accepted ADRs, or contracts. Conversely, architecture and planning prose cannot be used as evidence that implementation exists.

## 10. Document classes

- **Authoritative** — controls decisions within a declared concern.
- **Supporting** — explains or illustrates an authority.
- **Operational** — records current task, run, review, release, or verification state.
- **Historical** — preserves superseded context and traceability.
- **Generated** — derived from an identified canonical source.

## 11. Required metadata for new authoritative documents

Each new authoritative document should state:

- status;
- owner;
- responsibility;
- non-responsibilities;
- related authorities;
- superseded/superseding references where applicable;
- last material decision date.
