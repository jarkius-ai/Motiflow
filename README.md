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
- **Motiflow Platform** — APIs, connectors, SDKs, and enterprise integration after MVP proof

## Start Here

Every contributor and AI agent should begin with [`START_HERE.md`](./START_HERE.md).

The canonical foundation reading order is:

1. [`START_HERE.md`](./START_HERE.md)
2. [`PROJECT_CHARTER.md`](./PROJECT_CHARTER.md)
3. [`MASTER_CONTEXT.md`](./MASTER_CONTEXT.md)
4. [`CONTEXT_INDEX.yaml`](./CONTEXT_INDEX.yaml)
5. [`MEOS/20_PROJECT_BOOTSTRAP.md`](./MEOS/20_PROJECT_BOOTSTRAP.md)
6. task-specific product, architecture, engineering, AI, design, contract, ADR, and implementation documents

The `20` in the MEOS bootstrap filename is a topic identifier, not a fifth-step
sequence number. MEOS documents are selected by task routing; they are not read
as one numeric series.

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

## Current Decisive Slice

The product destination is a creative-direction-first MVP, not broad platform
breadth. No implementation task is ready yet.

The current ordered work is to execute intended-user validation, record the
product decision, close C-01 through C-06 and ADR-0003, and pass Task 001's
Definition of Ready. The first implementation after those gates is the bounded
ten-artifact schema, fixture, validator, and CI contract proof. The
provider-backed generation and review loop follows only after that proof is
accepted.

The eventual workflow retains **Approval Gate 1** before committing creative
direction downstream and **Approval Gate 2** after candidate critique and before
export or equivalent finalization. Publication-platform breadth, editorial
authoring expansion, multi-provider infrastructure, and publishing connectors
remain parked until MVP proof is accepted.

## Target Repository Structure

The following is the proposed canonical target structure. It describes a target state and does not claim that every directory already exists on the current branch:

```text
Motiflow/
├── MEOS/
├── docs/
├── apps/
│   ├── studio/
│   ├── api/
│   └── worker/
├── packages/
│   ├── creative-kernel/
│   ├── orchestrator/
│   ├── engines/
│   ├── critics/
│   ├── connectors/
│   ├── schemas/
│   ├── workflows/
│   ├── engine-sdk/
│   ├── connector-sdk/
│   └── shared/
├── knowledge/
├── prompts/
├── evaluations/
├── examples/
├── tools/
├── infrastructure/
└── diagrams/
```

Directories should be introduced only when they contain implemented or intentionally governed artifacts.

## Current Status

**Pre-implementation readiness for a creative-direction-first MVP proof.**

The documentation baseline is reconciled and review-ready. The next work is to
execute the MVP validation plan, record the accountable product-owner decision,
close the contract and ADR decisions, and promote the bounded Task 001 contract
proof only after its Definition of Ready passes. Broad Model Gateway
infrastructure, publication-platform expansion, editorial authoring breadth,
and connector ecosystems remain deferred.
