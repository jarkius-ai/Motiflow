# Motiflow

**Creative intelligence, orchestrated.**

Motiflow is an enterprise creative-intelligence platform that transforms business meaning, research, and narrative intent into governed visual direction and production-ready creative artifacts.

Its underlying technical architecture is the **Autonomous Creative Direction System (ACDS)**.

## Product modules

- **Motiflow Studio** — workspace for briefs, review, and approvals
- **Motiflow Intelligence** — research, narrative, audience, and business analysis
- **Motiflow Direction** — symbolism, metaphor, and creative-direction engines
- **Motiflow Flow** — workflow orchestration and execution monitoring
- **Motiflow Review** — multi-critic evaluation and human approval gates
- **Motiflow Platform** — APIs, connectors, SDKs, and enterprise integration

## Start here

1. Read [`MASTER_CONTEXT.md`](./MASTER_CONTEXT.md)
2. Review [`docs/VISION.md`](./docs/VISION.md)
3. Review [`docs/PRD.md`](./docs/PRD.md)
4. Review [`docs/SYSTEM_DESIGN.md`](./docs/SYSTEM_DESIGN.md)
5. Follow accepted decisions in [`docs/adr`](./docs/adr)

## Core principles

- Understand before generating
- Separate reasoning from rendering
- Business meaning drives aesthetics
- Prefer one dominant narrative and one dominant metaphor
- Keep critical decisions explainable, versioned, and reviewable
- Use model-agnostic interfaces
- Require human approval at meaningful risk and quality gates

## Target repository structure

```text
Motiflow/
├── README.md
├── MASTER_CONTEXT.md
├── docs/
│   ├── VISION.md
│   ├── PRD.md
│   ├── SYSTEM_DESIGN.md
│   ├── ROADMAP.md
│   └── adr/
├── apps/
│   ├── studio/
│   └── api/
├── packages/
│   ├── creative-kernel/
│   ├── orchestrator/
│   ├── engine-sdk/
│   └── connector-sdk/
├── knowledge/
├── prompts/
├── database/
├── diagrams/
└── infrastructure/
```

## Current status

**Foundation phase — product definition and architecture.**
