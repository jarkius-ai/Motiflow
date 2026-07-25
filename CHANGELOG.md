# Changelog

All notable changes to Motiflow and the Motiflow Engineering Operating System (MEOS) are recorded in this file.

The format follows Keep a Changelog principles and uses semantic versioning where practical.

## [Unreleased]

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
