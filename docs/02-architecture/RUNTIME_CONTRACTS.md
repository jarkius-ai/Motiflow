# Motiflow Runtime Contracts

**Status:** Proposed architecture freeze v0.1  
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

## Canonical artifact envelope

```yaml
artifact:
  id: art_<uuid>
  type: narrative_package
  schema_version: 1.0.0
  artifact_version: 1
  project_id: prj_<uuid>
  run_id: run_<uuid>
  parent_artifact_id: null
  status: valid
  created_at: 2026-07-25T00:00:00Z
  producer:
    component_id: narrative-engine
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
  id: narrative-engine
  version: 0.1.0
  capability: narrative_analysis
  accepts:
    - normalized_brief@1
  produces:
    - narrative_package@1
  owns:
    - payload.narrative
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
  node_id: node_narrative
  capability: narrative_analysis
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
  capability: high_precision_narrative_analysis
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
  id: editorial-banner
  version: 1.0.0
  input_schema: normalized_brief@1
  output_schema: approved_artifact@1
  mode_default: guided
  nodes:
    - id: narrative
      capability: narrative_analysis
      depends_on: []
      retry_policy: standard
      timeout_seconds: 120
      approval_gate: false
  gates: []
  budgets:
    max_duration_seconds: 1800
    max_cost: null
  completion:
    required_nodes: []
    required_artifact_types: []
```

Workflow definitions reference capabilities, not provider names or implementation classes.

## Critic contract

```yaml
critic:
  id: editorial-critic
  version: 0.1.0
  dimension: editorial_quality
  accepts:
    - creative_direction_package@1
  produces:
    - critic_evaluation@1
```

Evaluation output:

```yaml
critic_evaluation:
  dimension: editorial_quality
  score: 0
  gate_status: pass
  findings:
    - code: EDITORIAL_HERO_UNCLEAR
      severity: major
      message: ""
      affected_path: payload.direction.hero
      recommendation: ""
```

A critic does not mutate the reviewed artifact.

## Approval contract

```yaml
approval_record:
  id: apr_<uuid>
  project_id: prj_<uuid>
  run_id: run_<uuid>
  artifact_ref: art_<uuid>@1
  gate_id: final_direction
  decision: approved
  actor_id: usr_<uuid>
  actor_role: creative_director
  rationale: ""
  created_at: 2026-07-25T00:00:00Z
  conditions: []
```

Allowed decisions: `approved`, `rejected`, `revision_requested`, `waived`.

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

## Architecture-freeze rule

Changes to these envelope shapes or ownership rules require:

1. compatibility classification;
2. migration and rollback plan;
3. updated schemas and tests;
4. ADR review when architecture-significant.
