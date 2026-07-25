# Motiflow Terminology Standard

**Status:** Proposed foundation standard

## System identity

- **Motiflow** — the customer-facing product and platform brand.
- **ACDS (Autonomous Creative Direction System)** — the product architecture that transforms business meaning into governed creative direction and production-ready artifacts.
- **MEOS (Motiflow Engineering Operating System)** — the engineering governance and delivery system used by humans and AI agents to build Motiflow safely and consistently.

ACDS defines how the product reasons and operates. MEOS defines how the repository and engineering work are governed and delivered. MEOS is not a runtime subsystem of ACDS.

## Core runtime terms

- **Creative Kernel** — the integrity and governance runtime for schemas, validation, provenance, confidence, policy, versioning, approvals, and artifact state. Keep this official name until an ADR approves a rename.
- **Workflow Orchestrator** — the runtime responsible for DAG planning, dependency resolution, scheduling, retries, gates, and validated handoffs.
- **Specialist Engine** — a bounded reasoning component with explicit input and output contracts.
- **Critic** — a specialist evaluator that scores one or more explicit quality dimensions and returns evidence-backed findings.
- **Connector** — an adapter to an external provider or enterprise service. A connector must not contain domain orchestration logic.
- **Connector Gateway** — the outer controlled runtime boundary for external providers and enterprise services. It applies policy, credentials, observability, and normalized connector access.
- **Model Gateway** — the provider-neutral model-execution contract inside the connector boundary. It routes declared model capabilities, applies model-specific policy, validation, retry/fallback, provenance, usage, and cost controls without exposing provider SDKs to engines.
- **Workflow** — a versioned DAG definition that coordinates engines, gates, connectors, and human actions.
- **Run** — one execution instance of a workflow.
- **Package** — an immutable, versioned, validated information object exchanged between stages.
- **Artifact** — a governed output produced or referenced by a run, including images, documents, specifications, evaluations, and approval records.
- **Schema** — the machine-readable contract that defines a package, event, workflow, or artifact structure.
- **Agent** — an autonomous or semi-autonomous actor that performs a role using tools and policies. Do not use “agent” as a synonym for engine.

## Product module names

- **Motiflow Studio** — human workspace for briefs, workflow visibility, comparison, review, and approval.
- **Motiflow Intelligence** — research, narrative, audience, brand, and business analysis capabilities.
- **Motiflow Direction** — symbolism, metaphor, creative direction, composition, and visual-language capabilities.
- **Motiflow Flow** — workflow orchestration and execution visibility.
- **Motiflow Review** — critic evaluation, comparison, approvals, and decision history.
- **Motiflow Platform** — APIs, SDKs, connectors, identity, governance, and enterprise integration.

## Naming rules

1. Use **Motiflow**, not MotiFlow, Moti Flow, or Motiflow AI.
2. Use **ACDS** only for the product architecture.
3. Use **MEOS** only for engineering governance and delivery.
4. Use **engine** for bounded reasoning and **agent** for role-driven autonomous action.
5. Use **package** for typed information exchange and **artifact** for governed outputs.
6. Use **connector** for provider adapters and **gateway** for the controlled connector boundary.
7. Do not introduce new synonyms for canonical terms without updating this standard and, when significant, recording an ADR.
