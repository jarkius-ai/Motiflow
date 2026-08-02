# Motiflow Product Requirements Document

**Version:** 0.2
**Status:** Review-ready; human acceptance pending

## 1. Product objective

Deliver an MVP that transforms a structured or unstructured creative brief into an explainable Creative Direction Package, obtains explicit human direction approval, compiles a Generation Specification, produces candidates through one rendering provider, evaluates them, and records explicit human final approval with provenance.

Articles may be supplied as source material, but article authoring, SEO adaptation, social variants, CMS publishing, and full publication-platform behavior are outside this MVP.

The canonical decisive-slice sequence is:

`Intake Package` → `Normalized Brief` → `Knowledge Fusion Package` → `Creative Direction Package` → `Direction Approval Record` → `Generation Specification` → `Generated Candidate Set` → `Critic Evaluation Package` → `Final Approval Record` → `Provenance Record`.

## 1.1 Pre-implementation validation gate

Before implementation expands beyond schemas, fixtures, and a thin executable proof, the team must complete [`01-product/MVP_VALIDATION_PLAN.md`](01-product/MVP_VALIDATION_PLAN.md). Its evidence determines whether the workflow, artifacts, and measures are ready to build.

## 2. Primary users

The canonical persona definitions, needs, and pain points live in
[`01-product/PERSONAS.md`](01-product/PERSONAS.md). The personas most load-bearing
for this MVP are:

### Creative Lead

Needs to establish and approve the core narrative, metaphor, style, and quality threshold.

### Brand and Marketing Manager

Needs the visual output to accurately support a business message, audience, channel, and campaign objective.

### Designer or Content Producer

Needs clear, production-ready direction rather than vague prompts and repeated subjective feedback.

### Reviewer or Approver

Needs a concise explanation of why a direction was chosen, what changed, and whether it satisfies brand and strategic requirements before downstream production begins.

### Enterprise Administrator

Needs control over users, providers, connectors, policies, retention, and audit records.

## 3. MVP jobs to be done

1. Capture a brief and supporting source material.
2. Detect missing or contradictory requirements.
3. Normalize the brief into structured fields.
4. Produce narrative, audience, business, and brand analysis.
5. Fuse findings while preserving confidence and provenance.
6. Recommend a dominant metaphor and creative direction.
7. Let a human compare, revise, approve, or reject the direction.
8. Compile only the approved direction into a Generation Specification.
9. Generate a candidate set through one rendering provider.
10. Apply deterministic checks and focused critics.
11. Let a human approve, reject, select, or request revision of the final candidates.
12. Preserve both approval records, critic findings, and complete provenance.
13. Measure whether the direction was useful, understandable, and faster to approve than current practice.

## 4. MVP functional requirements

### FR-001 Project and brief management

The system shall allow a user to create a project, enter a brief, define audience and channel, attach references, and specify constraints.

### FR-002 Brief normalization

The system shall convert the submitted material into a validated Normalized Brief and surface missing information, contradictions, and assumptions.

### FR-003 Parallel intelligence analysis

The system shall run independent narrative, audience, business-context, and brand-constraint analysis concurrently where dependencies permit.

### FR-004 Knowledge fusion

The system shall produce a Knowledge Fusion Package that preserves sources, confidence, disagreements, and unresolved questions.

### FR-005 Creative direction

The system shall produce at least one structured Creative Direction Package containing:

- communication objective
- dominant narrative
- dominant metaphor
- symbolism
- visual hierarchy
- composition intent
- material and lighting language
- palette logic
- prohibited elements
- rationale and confidence

### FR-006 Human direction approval

The system shall allow authorized users to approve, reject, revise, or request alternatives before generation.

### FR-007 Generation specification

The system shall compile the approved Creative Direction Package into a provider-neutral Generation Specification and one provider-specific instruction set.

### FR-008 Rendering integration

The system shall submit the Generation Specification to one rendering provider, track status, preserve provider metadata, and store a Generated Candidate Set.

### FR-009 Critic evaluation

The system shall apply deterministic checks and focused critics to the Generated Candidate Set and produce a Critic Evaluation Package without mutating candidates.

### FR-010 Final review and approval

The system shall allow side-by-side candidate comparison, comments, selection, rejection, revision requests, and an explicit Final Approval Record.

### FR-011 Validation instrumentation

The system shall capture baseline and in-product measures for time to approved direction, direction revisions, usefulness, rationale clarity, candidate revisions, and final approval.

