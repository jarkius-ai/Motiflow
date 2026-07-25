# Motiflow Master Context

**Architecture name:** Autonomous Creative Direction System (ACDS)  
**Version:** 1.0  
**Status:** Foundational source of truth  
**Product name:** Motiflow  
**Positioning:** Creative intelligence, orchestrated.

## 1. Purpose

This document is the durable context for Motiflow. Product requirements, architecture, UX, AI-engine design, implementation plans, and future AI-assisted work must align with it unless an accepted Architecture Decision Record explicitly changes the direction.

Motiflow is not merely an image generator or prompt-writing tool. It is a governed creative-intelligence platform that converts business context, research, narrative intent, audience needs, and brand constraints into explainable visual direction and production-ready outputs.

## 2. Vision

Build the operating system for enterprise creative direction: a platform capable of understanding meaning before creating, coordinating specialist intelligence, preserving decision history, evaluating quality, and connecting to multiple rendering systems without becoming dependent on any single model.

## 3. Mission

Help teams move from fragmented briefs, inconsistent prompts, and subjective review toward a structured and repeatable creative process that is faster, more explainable, more consistent, and easier to govern.

## 4. Problem statement

Modern generative workflows often fail because they begin with rendering before establishing strategic intent. Common weaknesses include:

- incomplete or ambiguous briefs
- generic visual metaphors
- inconsistent output across teams and models
- excessive dependence on individual prompt-writing skill
- no traceable connection between business meaning and visual decisions
- weak review criteria and subjective approval cycles
- duplicated context across tools and conversations
- model lock-in
- limited governance, provenance, and auditability

Motiflow addresses these weaknesses by separating discovery, reasoning, direction, compilation, generation, and review into explicit stages with structured contracts.

## 5. Product philosophy

1. **Understand before creating.** No production prompt should be compiled before the system understands the business objective, audience, narrative, constraints, and desired outcome.
2. **Meaning drives form.** Visual style is derived from strategic meaning rather than selected as decoration.
3. **One dominant narrative.** Every artifact should communicate a clear primary idea.
4. **One dominant metaphor.** Supporting symbolism may exist, but the main visual mechanism must remain coherent.
5. **Separate reasoning from rendering.** Intelligence engines determine what should be communicated; rendering models determine how pixels are produced.
6. **Structured outputs over uncontrolled prose.** Engines exchange typed packages that can be validated, versioned, compared, and reused.
7. **Human judgment remains explicit.** Human approval is required at meaningful quality, brand, legal, or reputational gates.
8. **Model independence.** Models are replaceable providers behind stable interfaces.
9. **Explainability by design.** Major decisions must preserve rationale, evidence, confidence, provenance, and alternatives.
10. **Quality over raw generation volume.** The system optimizes for usable and defensible creative outcomes, not the number of generated variants.

## 6. System identity

- **Motiflow:** customer-facing product and platform brand
- **ACDS:** underlying autonomous creative-direction architecture
- **Creative Kernel:** integrity and governance runtime
- **Workflow Orchestrator:** execution planner and state coordinator
- **Specialist Engine:** bounded reasoning component with defined input and output contracts
- **Connector Gateway:** controlled interface to external models, knowledge sources, storage, and enterprise services
- **Motiflow Studio:** human workspace for briefs, workflow visibility, comparison, review, and approval

## 7. High-level architecture

```text
Human / API / Connector Input
            ↓
      Brief Normalization
            ↓
      Creative Kernel
            ↕
   Workflow Orchestrator
            ↓
 ┌───────────────────────────────┐
 │ Specialist Intelligence      │
 │ Narrative • Audience • Brand │
 │ Research • Business Context  │
 └───────────────────────────────┘
            ↓
       Knowledge Fusion
            ↓
 ┌───────────────────────────────┐
 │ Creative Reasoning           │
 │ Symbol • Metaphor • Direction│
 │ Composition • Visual DNA     │
 └───────────────────────────────┘
            ↓
       Prompt Compilation
            ↓
       Connector Gateway
            ↓
      Rendering Providers
            ↓
 Multi-Critic Review + Human Gate
            ↓
 Approved Artifact + Provenance
```

## 8. Creative Kernel responsibilities

The Creative Kernel protects system integrity. It owns:

- canonical schemas and package definitions
- validation and compatibility rules
- workflow and artifact state models
- confidence propagation
- provenance and evidence linkage
- policy and permission enforcement
- versioning and immutability rules
- approval requirements
- quality-gate contracts
- reproducibility metadata

The Kernel does not decide the visual idea and does not schedule tasks. It ensures that all parts of the system exchange trustworthy and governable information.

## 9. Workflow Orchestrator responsibilities

The Orchestrator coordinates work. It owns:

- DAG planning and execution
- sequential and parallel stage scheduling
- dependency resolution
- retry, timeout, fallback, and cancellation behavior
- event routing
- approval-gate pauses and resumptions
- resource and provider selection
- run-level status and observability
- handoff of validated outputs as inputs to downstream engines

The Orchestrator does not replace specialist reasoning. It invokes engines and applies workflow policies defined by the Kernel.

## 10. Hybrid execution model

Motiflow uses a hybrid directed acyclic graph rather than a fully linear chain or unrestricted parallel execution.

### Parallel discovery

Research, audience interpretation, brand constraints, business objectives, and narrative analysis may run concurrently when their inputs are independent.

### Fusion

The outputs are combined into a validated Knowledge Fusion Package. Conflicts, weak evidence, and confidence gaps are surfaced rather than silently merged.

### Sequential creative commitment

Symbolism, dominant metaphor, and core creative direction require progressively constrained decisions. These stages are predominantly sequential because each decision narrows the next design space.

