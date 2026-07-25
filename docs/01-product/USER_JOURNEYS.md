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
6. The system ranks direction candidates using constraints and evidence.
7. Motiflow creates a versioned Creative Direction Package.
8. An authorized human approves it, producing a Direction Approval Record, or requests revision.

## Journey B: Direction to generated assets

1. User selects an approved Creative Direction Package.
2. The system creates a Generation Specification tied to the approved direction version.
3. The MVP sends the specification to one rendering provider and receives a Generated Candidate Set.
4. Outputs are checked for technical and policy constraints.
5. Focused critics produce a Critic Evaluation Package.
6. Low-confidence or failed outputs are retried within configured limits.
7. An authorized human compares candidates, annotates, and records final approval or requests revision.
8. The Final Approval Record and Provenance Record are stored with the approved candidate set.

## Journey C: Review and revision

1. Reviewer opens a decision-centric comparison view.
2. Motiflow shows the direction, evidence, constraints, generation provenance, and critic findings.
3. Reviewer gives structured feedback or directly edits selected fields.
4. The orchestrator determines which downstream nodes are invalidated.
5. Only affected stages rerun.
6. The new version is linked to its parent and previous decisions remain available.

## Journey D: Build a reusable workflow after MVP proof

1. Administrator or developer chooses engines from the catalog.
2. They connect nodes into a DAG with declared artifact contracts.
3. They configure policies, retries, timeouts, costs, and approval gates.
4. Validation checks compatibility before publication.
5. The workflow is versioned, tested against fixtures, and published to a workspace.
6. Runtime telemetry feeds reliability and quality dashboards.
