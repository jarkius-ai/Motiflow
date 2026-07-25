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
| Product vision | `docs/01-product/` |
| Product requirements | `docs/01-product/` |
| Personas and jobs | `docs/01-product/` |
| User journeys and UX behavior | `docs/01-product/` and `docs/05-design/` |
| Roadmap and implementation sequencing | `docs/01-product/` or an explicitly approved roadmap document |

Product documents may expand the charter but must not redefine Motiflow, ACDS, MEOS, or canonical component boundaries.

## Architecture authority

| Concern | Canonical location |
|---|---|
| Stable architecture context | `MASTER_CONTEXT.md` |
| Detailed architecture specifications | `docs/02-architecture/` |
| Architecture dependency direction | [`docs/02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md`](../02-architecture/ARCHITECTURE_DEPENDENCY_MAP.md) |
| Data and artifact contracts | `docs/02-architecture/DATA_CONTRACTS.md` |
| Architecture decisions | `docs/adr/` |
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
| Evaluation and critic specifications | `docs/04-ai/` and `evaluation/` when implemented |
| Prompt assets | `prompts/` |
| Reusable knowledge | `knowledge/` |
| Workflow definitions | `workflows/` when implemented |
| Canonical schemas | `schemas/` when implemented |

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
