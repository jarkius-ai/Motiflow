# Motiflow Master Context

- **Architecture name:** Autonomous Creative Direction System (ACDS)
- **Version:** 1.1
- **Status:** Stable shared architecture context
- **Product:** Motiflow
- **Positioning:** Creative intelligence, orchestrated
- **Responsibility:** Define what Motiflow is, its stable runtime concepts, canonical creative spine, component boundaries, data ownership, and architecture principles
- **Does not own:** Product vision, current implementation state, phase sequencing, task readiness, provider installation, or verification evidence

## 1. Purpose

This document provides the minimum durable product/runtime context that every material Motiflow change must preserve unless an accepted ADR changes it.

It is intentionally stable. Product purpose is owned by `PROJECT_CHARTER.md`; future platform destination by the Target Platform Blueprint; current state by the Capability Map and Project Bootstrap; expansion order by the Capability Expansion Roadmap; engineering execution by MEOS.

## 2. System identity

- **Motiflow** — customer-facing product, platform, and repository identity.
- **ACDS** — product/runtime architecture for governed creative intelligence.
- **MEOS** — engineering operating system for readiness, roles, execution, review, verification, and release.
- **Creative Kernel** — integrity and governance runtime.
- **Workflow Orchestrator** — workflow planner, scheduler, and state coordinator.
- **Specialist Engine** — bounded reasoning or transformation component with typed inputs and outputs.
- **Critic** — independent evaluator that produces findings without silently mutating reviewed artifacts.
- **Connector Gateway** — controlled boundary to external providers, storage, knowledge sources, browser execution, and enterprise services.
- **Model Gateway** — provider-neutral model execution contract behind the Connector Gateway.
- **Motiflow Studio** — human workspace for intake, workflow visibility, comparison, review, approval, and package preview.

These names are canonical and must not be replaced by parallel systems without an accepted ADR.

## 3. Stable product architecture

```text
Human / API / Approved Connector Input
                 ↓
          Motiflow Studio / API
                 ↓
      Creative Kernel ↔ Workflow Orchestrator
                 ↓
   Specialist Engines / Critics / Bounded Agents
                 ↓
          Connector Gateway
       ┌─────────┼─────────────┐
       ↓         ↓             ↓
 Model Gateway  Knowledge     Execution and
                Providers     Publishing Providers
       └─────────┼─────────────┘
                 ↓
       External Systems and Tools
```

Cross-cutting roots are schemas, workflows, policy, provenance, evidence, security, observability, versioning, evaluation, human authority, and approved memory.

## 4. Product philosophy

1. Understand before creating.
2. Meaning drives form.
3. One dominant narrative.
4. One dominant metaphor.
5. Reasoning and rendering remain separate.
6. Components exchange structured, versioned outputs rather than uncontrolled prose.
7. Human judgment remains explicit at protected gates.
8. Models and providers remain replaceable.
9. Rationale, evidence, confidence, uncertainty, and provenance are preserved.
10. Quality is measured by usable outcomes, not generation volume.

## 5. Canonical creative spine

The decisive product workflow uses these immutable, versioned artifacts:

```text
Intake Package
→ Normalized Brief
→ Knowledge Fusion Package
→ Creative Direction Package
→ Direction Approval Record
→ Generation Specification
→ Generated Candidate Set
→ Critic Evaluation Package
→ Final Approval Record
→ Provenance Record
```

This sequence is the stable core that future acquisition, editorial, publication, publishing, measurement, and enterprise capabilities must extend rather than replace.

Supporting artifacts and package sections may exist, but they must not create competing canonical handoffs.

## 6. Creative Kernel responsibilities

The Creative Kernel owns:

- canonical artifact and package contracts;
- schema validation and compatibility;
- immutable versioning and lineage;
- state-transition protection;
- invalidation rules;
- policy and permission enforcement;
- approval requirements;
- provenance and evidence linkage;
- confidence and validation metadata.

It does not:

- decide creative meaning;
- schedule tasks;
- select providers;
- call external systems directly;
- publish externally.

## 7. Workflow Orchestrator responsibilities

The Workflow Orchestrator owns:

- workflow DAG planning and execution;
- sequential and parallel stage scheduling;
- dependency resolution;
- retries, timeouts, cancellation, and safe resume;
- budgets and resource controls;
- approval pauses and resumptions;
- capability resolution;
- run status and observability;
- validated handoffs between components.

It does not own canonical contracts, specialist reasoning, provider implementations, or human approval authority.

## 8. Hybrid execution model

Motiflow uses a hybrid directed acyclic graph.

### Parallel discovery

Independent research, audience, brand, business, and narrative analyses may run concurrently.

### Knowledge fusion

Outputs are combined into a validated Knowledge Fusion Package. Conflicts, missing evidence, and confidence gaps remain visible.

### Sequential creative commitment

Creative direction, direction approval, generation specification, candidate evaluation, and final approval are progressively constrained and predominantly sequential.

### Parallel derivation

After direction approval, bounded composition, lighting, material, camera, palette, and provider-adaptation work may run in parallel where contracts permit.

### Governed completion

Only current approved versions may progress. Revisions invalidate declared downstream artifacts and approvals.

