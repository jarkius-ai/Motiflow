# Motiflow System Design

**Version:** 0.1  
**Status:** Foundation draft

## 1. Architectural approach

Motiflow uses a modular, event-driven, hybrid-DAG architecture. The system separates platform integrity, workflow coordination, specialist reasoning, external integration, and human review.

## 2. Logical components

### Motiflow Studio

React-based application for project intake, direction review, workflow visibility, candidate comparison, comments, and approval.

### Application API

Laravel-based API responsible for authentication, authorization, project operations, package access, approval commands, and client-facing orchestration requests.

### Creative Kernel

Shared runtime and policy layer responsible for:

- schema registry
- package validation
- version compatibility
- provenance rules
- confidence representation
- state-transition rules
- approval policy
- artifact immutability
- tenant and permission enforcement

### Workflow Orchestrator

Coordinates execution of workflow definitions as directed acyclic graphs. It resolves dependencies, schedules parallel work, handles retry and timeout rules, waits for approvals, and emits workflow events.

### Engine Runtime

Hosts or invokes specialist engines through a common contract. Initial engines are expected to include:

- Brief Normalizer
- Narrative Intelligence
- Audience Intelligence
- Business Context Intelligence
- Brand Constraint Intelligence
- Knowledge Fusion
- Symbol Intelligence
- Creative Director
- Visual DNA
- Prompt Compiler
- Narrative Critic
- Visual Critic
- Brand and Policy Critic

### Connector Gateway

Controls communication with:

- rendering models
- language models
- storage providers
- knowledge sources
- enterprise applications
- notification systems

The gateway owns credentials, provider-specific mapping, rate limits, request policy, and audit logging.

### Package Store

PostgreSQL stores structured metadata, package indexes, workflow state, permissions, and approval records. Large package payloads and generated assets may be stored in S3-compatible object storage with content hashes and database references.

### Queue and event infrastructure

Redis initially supports queues, locks, cache, and ephemeral coordination. The design should allow migration to a dedicated event broker when throughput or integration requirements justify it.

### Observability layer

Collects structured logs, traces, metrics, model-provider usage, workflow timing, errors, retries, and quality outcomes.

## 3. Core separation of concerns

```text
Studio/API        → user interaction and commands
Kernel            → integrity, policy, contracts, validation
Orchestrator      → sequencing, dependencies, retries, approvals
Engines           → bounded reasoning
Connector Gateway → provider and enterprise integration
Package Store     → durable state and lineage
Critics/Humans    → evaluation and accountable approval
```

No component should absorb the responsibilities of all other layers.

## 4. Reference workflow

```text
Project Created
    ↓
Brief Submitted
    ↓
Brief Normalizer
    ↓
[ Narrative | Audience | Business | Brand ]
    ↓
Knowledge Fusion
    ↓
Symbol Intelligence
    ↓
Creative Director
    ↓
Human Direction Approval
    ↓
[ Visual DNA | Composition | Provider Adaptation ]
    ↓
Prompt Compiler
    ↓
Rendering Connector
    ↓
Generated Candidates
    ↓
[ Narrative Critic | Visual Critic | Brand/Policy Critic ]
    ↓
Human Final Approval
    ↓
Approved Artifact Package
```

## 5. Package contract

Every engine receives a validated envelope and returns a new immutable package.

```json
{
  "package_id": "uuid",
  "package_type": "creative_direction",
  "schema_version": "1.0",
  "project_id": "uuid",
  "run_id": "uuid",
  "producer": {
    "engine": "creative-director",
    "version": "0.1.0",
    "model_provider": "optional",
    "model": "optional"
  },
  "source_packages": ["uuid"],
  "confidence": {
    "score": 0.82,
    "basis": "evidence-and-rule-summary",
    "uncertainties": []
  },
  "provenance": [],
  "validation": {
    "status": "valid",
    "schema": "creative-direction/1.0"
  },
  "payload": {},
  "created_at": "RFC3339 timestamp"
}
```

