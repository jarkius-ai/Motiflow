# Motiflow Runtime Contracts

**Status:** Review-ready architecture contract v0.1
**Owner:** Chief Architect
**Applies to:** Creative Kernel, Workflow Orchestrator, engines, agents, critics, connectors, and applications

## Contract principles

- Structured JSON or YAML handoffs only across runtime boundaries.
- Every contract is versioned.
- Artifacts are immutable; revisions create new versions.
- Engines update only their owned output section.
- The Kernel validates artifacts and state transitions.
- The Orchestrator coordinates execution but does not perform specialist reasoning.
- External providers are accessed only through the Connector Gateway.
- Human approvals are explicit records and state transitions.
- The decisive slice exposes exactly two human gates: direction approval and final approval.

## Canonical decisive-slice vocabulary

Runtime contracts use these canonical artifact names for the decisive workflow slice:

- Intake Package
- Normalized Brief
- Knowledge Fusion Package
- Creative Direction Package
- Direction Approval Record
- Generation Specification
- Generated Candidate Set
- Critic Evaluation Package
- Final Approval Record
- Provenance Record

Legacy aliases remain readable for migration purposes only. In particular, `StrategicContext` maps to `Knowledge Fusion Package`, `PromptPackage` maps to `Generation Specification`, and generic approval records must be specialized as either `Direction Approval Record` or `Final Approval Record`.

## Canonical artifact envelope

```yaml
artifact:
  id: art_<uuid>
  type: creative_direction_package
  schema_version: 1.0.0
  artifact_version: 1
  project_id: prj_<uuid>
  run_id: run_<uuid>
  parent_artifact_id: null
  status: valid
  created_at: 2026-07-25T00:00:00Z
  producer:
    component_id: creative-director
    component_version: 0.1.0
    model_provider: optional
    model_name: optional
    instruction_version: optional
  source_refs: []
  confidence:
    evidence: 0
    reasoning: 0
    creative: 0
  provenance:
    evidence_refs: []
    knowledge_versions: []
    correlation_id: corr_<uuid>
    causation_id: cmd_<uuid>
  validation:
    status: passed
    findings: []
  payload: {}
```

Required fields may not be omitted. Optional dimensions use `null`, not ambiguous absence, when the schema requires an explicit value.

## Engine contract

Each engine registers:

```yaml
engine:
  id: creative-director
  version: 0.1.0
  capability: creative_direction
  accepts:
    - knowledge_fusion_package@1
  produces:
    - creative_direction_package@1
  owns:
    - payload.direction
  execution:
    idempotent: true
    timeout_seconds: 120
    max_attempts: 3
  quality:
    minimum_evidence_confidence: 70
    minimum_reasoning_confidence: 75
```

Invocation request:

```yaml
engine_request:
  request_id: req_<uuid>
  run_id: run_<uuid>
  node_id: node_creative_direction
  capability: creative_direction
  input_artifact_refs: []
  project_context_ref: ctx_<uuid>
  constraints: {}
  deadline: null
  correlation_id: corr_<uuid>
```

Invocation response:

```yaml
engine_response:
  request_id: req_<uuid>
  status: succeeded
  output_artifact_refs: []
  warnings: []
  metrics:
    duration_ms: 0
    input_units: 0
    output_units: 0
    estimated_cost: null
  error: null
```

Allowed statuses: `succeeded`, `failed`, `needs_clarification`, `blocked`, `cancelled`.

## Connector contract

Capability request:

```yaml
connector_request:
  request_id: conreq_<uuid>
  capability: candidate_generation
  provider_policy:
    allowed_providers: []
    preferred_provider: null
    data_classification: internal
  payload: {}
  timeout_seconds: 90
  idempotency_key: idem_<hash>
  correlation_id: corr_<uuid>
```

Normalized response:

```yaml
connector_response:
  request_id: conreq_<uuid>
  status: succeeded
  provider:
    id: provider-id
    model: model-id
    region: null
  output: {}
  usage:
    input_units: 0
    output_units: 0
    cost: null
    latency_ms: 0
  safety:
    status: passed
    findings: []
  error: null
```

Provider-native request and response types must not escape the connector implementation.

## Workflow definition contract

