# Motiflow

**Creative intelligence, orchestrated.**

Motiflow is an enterprise creative-intelligence platform that transforms business meaning, research, narrative intent, audience needs, and brand constraints into governed visual direction and production-ready creative artifacts.

Its underlying product architecture is the **Autonomous Creative Direction System (ACDS)**. Motiflow is built and maintained through the **Motiflow Engineering Operating System (MEOS)**, which defines engineering governance, delivery standards, verification gates, and role-based context.

## Product Modules

- **Motiflow Studio** — workspace for briefs, review, and approvals
- **Motiflow Intelligence** — research, narrative, audience, and business analysis
- **Motiflow Direction** — symbolism, metaphor, and creative-direction engines
- **Motiflow Flow** — workflow orchestration and execution monitoring
- **Motiflow Review** — multi-critic evaluation and human approval gates
- **Motiflow Platform** — APIs, connectors, SDKs, and enterprise integration

## Start Here

Every contributor and AI agent should begin with [`START_HERE.md`](./START_HERE.md).

The canonical foundation reading order is:

1. [`START_HERE.md`](./START_HERE.md)
2. [`PROJECT_CHARTER.md`](./PROJECT_CHARTER.md)
3. [`MASTER_CONTEXT.md`](./MASTER_CONTEXT.md)
4. [`CONTEXT_INDEX.yaml`](./CONTEXT_INDEX.yaml)
5. [`MEOS/20_PROJECT_BOOTSTRAP.md`](./MEOS/20_PROJECT_BOOTSTRAP.md)
6. task-specific product, architecture, engineering, AI, design, contract, ADR, and implementation documents

Foundation standards:

- [`DOCUMENT_AUTHORITY.md`](./docs/00-foundation/DOCUMENT_AUTHORITY.md)
- [`TERMINOLOGY.md`](./docs/00-foundation/TERMINOLOGY.md)
- [`REPOSITORY_STRUCTURE.md`](./docs/00-foundation/REPOSITORY_STRUCTURE.md)
- [`MIGRATION_PLAN.md`](./docs/00-foundation/MIGRATION_PLAN.md)

## Core Principles

- Understand before generating
- Separate reasoning from rendering
- Business meaning drives aesthetics
- Prefer one dominant narrative and one dominant metaphor
- Keep critical decisions explainable, versioned, and reviewable
- Use model-agnostic interfaces
- Require human approval at meaningful risk and quality gates

## Target Repository Structure

The following is the approved target structure, not a claim that every directory already exists:

```text
Motiflow/
├── apps/
├── packages/
│   ├── core/
│   ├── orchestrator/
│   ├── engines/
│   ├── agents/
│   ├── evaluation/
│   ├── connectors/
│   ├── sdk/
│   └── shared/
├── schemas/
├── workflows/
├── prompts/
├── knowledge/
├── docs/
├── infrastructure/
├── tools/
├── examples/
└── tests/
```

Directories should be introduced only when they contain implemented or intentionally governed artifacts.

## Current Status

**Foundation alignment phase — terminology, document authority, repository structure, and migration sequencing.**

Implementation should begin only after the governing documents, canonical contracts, and first vertical-slice task are aligned and ready under MEOS.