## 6. Workflow states

Initial run states:

- drafted
- queued
- running
- waiting_for_dependency
- waiting_for_approval
- retry_scheduled
- failed
- cancelled
- completed

Initial stage states:

- pending
- ready
- running
- succeeded
- failed
- skipped
- cancelled

State transitions must be explicit and validated by the Kernel.

## 7. Event examples

- `project.created`
- `brief.submitted`
- `package.validated`
- `stage.ready`
- `stage.started`
- `stage.completed`
- `stage.failed`
- `approval.requested`
- `approval.recorded`
- `generation.requested`
- `artifact.created`
- `run.completed`

Events should include identifiers, event version, tenant, actor or service, correlation ID, timestamp, and minimal routing data. Sensitive package content should not be duplicated into every event.

## 8. Data domains

Core database domains:

- tenants
- users and roles
- projects
- briefs and references
- workflow definitions
- workflow runs and stages
- packages and package relationships
- engine definitions and versions
- connector configurations
- generation requests and artifacts
- critic evaluations
- approvals and comments
- policies
- audit events

## 9. API direction

Initial APIs should be versioned under `/api/v1` and organized around resources and commands.

Examples:

- `POST /projects`
- `POST /projects/{id}/briefs`
- `POST /projects/{id}/runs`
- `GET /runs/{id}`
- `GET /runs/{id}/packages`
- `POST /approvals/{id}/decisions`
- `POST /runs/{id}/cancel`
- `GET /artifacts/{id}`

Long-running commands should return an accepted response with run and status references rather than holding an HTTP connection open.

## 10. Idempotency and retries

- Command endpoints that initiate work should support idempotency keys.
- Engine stages should persist their execution attempt and input package set.
- Retries must not create duplicate approved packages or generation requests.
- External provider retries must distinguish safe retries from operations that may already have completed.
- Dead-letter handling must preserve enough context for diagnosis and controlled recovery.

## 11. Confidence and conflict handling

Confidence is not a substitute for validation. The system should preserve:

- engine-reported confidence
- evidence coverage
- missing information
- disagreement between engines
- critic score variance
- human overrides

Fusion must surface material conflicts and may route the workflow to clarification or human review rather than forcing a single conclusion.

## 12. Security boundaries

- Studio clients never receive provider secrets.
- Connector credentials are scoped by tenant, environment, and provider.
- External-provider requests pass through policy and data-classification checks.
- Package access is authorized by tenant, project role, and artifact sensitivity.
- Audit records are append-oriented.
- Human overrides and approvals require authenticated identity.

## 13. Deployment direction

A practical first deployment may use:

- React application
- Laravel application and workers
- PostgreSQL
- Redis
- S3-compatible object storage
- containerized runtime
- managed observability

The first implementation may be a modular monolith with background workers. Logical boundaries should be preserved so high-load or security-sensitive components can later be extracted without redesigning product contracts.

## 14. Testing strategy

- schema contract tests
- workflow graph validation tests
- state-transition tests
- engine fixture and regression tests
- connector contract tests
- policy and authorization tests
- end-to-end reference workflow tests
- critic calibration tests
- provider failure and retry tests
- package-lineage integrity tests

## 15. Key design constraints

- Do not persist hidden chain-of-thought.
- Do persist concise rationale, evidence, assumptions, confidence, and decisions.
- Do not couple canonical packages to one model provider.
- Do not allow an engine to mutate previous packages.
- Do not let orchestration logic become embedded in UI code.
- Do not let provider-specific prompt syntax become the creative system's source of truth.

## 16. Open architecture questions

- Exact queue and event technology beyond the MVP
- Package payload storage threshold between PostgreSQL and object storage
- Workflow definition format and visual authoring requirements
- Engine isolation model
- Multi-region and data-residency requirements
- Evaluation service design and score calibration
- Approach to reusable organizational knowledge and embeddings
