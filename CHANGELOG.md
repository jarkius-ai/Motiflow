# Changelog

All notable changes to Motiflow and the Motiflow Engineering Operating System (MEOS) are recorded in this file.

The format follows Keep a Changelog principles and uses semantic versioning where practical.

## [Unreleased]

### Added — 2026-07-26
- Pre-implementation readiness packet and validation instruments: validation case catalog, session instruments, artifact worksheets, and instrument dry run under `docs/01-product/validation/`.
- `docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md`, proposed and then accepted with contract decisions C-01–C-06 (`docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`).
- Governance role assignment recorded via PR #5 (`MEOS/roles.yaml`, `CONTEXT_INDEX.yaml` governance assignments).
- Delivery-control documents: `docs/03-delivery/PENDING_WORK_TO_READY.md`, `docs/03-delivery/PLAN_TO_EVIDENCE_TRACEABILITY_MATRIX.md`, `docs/03-delivery/RELEASE_AND_STAGING_DECISION_PLAN.md`, and `docs/03-delivery/DOCUMENTATION_AND_PLANNING_QUALITY_REVIEW.md` (initial quality score 97/100, re-scored 99/100 after alignment fixes and docs-check tooling).
- `docs/adr/ADR-0005-python-backend-and-react-typescript-stack.md`: Python 3.12+/FastAPI backend with React/TypeScript frontend, accepted; validator toolchain is Python `jsonschema>=4.21,<5`.
- Docs-check tooling introduction (link, metadata, and terminology checks) to close the remaining quality-review points.

### Changed — 2026-07-26
- Contract decisions C-01–C-06 accepted by the product owner; ADR-0003 moved from Proposed to Accepted.
- ADR files renamed to a single `ADR-NNNN-title` convention (ADR-0001, ADR-0002, ADR-0003, ADR-0004 — formerly ADR-001 — and new ADR-0005).
- Backend direction changed from Laravel/PHP to Python per ADR-0005; affected foundation and architecture documents updated.
- MVP validation round rescoped to a recorded solo round: the product owner is the sole intended user; multi-user evidence deferred to a post-build pilot (`docs/01-product/MVP_VALIDATION_PLAN.md`).

### Planned
- Validate MEOS against a real Motiflow feature from idea through production.
- Add automated metadata, link, and context-index validation.
- Enforce selected MEOS gates in CI.
- Introduce machine-validated artifact contracts where justified by real use.

## [1.0.0] - 2026-07-25

### Added
- Project Charter and documentation hierarchy.
- Documentation map and authority rules.
- Foundation, product, architecture, engineering, AI, governance, ADR, and archive sections.
- AI collaboration context and current project status documents.
- `CONTEXT_INDEX.yaml` for machine-readable bootstrap and task routing.
- `MEOS/20_PROJECT_BOOTSTRAP.md` as the single MEOS entry point.
- `MEOS/01_ENGINEERING_CONSTITUTION.md` defining non-negotiable engineering rules.
- `MEOS/02_AI_CONSTITUTION.md` defining AI behavior, evidence, escalation, and collaboration boundaries.
- `MEOS/03_CONTEXT_STRATEGY.md` defining minimum-complete context selection and authority resolution.
- `MEOS/05_TASK_SPECIFICATION.md` defining canonical task inputs, outputs, acceptance criteria, contracts, and completion evidence.
- `MEOS/06_DEFINITION_OF_READY.md` defining implementation entry criteria.
- `MEOS/10_QUALITY_GATE.md` defining ACCEPT, LOOP, BLOCKED, and REJECT outcomes and the engineering improvement flywheel.
- `MEOS/11_ARCHITECTURE_RULES.md` defining system boundaries, dependency direction, compatibility, reliability, and architecture review requirements.
- `MEOS/12_CODING_STANDARD.md` defining implementation, testing, security, observability, documentation, dependency, and AI-generated-code standards.
- `MEOS/13_REVIEW_STANDARD.md` defining independent review order, evidence, severity, outcomes, and approval rules.
- `MEOS/14_ADR_PROCESS.md` defining when and how architecture decisions are proposed, reviewed, accepted, superseded, and enforced.
- `MEOS/15_GOLDEN_PATH.md` defining the reference path from idea to production and learning.
- `MEOS/19_AI_WORKFORCE_CHARTER.md` defining role collaboration, separation of duties, handoffs, and escalation.
- `MEOS/roles.yaml` defining machine-readable roles, ownership, required reading, outputs, and authority boundaries.
- `MEOS/RELEASE_1.0_READINESS.md` documenting release scope, readiness assessment, known limitations, and next validation steps.
- Canonical artifact-contract documentation and AI evaluation guidance.

### Changed
- Expanded task specifications to reference affected contracts, migration, rollback, monitoring, independent review, and release evidence.
- Expanded role definitions with collaboration flow, prohibited actions, handoff requirements, and release ownership.
- Expanded context routing for architecture, product, backend, frontend, AI, security-sensitive, contract, and release work.
- Consolidated MEOS into a lean operating layer rather than a large standalone platform.

### Governance
- Architecture changes require ADRs.
- Non-trivial implementation requires independent review.
- Security-sensitive work requires specialist review.
- Release-critical work requires traceable acceptance evidence, migration and rollback planning, and Quality Gate approval.
- AI-generated work is treated as untrusted until independently verified.

### Release Assessment
- MEOS 1.0 documentation and governance baseline: release-ready.
- Operational validation through a real Motiflow feature: pending.
- Automated CI enforcement and repository validation: deferred to a later release based on demonstrated need.

## Versioning Policy

- **Major**: breaking changes to MEOS governance, required workflow, artifact contracts, or authority boundaries.
- **Minor**: backward-compatible capabilities, roles, validation, templates, or workflow improvements.
- **Patch**: clarifications, corrections, link fixes, and non-breaking documentation improvements.

## Change Entry Requirements

Every future release entry should state:
- what changed;
- why it changed;
- whether the change is breaking;
- migration or adoption instructions;
- affected contracts, roles, and workflows;
- validation evidence;
- known risks or deferred work.
