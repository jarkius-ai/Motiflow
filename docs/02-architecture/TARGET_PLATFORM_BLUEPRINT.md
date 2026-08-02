# Motiflow Target Platform Blueprint

- **Status:** Accepted target-state direction
- **Owner:** Chief Architect
- **Product:** Motiflow
- **Product architecture:** Autonomous Creative Direction System (ACDS)
- **Engineering governance:** Motiflow Engineering Operating System (MEOS)
- **Responsibility:** Describe the complete future platform, architectural boundaries, capability domains, and stable expansion seams
- **Does not own:** Current implementation state, delivery phases, task readiness, provider selection, test plans, CI details, or release authorization

## 1. Role of this blueprint

This blueprint answers one question:

> When Motiflow matures beyond its first validated product slice, what complete platform should it be able to become without abandoning its core architecture?

It is the repository's **destination architecture**. It preserves long-term product coherence while allowing implementation to proceed incrementally.

This document does not authorize work. Future capability state is recorded in `TARGET_PLATFORM_CAPABILITY_MAP.md`; activation order is owned by `CAPABILITY_EXPANSION_ROADMAP.md`; implementation is authorized only by ready MEOS tasks and accepted decisions.

## 2. Authority boundary

When documents overlap, apply this responsibility model:

| Concern | Canonical owner |
|---|---|
| Product purpose, value, and durable scope | `PROJECT_CHARTER.md` |
| Stable product/runtime architecture and terminology | `MASTER_CONTEXT.md` |
| Future complete capability destination | This blueprint |
| Current capability state | `TARGET_PLATFORM_CAPABILITY_MAP.md` |
| Expansion order and activation gates | `CAPABILITY_EXPANSION_ROADMAP.md` |
| Consequential architecture decisions | Accepted ADRs |
| Engineering execution, readiness, review, and release | MEOS |
| Today's authorized work | Ready task specifications |
| What is actually true | Repository implementation and verification evidence |

The blueprint must never silently override the Charter, Master Context, accepted ADRs, canonical contracts, or protected human authority.

## 3. Product destination

Motiflow is intended to become an operating system for governed enterprise creative intelligence.

The complete platform connects:

```text
Business intent and source material
        ↓
Knowledge acquisition and normalization
        ↓
Creative intelligence and knowledge fusion
        ↓
Explainable creative direction
        ↓
Human direction approval
        ↓
Provider-neutral generation specification
        ↓
Generation and candidate normalization
        ↓
Deterministic and critic evaluation
        ↓
Human final approval and provenance
        ↓
Editorial and Publication Package assembly
        ↓
Explicit publishing authorization
        ↓
Channel execution and published-state evidence
        ↓
Measurement, governed learning, and reusable knowledge
```

Not every workflow must use every capability. Each workflow declares the minimum capabilities, contracts, policies, approval gates, and evidence required for its product outcome.

## 4. Architectural model

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