### Parallel design derivation

Once a direction is accepted, composition, lighting, material language, camera logic, palette, and provider-specific adaptation may be derived in parallel.

### Compilation and review

The final direction is compiled into provider-neutral and provider-specific generation instructions. Multiple critics then evaluate narrative alignment, visual coherence, brand safety, technical quality, originality, and usability before human approval.

## 11. Canonical packages

The system should evolve around immutable, versioned packages such as:

- Intake Package
- Normalized Brief
- Research Package
- Audience Package
- Brand Constraint Package
- Narrative Package
- Knowledge Fusion Package
- Symbol Package
- Creative Direction Package
- Visual DNA Package
- Composition Package
- Generation Specification
- Critic Evaluation Package
- Approval Record
- Artifact Package
- Change Set

Every package should include at minimum:

- unique identifier
- schema version
- project and run identifiers
- creation timestamp
- producing engine and engine version
- source package references
- confidence and uncertainty
- provenance or evidence references
- validation status
- human overrides, when present

## 12. Quality model

Quality must be measured through explicit dimensions rather than one opaque score. Initial dimensions include:

- strategic alignment
- narrative clarity
- metaphor strength
- audience relevance
- brand alignment
- visual hierarchy
- composition quality
- technical render quality
- originality and non-generic character
- accessibility and legibility where text is used
- policy and safety compliance
- production usability

A composite score may support prioritization, but it must not hide dimension-level failures.

## 13. Human approval gates

Human approval should be configurable but mandatory for:

- final creative-direction commitment in enterprise workflows
- brand exceptions
- legal, regulatory, or reputational risk
- external publication
- low-confidence recommendations
- conflicting critic results
- material changes after approval

Every approval or override must be recorded with actor, timestamp, rationale, and affected package version.

## 14. UX philosophy

Motiflow Studio should make the reasoning process understandable without exposing uncontrolled chain-of-thought. It should show concise rationale, evidence, alternatives, confidence, decisions, dependencies, and change impact.

The interface should prioritize:

- brief clarity
- visible workflow status
- side-by-side options
- structured review
- clear approval ownership
- traceable revisions
- progressive disclosure of technical detail
- low cognitive load for non-technical creative stakeholders

The UI should feel like a creative operating environment, not a generic chatbot or engineering dashboard.

## 15. Engineering principles

- Contract-first interfaces
- Schema versioning
- Idempotent workflow steps
- Immutable package history
- Event-driven integration
- Explicit state transitions
- Model-provider abstraction
- Secure-by-default connector access
- Observability across every run
- Automated tests for schemas, workflows, engines, and policies
- Reproducible inputs and configuration
- Backward compatibility unless an ADR approves a breaking change
- Documentation updated in the same change as architecture or behavior

## 16. Initial technology direction

The current preferred implementation direction is:

- **Frontend:** React with TypeScript
- **Backend:** Laravel
- **Primary database:** PostgreSQL
- **Cache, queue, and ephemeral coordination:** Redis
- **Object storage:** S3-compatible storage
- **Workflow architecture:** event-driven hybrid DAG
- **API style:** versioned REST initially, with event contracts for asynchronous work
- **Identity:** enterprise-ready authentication and role-based access control
- **Deployment:** containerized services with environment-portable infrastructure

These are preferred foundations, not irreversible commitments. Material changes require an ADR.

## 17. Security and governance principles

- Least-privilege access
- Tenant and project isolation
- Encryption in transit and at rest
- Secret management outside source code
- Auditable connector calls
- Data-retention controls
- Explicit model-provider data policies
- PII and confidential-information classification
- Role-based approvals
- Tamper-evident artifact and decision history
- Configurable regional and enterprise compliance controls

## 18. Repository strategy

The repository is the durable source of truth. Chat conversations may accelerate work, but accepted knowledge must be committed into version-controlled documents, schemas, tests, or ADRs.

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

Empty folders should be introduced only when implementation starts or through placeholder files with a documented purpose.

## 19. Success definition

Motiflow succeeds when teams can reliably:

- convert an ambiguous brief into a validated creative direction
- understand why the direction was recommended
- generate consistent results across multiple rendering providers
- reduce avoidable revision cycles
- reuse approved knowledge and visual language
- measure quality and workflow performance
- preserve governance, provenance, and approval history
- replace or add models without redesigning the product

## 20. Initial product boundary

The first release should focus on editorial and enterprise visual-direction workflows. It should not attempt to replace every creative application, digital asset management platform, or project-management tool.

The MVP should prove the complete reasoning-to-approval loop with a limited number of engines and rendering providers before broadening scope.

## 21. Decision discipline

Any significant change to architecture, core terminology, canonical packages, security boundaries, data ownership, workflow semantics, or technology foundations must be captured as an ADR containing:

- context
- decision
- alternatives considered
- consequences
- status
- date
- related documents

## 22. Near-term priorities

1. Stabilize the master context and vocabulary
2. Define MVP personas, jobs, scope, and measurable success criteria
3. Finalize canonical package schemas
4. Specify the Creative Kernel and Orchestrator contracts
5. Define the first end-to-end reference workflow
6. Design Motiflow Studio around that workflow
7. Implement one vertical slice with real provider integration
8. Add critic evaluation and approval history
9. Establish observability and evaluation datasets
10. Iterate from measured outcomes rather than feature volume

## 23. Working instruction for future AI-assisted sessions

Use this document as the authoritative project context. Preserve established terminology and architecture. Clearly identify assumptions, proposed changes, unresolved decisions, and affected documents. Do not silently introduce breaking changes. Convert accepted outcomes into repository artifacts rather than relying on conversation history.
