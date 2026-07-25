# Motiflow Roadmap

**Status:** Review-ready planning baseline; human acceptance pending

## Phase 0 — Foundation

**Goal:** Establish one coherent source of truth before implementation.

Deliverables:

- product name and positioning
- Master Context v1.0
- Vision
- initial PRD
- initial System Design
- ADR process
- canonical vocabulary
- repository conventions

Exit criteria:

- architecture layers have clear responsibilities
- MVP boundary is documented
- open decisions are visible
- future discussions can begin from repository documents rather than chat history

## Phase 1 — Workflow validation and baseline

**Goal:** Test the creative-direction workflow before broad implementation.

Deliverables:

- 5–10 representative briefs or source articles;
- 2–3 intended users or design partners;
- manual execution of the proposed two-gate creative-direction and candidate-review workflow;
- baseline for time to approved direction and revision count;
- baseline for direction usefulness and rationale clarity;
- candidate revision and final-approval observations;
- documented proceed, revise, or stop decision.

Exit criteria:

- [`01-product/MVP_VALIDATION_PLAN.md`](01-product/MVP_VALIDATION_PLAN.md) is complete;
- baseline measures are recorded for time to approved direction, revision count, direction usefulness, and rationale clarity;
- product scope and vocabulary conflicts are resolved;
- participants can distinguish direction approval from final-candidate approval;
- the accountable product owner authorizes the full decisive slice;
- rejected assumptions and deferred capabilities are recorded.

## Phase 2 — Decisive-slice contracts

**Goal:** Make only the validated brief-to-final-approved-candidate slice executable.

Deliverables:

- canonical artifact vocabulary and JSON Schemas;
- two-gate workflow state machine;
- one executable workflow definition;
- deterministic fixtures and validation command;
- minimal engine and connector interfaces;
- Direction Approval Record and Final Approval Record;
- deterministic and focused critic rubric.

Exit criteria:

- every decisive-slice stage has typed inputs and outputs;
- the workflow validates without external providers;
- direction and final-candidate approval requirements are distinct and testable;
- package lineage and provenance are testable.

## Phase 3 — Executable workflow proof

**Goal:** Prove the complete workflow shape with deterministic fixtures before external-provider or platform work.

Deliverables:

- minimal Creative Kernel validation boundary;
- one executable workflow spanning all ten canonical artifacts;
- a narrow connector port with deterministic mock behavior;
- both approval gates and downstream invalidation behavior;
- retained provenance, failure, and supersession records.

Exit criteria:

- the full reference workflow executes deterministically without external providers;
- generation cannot begin without a current Direction Approval Record;
- export cannot begin without a current Final Approval Record;
- invalid fixtures prove that schema, gate, and lineage violations fail safely.

## Phase 4 — One-provider decisive-slice MVP

**Goal:** Implement and test the full creative-direction-to-approved-candidate loop as one vertical product slice.

Deliverables:

- minimal project and brief persistence;
- Brief Normalizer, focused analysis, and Knowledge Fusion;
- Creative Direction Package plus direction comparison and approval;
- Generation Specification;
- thin Model Gateway interface and deterministic mock;
- one real rendering-provider adapter;
- Generated Candidate Set;
- deterministic checks and focused critics;
- side-by-side candidate review;
- Final Approval Record and Provenance Record.

Exit criteria:

- representative inputs produce schema-valid artifacts through the full decisive slice;
- confidence, assumptions, evidence, conflicts, and lineage are visible;
- the approved direction version is pinned to generation;
- no engine imports a provider SDK directly;
- deterministic checks, critic findings, revisions, both approvals, and provenance are auditable;
- the workflow ends at an approved export rather than autonomous publication.

## Phase 5 — Controlled pilot and measurement

**Goal:** Confirm repeatable value before platform expansion.

Deliverables:

- expanded controlled pilot;
- comparison against the pre-build baseline;
- reviewer usefulness and rationale-clarity surveys;
- workflow latency and cost analysis;
- failure taxonomy;
- prioritized product-learning backlog.

Exit criteria:

- measurable evidence supports or rejects the MVP hypotheses;
- the team knows which stages create value and friction;
- success criteria are recalibrated using real data;
- platform investment is justified by observed workflow demand.

## Phase 6 — Enterprise hardening

**Goal:** Make the platform suitable for broader enterprise adoption.

Potential deliverables:

- SSO and enterprise identity
- advanced tenant administration
- retention and regional controls
- expanded policy engine
- additional rendering and knowledge connectors
- reusable brand and visual-DNA libraries
- workflow templates
- cost controls and provider routing
- export and integration APIs
- disaster recovery and operational runbooks

## Phase 7 — Platform ecosystem

**Goal:** Allow controlled extensibility without compromising system integrity.

Potential deliverables:

- engine SDK
- connector SDK
- workflow authoring tools
- evaluation extension points
- partner and enterprise integration framework
- governed organization-specific engines

## Phase 8 — Publication specialization

**Goal:** Add editorial and publishing behavior only after the creative workflow demonstrates demand.

Potential deliverables:

- article and newsletter authoring;
- SEO and social-content variants;
- Publication Package composition;
- CMS and publishing-destination connectors;
- publication analytics and editorial memory.

## Planning rule

Each phase should deliver a demonstrable vertical capability and measurable learning. Feature expansion must not outrun schema stability, evaluation quality, security, or evidence of user value.

Article authoring, SEO, social-content production, CMS publishing, multi-provider optimization, broad dashboards, and SDK ecosystems remain deferred until the creative-direction workflow demonstrates value.