### FR-012 Version history

The system shall retain immutable versions of briefs, packages, both approval records, critic findings, reviewer comments, overrides, and revision requests.

### FR-013 Run visibility

The system shall show workflow stage, state, dependency, duration, failure, retry, and approval status without exposing private chain-of-thought.

## 5. Non-functional requirements

### Reliability

- Workflow steps must be idempotent where practical.
- Failed external calls must support bounded retry and clear error reporting.
- Approved package history must not be overwritten.

### Performance

- Independent analysis stages should run concurrently.
- Interactive screens should remain responsive while asynchronous work continues.
- Direction review interactions should remain responsive while background analysis completes.

### Security

- Access must be authenticated and role-based.
- Projects and artifacts must be isolated by tenant and permission.
- Secrets must not be stored in source code or visible logs.
- Connector activity must be auditable.

### Explainability

- Recommendations must include concise rationale, evidence references, confidence, and alternatives.
- The system must not present uncertain conclusions as established facts.

### Extensibility

- Rendering providers must be replaceable behind connector contracts, although the MVP implements only one real provider.
- Specialist engines must use versioned input and output schemas.
- Workflow definitions must support future stages without rewriting the entire runtime.

### Observability

- Every run must have traceable identifiers.
- Stage duration, error rate, approval latency, revision count, and quality results should be measurable.

## 6. MVP screens

1. **Project dashboard** — projects, status, pending approvals, recent artifacts
2. **Brief workspace** — input, references, constraints, detected gaps
3. **Direction workspace** — narrative, metaphor, options, rationale, approval
4. **Generation workspace** — approved direction, Generation Specification, provider status, candidates
5. **Review workspace** — side-by-side candidates, critic findings, comments, final approval
6. **Run inspector** — DAG stages, package lineage, errors, retries, timing
7. **Validation insights** — baseline measures, approval timing, revision patterns, reviewer scores
8. **Administration** — users, roles, providers, policies, retention

## 7. Initial success criteria

Pre-build validation should use 5–10 representative briefs to establish
baseline measures for the criteria below. The recorded 2026-07-26 scope
revision runs the pre-build round solo (Jarkius as sole intended user);
2–3-user or design-partner coverage is deferred to the post-build pilot. See
[`01-product/MVP_VALIDATION_PLAN.md`](01-product/MVP_VALIDATION_PLAN.md) for
the current authoritative scope.

- time to approved direction
- revision count
- direction usefulness
- rationale clarity

The detailed validation approach is defined in [`01-product/MVP_VALIDATION_PLAN.md`](01-product/MVP_VALIDATION_PLAN.md).

The MVP will be considered validated when it demonstrates:

- at least 80% of test briefs produce a complete direction without schema failure
- reviewers can trace every approved direction and final candidate to the brief and source packages
- a full brief-to-final-approved-candidate workflow completes without manual artifact transfer between stages
- time to approved direction improves against the pre-build baseline in a controlled pilot
- revision count improves against the pre-build baseline in a controlled pilot
- at least 70% reviewer agreement that the direction is useful
- at least 70% reviewer agreement that the rationale is understandable and useful
- one rendering provider can be changed behind the connector boundary without changing engine business logic
- deterministic checks, critic findings, both approvals, and overrides are auditable

These are provisional targets and should be refined after baseline measurement.

## 8. Out of scope for the first MVP

- full digital asset management
- broad project-management replacement
- autonomous public publishing
- article and newsletter authoring
- SEO adaptation and social variants
- CMS publishing
- full publication-platform behavior
- full publication-package authoring and release management
- multi-provider optimization and routing dashboards
- public SDK and connector ecosystems
- video production pipeline
- unrestricted marketplace of third-party engines
- automatic brand training from uncurated company data
- fully autonomous approval of high-risk external content

## 9. Key risks

- over-engineering before proving user value
- generating polished but strategically weak directions
- false confidence from critic scores
- excessive workflow latency
- unclear ownership between AI recommendation and human decision
- insufficient evaluation data
- brand or confidential-data leakage through external providers

## 10. Open decisions

- Authentication and tenant model for pilot
- Whether the first release supports one or multiple direction alternatives
- Minimum human approval gates for low-risk workflows
- Initial evaluation dataset and scoring calibration
- Which source-material inputs are required for the first wedge beyond briefs and references
- Pricing and packaging model