Cross-cutting roots:
Schemas • Workflows • Policy • Provenance • Evidence • Security
Observability • Versioning • Evaluation • Human Authority • Memory
```

## 5. Stable component responsibilities

### 5.1 Motiflow Studio and API

Own human and system-facing interaction:

- project and brief intake;
- workflow visibility;
- artifact comparison;
- clarification;
- review and approval;
- package preview and export;
- current-state read models.

They must not call provider SDKs directly or mutate canonical artifact state outside application services and Kernel contracts.

### 5.2 Creative Kernel

Owns integrity and governance:

- canonical artifact and package contracts;
- schema validation and compatibility;
- immutable versioning and lineage;
- policy and permission enforcement;
- approval requirements;
- provenance and evidence linkage;
- protected state transitions;
- invalidation rules.

The Kernel does not perform specialist creative reasoning, choose providers, schedule workflows, or publish externally.

### 5.3 Workflow Orchestrator

Owns execution coordination:

- workflow DAGs;
- dependency resolution;
- scheduling and concurrency;
- retries, timeouts, cancellation, and safe resume;
- budget and resource controls;
- approval pauses;
- capability resolution;
- run-level observability.

The Orchestrator does not own canonical contracts, creative reasoning, provider implementations, or human authority.

### 5.4 Specialist engines and critics

Engines perform bounded reasoning and transformation through typed contracts. Critics produce findings, evidence, and recommendations without silently rewriting reviewed artifacts.

Engines and critics must not:

- import provider SDKs directly;
- mutate another component's owned output;
- bypass Kernel validation;
- advance workflow state directly;
- authorize external publication.

### 5.5 Connector Gateway

Owns the controlled boundary to external systems:

- provider-specific adapters;
- credentials and permissions;
- request/result normalization;
- external-call policy;
- retries and provider diagnostics;
- audit and usage evidence;
- platform-specific payloads.

Provider-native types, browser selectors, cookies, account identifiers, and authentication mechanisms remain inside connector implementations.

### 5.6 Model Gateway

Provides provider-neutral model execution for reasoning and generation. It owns capability descriptions, normalized request/result contracts, and model/provider execution evidence.

It remains replaceable and must not become the owner of workflow state or business artifacts.

### 5.7 Human authority

Human decisions are explicit versioned records. The creative core protects two gates:

1. Direction approval before generation.
2. Final approval after candidate evaluation and before export or publication.

External publication requires a distinct publishing authorization. Creative approval is not automatically permission to post.

## 6. Canonical creative spine

The first durable platform spine remains:

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

Every future domain must extend this spine through versioned references or approved supporting contracts. No later capability may create a second artifact envelope, approval model, provenance system, or workflow-state owner.

## 7. Target capability domains

### 7.1 Intake and workspace

- Project and brief management.
- Source and reference attachment.
- Audience, brand, objective, channel, and constraint capture.
- Clarification and decision history.
- Artifact, workflow, approval, and lineage visibility.

### 7.2 Creative intelligence

- Brief normalization.
- Narrative and audience analysis.
- Business-context interpretation.
- Brand and policy constraints.
- Research synthesis.
- Knowledge fusion that preserves conflict, uncertainty, and confidence.

### 7.3 Creative direction

- Dominant narrative and metaphor.
- Symbolism and visual language.
- Composition, camera, lighting, material, and palette logic.
- Prohibited elements and brand-safety rules.
- Alternatives, rationale, and confidence.

### 7.4 Generation

- Provider-neutral Generation Specification.
- Replaceable rendering providers.
- Candidate normalization.
- Cost, latency, model, configuration, and version provenance.
- Deterministic mock execution for verification.

### 7.5 Evaluation and approval

- Deterministic checks.
- Focused critics.
- Dimension-level findings.
- Revision routing and invalidation.
- Direction and final approval records.
- Complete provenance closure.

### 7.6 Knowledge acquisition

- Public web, video transcript, repository, and feed acquisition.
- Search and source discovery.
- Normalized Source Records and Source Bundles.
- Citations, source hashes, rights, classification, and retrieval evidence.
- Provider health and diagnostics.
- Authenticated paths only under separately accepted security and policy controls.

### 7.7 Editorial intelligence

- Research briefs.
- Claim extraction and evidence mapping.
- Editorial drafting and revision.
- Factual, brand, policy, and accessibility review.
- Channel variants derived from approved source and package versions.

### 7.8 Publication Package

- Approved content body.
- Markdown and sanitized HTML.
- Selected visual artifacts and crops.
- Captions, alt text, credits, and accessibility metadata.
- Claim-to-source links and citations.
- Editorial, factual, visual, brand, and approval state.
- Reproducible export manifest.

### 7.9 Publishing execution

- Official API connectors where suitable.
- Approved normalized platform adapters.
- Browser execution only as a replaceable, policy-approved provider.
- Preview, dry-run, and explicit authorization.
- Idempotency, target-account verification, and published-state evidence.

### 7.10 Measurement and governed learning

- Workflow and approval latency.
- Revision, critic, and quality analytics.
- Source-quality and factual-accuracy signals.
- Provider cost, latency, and reliability.
- Publication outcome ingestion.
- Evidence-backed learning proposals.
- Human-approved updates to reusable brand, knowledge, creative, and evaluation memory.

### 7.11 Enterprise and ecosystem

- Tenant and project isolation.
- Enterprise identity and delegated approval.
- Regional and provider data controls.
- Engine and connector SDKs.
- Multi-provider routing and resilience.
- Governed extensibility and marketplace capabilities after trust and demand are proven.

## 8. Stable expansion seams

The following interfaces are the architectural jigsaw joints:

```text
Canonical Artifact Envelope
Workflow Definition Contract
Specialist Engine Contract
Critic Contract
Artifact Repository Contract
Approval Record Contract
Provenance and Evidence Contract
Connector Request and Result Contract
Model Gateway Contract
Knowledge Acquisition Contract
Publication Package Contract
Publishing Connector Contract
Measurement Event Contract
Learning Proposal Contract
```

Each seam is independently versioned. Later capabilities may add implementations behind a seam but must not bypass or silently reinterpret it.

## 9. External provider neutrality

The blueprint names capability classes, not mandatory vendors.

### Acquisition provider examples

A future `KnowledgeAcquisitionProvider` may be implemented by:

- manual or uploaded-source ingestion;
- direct official APIs;
- public reader services;
- Agent Reach as an optional adapter;
- an approved browser source provider;
- another compliant provider.

Agent Reach is not part of the core architecture and does not own Motiflow contracts, state, policy, credentials, provenance, or approval.

### Browser provider examples

A future browser execution seam may be implemented by:

- an extension bridge;
- CDP or Playwright;
- a bounded semantic browser provider;
- another policy-approved implementation.

Browser automation is not assumed to exist. It must remain replaceable and independently verifiable.

### Proxy status

Proxy infrastructure is not a platform requirement. It may not be used to evade platform controls or silently escalate access. Any legitimate future need requires a dedicated decision, security/legal review, accepted policy, and a ready task.

## 10. Data and ownership rules

- Canonical artifacts are immutable and versioned.
- Components exchange identifiers and typed packages rather than shared mutable domain objects.
- Events describe completed facts; commands request work.
- External provider data is normalized before entering canonical workflows.
- Source and provider evidence remains traceable to the artifact versions it influenced.
- Human edits, overrides, and approvals create durable provenance.
- Provider credentials and raw authentication material never enter prompts or canonical artifacts.

## 11. Security and trust boundaries

- Least privilege and explicit data classification.
- Secrets outside prompts, artifacts, logs, fixtures, screenshots, and source control.
- Separate research and publishing credentials.
- Acquired content treated as untrusted input.
- Prompt-injection and content-safety controls at acquisition boundaries.
- Explicit authorization before authenticated access, browser sessions, external writes, or publication.
- Provider, model, tool, source, version, policy, and decision evidence retained according to policy.
- No claims of compliance, invisibility, or platform safety without evidence.

## 12. Architectural constraints

The mature platform must preserve:

- model and provider replaceability;
- one canonical artifact and provenance model;
- explicit human authority;
- provider isolation behind gateways;
- versioned contracts and compatibility rules;
- evidence-backed state claims;
- independent evaluation and review;
- bounded failure and safe-stop behavior;
- the ability to expand without rewriting the validated creative core.

## 13. Explicit non-responsibilities

This blueprint does not define:

- current implementation status;
- phase dates or sprint commitments;
- task specifications;
- Definition of Ready or Done;
- CI workflows or command names;
- exact test cases;
- repository file manifests;
- provider selection or installation;
- release authorization;
- acceptance evidence.

Those concerns are retained in their canonical owners and linked below.

## 14. Related authorities

- Product purpose: `../../PROJECT_CHARTER.md`
- Stable architecture: `../../MASTER_CONTEXT.md`
- Current capability state: `TARGET_PLATFORM_CAPABILITY_MAP.md`
- Expansion sequencing: `../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- Reconciliation decisions: `../03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`
- Architecture decision: `../adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`
- Context routing: `../../CONTEXT_INDEX.yaml`
- Current delivery state: `../../MEOS/20_PROJECT_BOOTSTRAP.md`
- Engineering governance: `../../MEOS/`

## 15. Success definition

The blueprint succeeds when Motiflow can expand from one validated creative-direction product into a governed research, creation, publication, and learning platform without discarding its core contracts, compromising human authority, duplicating architecture ownership, or rebuilding around one provider.
