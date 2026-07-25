# AI Execution Implementation Plan

**Status:** Review-ready implementation planning artifact
**Owner:** Delivery and Chief Architect
**Scope:** Sequenced implementation of the first creative-direction execution slice

This plan is a review-ready delivery proposal. It must not be treated as a human-accepted architecture decision unless it is explicitly approved and promoted through the repository's governing process.

## Objective

Implement the narrowest executable path that proves Motiflow can move from a brief or source article through grounded creative direction, direction approval, generated candidates, critic review, final human approval, and provenance.

## Required sequence

Deliver:

### 1. Manual validation baseline

Deliver:

- a manually executable creative-direction validation path;
- representative source inputs and expected review criteria;
- clear evidence for what counts as review-ready direction before generation;
- the product-owned `docs/01-product/MVP_VALIDATION_PLAN.md` as the validation protocol.

Exit criteria:

- humans can run the slice manually without hidden workflow assumptions;
- expected approval signals and rejection reasons are explicit;
- the first automation work has a stable target to preserve.

### 2. Two-gate workflow correction

Deliver:

- Gate 1: authorized human direction approval before generation;
- Gate 2: final human approval after generated candidates and critics complete;
- workflow states and transition rules that preserve both gates;
- provenance rules for decisions, rejections, and superseded candidates.

Exit criteria:

- generation cannot proceed without an authorized Direction Approval Record for the current direction version;
- final approval cannot be implied by intermediate success;
- rejected or superseded paths remain traceable.

### 3. Canonical schemas, fixtures, and validation command

Deliver:

- canonical schemas for all ten decisive-slice artifacts, from Intake Package through Provenance Record;
- deterministic fixtures that exercise happy-path and invalid-path behavior;
- one canonical repository validation command that proves the slice contracts end to end;
- schema and semantic validation rules for the first slice.

Exit criteria:

- invalid or incomplete artifacts fail before workflow execution continues;
- fixtures protect the intended slice behavior from drift;
- the validation command is the default proof for the slice contracts.

### 4. One executable workflow

Deliver:

- one workflow that runs the validated slice from Intake Package through both approval gates and Provenance Record;
- workflow-local provenance and audit records;
- execution hooks that use the canonical schemas and fixtures rather than ad hoc payloads.

Exit criteria:

- the workflow can run deterministically in test mode;
- its stage boundaries match the two-gate design;
- the workflow is simpler to reason about than any broader infrastructure alternative.

### 5. Thin Model Gateway

Deliver:

- a provider-neutral interface that the first workflow can call;
- deterministic mock execution for tests and fixture runs;
- one real provider integration;
- request, response, error, usage, and trace types required by the first slice only.

Exit criteria:

- workflow code does not import provider SDKs directly;
- mock execution produces repeatable outputs for fixtures;
- one real provider path works without requiring routing breadth or a provider mesh.

### 6. Generated candidates, critics, and final approval

Deliver:

- generation of the first candidate set from an approved direction;
- critic passes required by the first slice;
- final approval capture with retained rationale and provenance;
- stored records of superseded and rejected candidates.

Exit criteria:

- a reviewer can inspect candidates, critic findings, and the final decision in one coherent path;
- the slice proves Motiflow's value before multi-provider or platform breadth is added;
- final approval evidence is durable and queryable.

## Proposed canonical package alignment

```text
packages/
  schemas/
    intake/
    brief/
    knowledge-fusion/
    creative-direction/
    generation/
    critics/
    approvals/
    provenance/
  workflows/
    creative-direction-slice/
  connectors/
    model-gateway/
      mock/
      provider-1/
  critics/
    creative-direction/
    generated-candidate/
  shared/
    validation/
    provenance/
```

Do not introduce a `packages/ai/` subtree. Use the canonical top-level package boundaries from `docs/00-foundation/REPOSITORY_STRUCTURE.md`.

## Explicit deferrals

- multi-provider routing and provider-mesh orchestration;
- fallback mesh and resilience breadth beyond the first provider path;
- dashboards for cost, token, latency, or validation analytics;
- CMS or social publishing connectors;
- SDK ecosystem expansion;
- editorial authoring automation beyond what the first slice strictly requires.

## Security and operational requirements

- API keys are provided through secret management and never stored in governed artifacts.
- Restricted content is routed only to approved providers.
- Logs must redact source content where policy requires it.
- Export remains human-gated through the Final Approval Record.
- All external calls are idempotency-aware and traceable.
- Physical deletion requires a separate policy-authorized process.

## Definition of done

This slice is complete when a representative Intake Package can run through one executable workflow using canonical schemas, deterministic fixtures, the thin Model Gateway, critics, and one real provider path, ending in recorded final human approval with complete provenance and no direct provider dependency inside workflow code.