## 9. Human approval model

The creative core protects two non-bypassable gates:

1. **Direction approval** after the Creative Direction Package and before Generation Specification.
2. **Final approval** after Generated Candidate Set and Critic Evaluation Package and before export or publication.

Every decision records actor, role, timestamp, rationale, decision, conditions, and exact artifact versions.

External publication requires a distinct publishing authorization. Final creative approval is not permission to write to an external system.

## 10. Data and artifact rules

Every canonical artifact should carry:

- stable artifact identifier;
- artifact type;
- schema and artifact versions;
- project and workflow-run identifiers;
- versioned parent references;
- creation time and accountable creator;
- producer and provider metadata where applicable;
- source and evidence references;
- confidence and uncertainty;
- provenance;
- validation state;
- typed payload.

Components exchange identifiers and typed packages rather than shared mutable in-memory domain objects.

## 11. Dependency direction

```text
Applications
  → workflow-facing application services
  → Creative Kernel and Workflow Orchestrator contracts
  → schemas, workflows, policies, and approved capability interfaces

Engines and Critics
  → canonical schemas and capability interfaces
  → Connector Gateway ports

Connectors
  → normalized connector contracts
  → external providers
```

Prohibited patterns include:

- provider SDKs inside engines or workflows;
- UI-to-database shortcuts;
- engine-to-engine mutation;
- workflow transitions outside Orchestrator/Kernel contracts;
- duplicate domain models for the same artifact;
- events used as undocumented synchronous RPC;
- generic shared packages that become uncontrolled dependency hubs.

## 12. Connector and provider model

External systems are replaceable implementations behind provider-neutral contracts.

The Connector Gateway owns provider-specific authentication, payloads, retries, health, audit, and normalization.

Agent Reach, browser extension bridges, Playwright/CDP, semantic browser systems, model vendors, reader services, and publishing platforms are possible implementations—not architecture owners and not current-state assumptions.

No provider can weaken Motiflow approval, provenance, security, or validation requirements.

## 13. Quality model

Quality is evaluated through explicit dimensions such as:

- strategic alignment;
- narrative clarity;
- metaphor strength;
- audience relevance;
- brand alignment;
- hierarchy and composition;
- technical quality;
- originality;
- accessibility;
- policy and safety;
- production usability.

A composite score may support prioritization but cannot hide a failed mandatory dimension.

## 14. UX principles

Motiflow Studio presents concise rationale, evidence, alternatives, confidence, dependencies, decisions, and change impact without exposing hidden chain-of-thought.

The experience prioritizes:

- brief clarity;
- visible workflow state;
- side-by-side comparison;
- structured review;
- clear approval ownership;
- traceable revisions;
- progressive disclosure;
- low cognitive load for non-technical stakeholders.

It should feel like a creative operating environment rather than a generic chatbot or engineering console.

## 15. Engineering architecture principles

- Contract-first interfaces.
- Independent schema versioning.
- Idempotent workflow steps.
- Immutable artifact history.
- Explicit state transitions.
- Provider abstraction.
- Secure-by-default external access.
- Observable workflow execution.
- Reproducible inputs and configuration.
- Compatibility and migration discipline.
- Documentation updated with architecture or behavior changes.

Implementation process and quality gates are owned by MEOS, not by this document.

## 16. Security principles

- Least privilege.
- Tenant and project isolation when introduced.
- Encryption in transit and at rest.
- Secrets outside source code, prompts, artifacts, logs, and fixtures.
- Auditable connector calls.
- Data-retention and classification controls.
- Explicit provider data policies.
- Role-based approval.
- Tamper-evident artifact and decision history.
- Separate research and publishing credentials.
- Acquired external content treated as untrusted input.

## 17. Stable implementation direction

Current preferred foundations are:

- React with TypeScript for human-facing applications;
- Laravel for the primary application/API backend;
- PostgreSQL for durable relational state;
- Redis for queue, cache, and ephemeral coordination;
- S3-compatible object storage;
- versioned REST initially plus asynchronous event contracts;
- containerized, environment-portable deployment.

These are architectural preferences, not evidence that implementation exists. Material changes require an ADR.

## 18. Decision discipline

An accepted ADR is required when a change materially affects:

- system boundaries or dependency direction;
- canonical terminology or artifacts;
- public, persisted, or security-sensitive contracts;
- provider/platform foundations;
- workflow or approval semantics;
- data ownership;
- difficult-to-reverse technology choices;
- reliability, privacy, cost, or operability.

## 19. Related authorities

- Product purpose and durable scope: `PROJECT_CHARTER.md`
- Complete future platform: `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- Current capability state: `docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- Expansion sequence: `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- Engineering governance: `MEOS/`
- Current delivery state: `MEOS/20_PROJECT_BOOTSTRAP.md`
- Context routing: `CONTEXT_INDEX.yaml`
- Architecture decisions: `docs/adr/`

## 20. Working instruction

Preserve this architecture and terminology. Clearly identify assumptions, proposed changes, affected contracts, and required decisions. Do not infer implementation from architecture prose. Convert accepted outcomes into repository artifacts and evidence rather than relying on chat history.
