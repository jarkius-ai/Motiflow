# Workflow Orchestrator

**Status:** Architecture specification
**Owner:** Chief Architect
**Scope:** Workflow planning, execution, dependency, retry, and approval boundaries

The Workflow Orchestrator executes Motiflow workflows as governed directed acyclic graphs.

## Responsibilities

- Parse and validate workflow definitions
- Resolve node dependencies
- Run independent nodes in parallel
- Enforce sequential dependencies where outputs become validated inputs
- Persist execution state and checkpoints
- Apply timeout, retry, fallback, and stopping policies
- Pause for human approval
- Recompute only invalidated downstream nodes
- Emit telemetry, audit events, and cost records

## Execution model

```text
Parallel discovery
→ knowledge fusion
→ sequential creative reasoning
→ parallel direction or asset generation
→ multi-critic evaluation
→ human approval
→ publication
```

## Node contract

Every node declares:

- Node type and version
- Required input artifact contracts
- Output artifact contracts
- Idempotency strategy
- Timeout and retry policy
- Cost and provider constraints
- Confidence requirements
- Failure and fallback behavior
- Approval requirements

## State model

Suggested execution states:

`draft`, `validated`, `queued`, `running`, `waiting`, `succeeded`, `failed`, `cancelled`, `superseded`.

## Failure behavior

- Retry only transient failures.
- Do not retry deterministic schema or policy failures without changed input.
- Preserve partial successful outputs.
- Escalate when confidence, quality, budget, or retry thresholds are exceeded.
- Never hide fallback behavior from provenance.

## Selective rerun

When an upstream artifact changes, the orchestrator calculates affected descendants using artifact lineage. Unaffected branches remain valid, reducing cost and preserving approved work.