```yaml
workflow:
  id: creative-direction-decisive-slice
  version: 1.0.0
  input_schema: intake_package@1
  output_schema: provenance_record@1
  mode_default: guided
  nodes:
    - id: normalize-brief
      capability: brief_normalization
      depends_on: []
      retry_policy: standard
      timeout_seconds: 60
      approval_gate: false
    - id: knowledge-fusion
      capability: knowledge_fusion
      depends_on: [normalize-brief]
      retry_policy: standard
      timeout_seconds: 120
      approval_gate: false
    - id: creative-direction
      capability: creative_direction
      depends_on: [knowledge-fusion]
      retry_policy: standard
      timeout_seconds: 120
      approval_gate: true
    - id: generation-specification
      capability: generation_specification
      depends_on: [creative-direction]
      retry_policy: standard
      timeout_seconds: 120
      approval_gate: false
    - id: generate-candidates
      capability: candidate_generation
      depends_on: [generation-specification]
      retry_policy: standard
      timeout_seconds: 300
      approval_gate: false
    - id: deterministic-review
      capability: deterministic_candidate_review
      depends_on: [generate-candidates]
      retry_policy: standard
      timeout_seconds: 90
      approval_gate: false
    - id: critic-review
      capability: critic_evaluation
      depends_on: [deterministic-review]
      retry_policy: standard
      timeout_seconds: 180
      approval_gate: true
  gates:
    - id: direction_approval
      subject_artifact_type: creative_direction_package@1
      approval_record_type: direction_approval_record@1
    - id: final_approval
      subject_artifact_type: generated_candidate_set@1
      required_companion_artifact_type: critic_evaluation_package@1
      approval_record_type: final_approval_record@1
  budgets:
    max_duration_seconds: 1800
    max_cost: null
  completion:
    required_nodes: [normalize-brief, knowledge-fusion, creative-direction, generation-specification, generate-candidates, deterministic-review, critic-review]
    required_artifact_types:
      - normalized_brief@1
      - knowledge_fusion_package@1
      - creative_direction_package@1
      - direction_approval_record@1
      - generation_specification@1
      - generated_candidate_set@1
      - critic_evaluation_package@1
      - final_approval_record@1
      - provenance_record@1
```

Workflow definitions reference capabilities, not provider names or implementation classes.

## Critic contract

```yaml
critic:
  id: visual-alignment-critic
  version: 0.1.0
  dimension: visual_alignment
  accepts:
    - generation_specification@1
    - generated_candidate_set@1
  produces:
    - critic_evaluation_package@1
```

Evaluation output:

```yaml
critic_evaluation:
  dimension: visual_alignment
  score: 0
  gate_status: pass
  findings:
    - code: VISUAL_DIRECTION_MISMATCH
      severity: major
      message: ""
      affected_path: payload.candidates[0]
      recommendation: ""
```

A critic does not mutate the reviewed artifact.

## Human gate contract

```yaml
approval_record:
  id: apr_<uuid>
  project_id: prj_<uuid>
  run_id: run_<uuid>
  artifact_ref: art_<uuid>@1
  record_type: direction_approval_record
  gate_id: direction_approval
  decision: approved
  actor_id: usr_<uuid>
  actor_role: creative_director
  rationale: ""
  created_at: 2026-07-25T00:00:00Z
  conditions: []
```

Allowed decisions: `approved`, `rejected`, `revision_requested`, `waived`.

Canonical gate IDs are `direction_approval` and `final_approval`. Generation must not start without a valid approved `direction_approval` record for the current `Creative Direction Package`, and export must not start without a valid approved `final_approval` record for the current `Generated Candidate Set` plus `Critic Evaluation Package`.

## Error contract

```yaml
error:
  code: SYM-001
  category: validation
  message: Mixed metaphors detected
  retryable: false
  severity: major
  affected_path: payload.symbolism
  details: {}
  upstream_artifact_refs: []
```

Error categories: `input`, `validation`, `policy`, `dependency`, `provider`, `timeout`, `rate_limit`, `conflict`, `internal`, `cancelled`.

## Ownership enforcement

The Kernel rejects a write when:

- the producer does not own the target artifact section;
- the schema version is unsupported;
- required provenance is missing;
- source references do not exist;
- a state transition is invalid;
- an immutable artifact is modified in place;
- a human gate is bypassed.

The Kernel also rejects any attempt to export directly from generated outputs without passing through deterministic review, critic evaluation, final approval, and provenance capture.

## Architecture-freeze rule

Changes to these envelope shapes or ownership rules require:

1. compatibility classification;
2. migration and rollback plan;
3. updated schemas and tests;
4. ADR review when architecture-significant.
