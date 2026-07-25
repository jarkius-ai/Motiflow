# Motiflow Architecture Dependency Map

**Status:** Proposed architecture control
**Owner:** Chief Architect
**Related authority:** `MASTER_CONTEXT.md`, ADR-0001

## Purpose

This document defines permitted dependency direction. It prevents the repository from becoming a collection of components that call each other directly without stable boundaries.

## System layers

```text
Application Surfaces (Studio / API / approved worker entry points)
            ↓
Workflow-facing application services
            ↓
Creative Kernel ↔ Workflow Orchestrator
            ↓
Specialist Engines / Critics / Agent roles
            ↓
Model Gateway → Connector Gateway / Connector implementations
            ↓
External Providers and Enterprise Systems

Cross-cutting contracts: schemas, workflows, policy, provenance, observability, security
```

## Canonical dependency direction

```text
apps
  → workflow/orchestration APIs
  → Creative Kernel contracts
  → packages/schemas and packages/workflows

packages/orchestrator
  → packages/workflows
  → Creative Kernel contracts
  → engine and connector capability interfaces

packages/engines and packages/critics
  → Creative Kernel contracts
  → packages/schemas
  → approved connector and knowledge capability interfaces

agent roles
  → declared workflow, engine, and connector capabilities
  → policies and tool boundaries

connectors
  → connector-sdk and gateway interfaces
  → packages/schemas
  → shared infrastructure abstractions

all runtime packages
  → packages/schemas and narrowly scoped shared utilities
```

A lower layer must not import application UI, product-specific presentation logic, or a higher-level workflow implementation.

## Component rules

### Applications

Applications may depend on public SDKs, application services, workflow APIs, and read models. They must not import provider clients or mutate artifact state directly.

### Creative Kernel

The Kernel may depend on schemas, validation primitives, policy definitions, event contracts, provenance contracts, and persistence interfaces.

The Kernel must not depend on:

- UI code;
- provider SDKs;
- specialist engine prompts;
- workflow scheduling implementations;
- publishing destinations.

### Workflow Orchestrator

The Orchestrator may depend on workflow definitions, Kernel state and policy interfaces, engine registries, connector capability interfaces, event contracts, and observability interfaces.

The Orchestrator must not contain narrative, symbolism, creative-direction, prompt-writing, or critic reasoning.

### Engines

Engines may depend on canonical schemas, package contracts, model capability interfaces, knowledge retrieval interfaces, and shared evaluation primitives.

Engines must not:

- call provider SDKs directly;
- write another engine's owned artifact section;
- bypass Kernel validation;
- advance workflow state directly;
- publish external content.

### Agents

Agents coordinate bounded task execution using approved tools, workflows, and engines. They must operate through declared capabilities and policies. Agent convenience must not create hidden cross-layer dependencies or imply a standalone agent package boundary.

### Evaluation

Critics and evaluators may read validated artifacts and evaluation criteria. They produce findings and recommendations; they do not silently rewrite approved artifacts.

### Connectors

Connectors implement normalized interfaces for models, knowledge, storage, image generation, and publishing. Provider-specific types must remain inside the connector implementation.

### Schemas

Schemas are dependency roots. They must not import runtime implementation code. Breaking schema changes require compatibility classification, migration planning, and ADR review when architecture-significant.

### Workflows

Workflow definitions reference registered capabilities and artifact contracts. They must not embed secrets, provider credentials, or undocumented implementation-specific behavior.

## Shared-state rule

The canonical state is a versioned artifact/package model protected by the Creative Kernel. Components exchange identifiers and typed packages; they do not share mutable in-memory domain objects across architectural boundaries.

## External-call rule

```text
Engine or Agent
      ↓ capability request
Connector Gateway
      ↓ normalized adapter
External Provider
```

Direct engine-to-provider access is prohibited.

## Event rule

Events describe completed facts. Commands request work. A component must not use events as undocumented synchronous RPC.

Each event contract must define:

- name and version;
- producer;
- consumers or intended audience;
- payload schema;
- idempotency key;
- correlation and causation identifiers;
- privacy classification;
- compatibility expectations.

## Data ownership

| Data | Owner |
|---|---|
| Canonical schemas and validation state | Creative Kernel |
| Workflow plan and node execution state | Workflow Orchestrator |
| Specialist artifact section | Producing engine, validated by Kernel |
| Provider credentials and raw provider normalization | Connector Gateway |
| Critic findings | Critics and evaluation artifacts |
| Approval decision | Authorized human gate / approval service |
| Product presentation state | Application surfaces |

## Prohibited dependency patterns

- circular package dependencies;
- engine-to-engine direct mutation;
- UI-to-database shortcuts;
- provider SDK usage outside connectors;
- workflow state transitions outside the Orchestrator and Kernel contract;
- schemas importing implementation code;
- generic `shared` packages becoming uncontrolled dumping grounds;
- duplicate domain models for the same canonical artifact.

## Enforcement roadmap

1. Record the dependency rules in documentation.
2. Define package manifests and public interfaces.
3. Add static import-boundary checks when implementation begins.
4. Add schema compatibility checks.
5. Add CI failure messages that identify the violated rule and approved dependency path.
