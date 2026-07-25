# Motiflow Product Requirements Document

**Version:** 0.1  
**Status:** Foundation draft

## 1. Product objective

Deliver an MVP that transforms a structured or unstructured creative brief into an explainable creative direction, a production-ready generation specification, evaluated visual outputs, and a recorded human approval decision.

## 2. Primary users

### Creative lead

Needs to establish and approve the core narrative, metaphor, style, and quality threshold.

### Content or marketing lead

Needs the visual output to accurately support a business message, audience, channel, and campaign objective.

### Designer or producer

Needs clear, production-ready direction rather than vague prompts and repeated subjective feedback.

### Reviewer or approver

Needs a concise explanation of why a direction was chosen, what changed, and whether it satisfies brand and publication requirements.

### Platform administrator

Needs control over users, providers, connectors, policies, retention, and audit records.

## 3. MVP jobs to be done

1. Capture a brief and supporting source material.
2. Detect missing or contradictory requirements.
3. Normalize the brief into structured fields.
4. Produce narrative, audience, business, and brand analysis.
5. Fuse findings while preserving confidence and provenance.
6. Recommend a dominant metaphor and creative direction.
7. Let a human compare, revise, approve, or reject the direction.
8. Compile the approved direction into a generation specification.
9. Send the specification to at least one rendering provider.
10. Evaluate generated candidates with multiple quality dimensions.
11. Let a human select and approve a final artifact.
12. Preserve the complete package and decision history.

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

The system shall compile the approved direction into a provider-neutral specification and one provider-specific instruction set.

### FR-008 Rendering integration

The system shall submit generation requests, track status, store outputs, and preserve provider and configuration metadata.

### FR-009 Critic evaluation

The system shall evaluate each candidate across strategic alignment, narrative clarity, metaphor strength, composition, technical quality, originality, brand alignment, and policy compliance.

### FR-010 Final review and approval

The system shall allow side-by-side candidate comparison, reviewer comments, selection, approval, and revision requests.

### FR-011 Version history

The system shall retain immutable versions of packages, artifacts, approvals, overrides, and changes.

### FR-012 Run visibility

The system shall show workflow stage, state, dependency, duration, failure, retry, and approval status without exposing private chain-of-thought.

## 5. Non-functional requirements

### Reliability

- Workflow steps must be idempotent where practical.
- Failed external calls must support bounded retry and clear error reporting.
- Approved package history must not be overwritten.

### Performance

- Independent analysis stages should run concurrently.
- Interactive screens should remain responsive while asynchronous work continues.
- Long-running generation should expose progress and status.

### Security

- Access must be authenticated and role-based.
- Projects and artifacts must be isolated by tenant and permission.
- Secrets must not be stored in source code or visible logs.
- Connector activity must be auditable.

### Explainability

- Recommendations must include concise rationale, evidence references, confidence, and alternatives.
- The system must not present uncertain conclusions as established facts.

### Extensibility

- Rendering providers must be replaceable behind connector contracts.
- Specialist engines must use versioned input and output schemas.
- Workflow definitions must support future stages without rewriting the entire runtime.

### Observability

- Every run must have traceable identifiers.
- Stage duration, error rate, provider use, token or compute use, approval latency, and quality results should be measurable.

## 6. MVP screens

1. **Project dashboard** — projects, status, pending approvals, recent artifacts
2. **Brief workspace** — input, references, constraints, detected gaps
3. **Direction workspace** — narrative, metaphor, options, rationale, approval
4. **Generation workspace** — compiled specification, provider status, candidates
5. **Review workspace** — side-by-side comparison, critic dimensions, comments, final approval
6. **Run inspector** — DAG stages, package lineage, errors, retries, timing
7. **Administration** — users, roles, providers, policies, retention

## 7. Initial success criteria

The MVP will be considered validated when it demonstrates:

- at least 80% of test briefs produce a complete direction without schema failure
- reviewers can trace every final direction to its brief and source packages
- a full brief-to-approved-artifact workflow completes without manual data transfer between tools
- at least 30% reduction in revision cycles versus the team's prior baseline in a controlled pilot
- at least 70% reviewer agreement that the rationale is understandable and useful
- rendering providers can be changed without modifying creative-engine business logic
- all approvals and overrides are auditable

These are provisional targets and should be refined after baseline measurement.

## 8. Out of scope for the first MVP

- full digital asset management
- broad project-management replacement
- autonomous public publishing
- video production pipeline
- unrestricted marketplace of third-party engines
- automatic brand training from uncurated company data
- fully autonomous approval of high-risk external content

## 9. Key risks

- over-engineering before proving user value
- generating polished but strategically weak directions
- false confidence from critic scores
- excessive workflow latency
- model-provider inconsistency
- unclear ownership between AI recommendation and human decision
- insufficient evaluation data
- brand or confidential-data leakage through external providers

## 10. Open decisions

- Exact first rendering provider
- Authentication and tenant model for pilot
- Whether the first release supports one or multiple direction alternatives
- Minimum human approval gates for low-risk workflows
- Initial evaluation dataset and scoring calibration
- Pricing and packaging model
