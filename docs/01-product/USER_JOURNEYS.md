# Core User Journeys

**Status:** Supporting product specification
**Owner:** Product and Design
**Scope:** Core Motiflow user flows from brief through approval

## Journey A: Brief to approved creative direction

1. User creates a project and submits a business brief.
2. Motiflow validates required context and identifies missing information.
3. Research, audience, brand, and narrative engines run where appropriate.
4. The Knowledge Fusion stage produces a grounded strategic summary.
5. Direction engines propose narrative and metaphor candidates.
6. The system ranks candidates using constraints, evidence, and critic feedback.
7. A human approves or edits the selected direction.
8. Motiflow creates a versioned Creative Direction Package.

## Journey B: Direction to generated assets

1. User selects an approved Creative Direction Package.
2. Prompt Compiler converts the package into provider-specific generation requests.
3. Generation jobs run in parallel across selected formats or providers.
4. Outputs are checked for technical and policy constraints.
5. Visual, brand, and business critics produce evaluation reports.
6. Low-confidence or failed outputs are retried within configured limits.
7. Human reviewers compare candidates, annotate, approve, or request revision.
8. Approved assets and provenance are stored in the project history.

## Journey C: Review and revision

1. Reviewer opens a decision-centric comparison view.
2. Motiflow shows the direction, evidence, constraints, generation provenance, and critic findings.
3. Reviewer gives structured feedback or directly edits selected fields.
4. The orchestrator determines which downstream nodes are invalidated.
5. Only affected stages rerun.
6. The new version is linked to its parent and previous decisions remain available.

## Journey D: Build a reusable workflow

1. Administrator or developer chooses engines from the catalog.
2. They connect nodes into a DAG with declared artifact contracts.
3. They configure policies, retries, timeouts, costs, and approval gates.
4. Validation checks compatibility before publication.
5. The workflow is versioned, tested against fixtures, and published to a workspace.
6. Runtime telemetry feeds reliability and quality dashboards.
