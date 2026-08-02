# ADR-0004: Use a Hybrid DAG Execution Model

- Status: Accepted
- Date: 2026-07-25
- Decision owners: Motiflow architecture
- Related task: None
- Supersedes: None
- Superseded by: None

## Context

Motiflow must coordinate research, business analysis, narrative interpretation, symbolism, creative direction, generation, evaluation, and human approval.

A purely sequential chain is easy to understand but wastes time where analysis tasks are independent and increases the risk that early weak output contaminates every later stage. A fully parallel multi-agent system is faster in theory but creates uncontrolled conflicts, duplicate work, unclear decision ownership, and difficulty determining which output should constrain downstream work.

The system also needs to ensure that each output is validated before it becomes an input to another engine, while preserving provenance, confidence, retry behavior, and human approval.

## Decision

Motiflow will use a **hybrid directed acyclic graph (DAG)** execution model.

The default pattern is:

1. Parallel discovery for independent intelligence tasks
2. A fusion stage that validates and reconciles findings
3. Sequential creative commitment for decisions that narrow the design space
4. Parallel derivation after a creative direction is approved
5. Compilation into provider-neutral and provider-specific specifications
6. Parallel critic evaluation
7. Human approval before external publication or other configured high-impact actions

The Workflow Orchestrator schedules and tracks this graph. The Creative Kernel validates packages, state transitions, confidence, provenance, and policies. Specialist engines remain bounded reasoning components and do not control the overall workflow.

## Consequences

### Positive

- Independent analysis can run concurrently.
- Creative decisions remain coherent and progressively constrained.
- Outputs become validated inputs through explicit package contracts.
- Failures can be retried at stage level.
- Human gates can pause and resume workflows cleanly.
- Provenance and dependency relationships are visible.
- The workflow can evolve without building one monolithic agent.

### Negative

- DAG definition, state management, and observability add implementation complexity.
- Fusion and conflict-resolution policies require deliberate design.
- Debugging distributed asynchronous behavior is harder than debugging one synchronous chain.
- Schema and version discipline become mandatory.

## Alternatives considered

### Fully sequential chain

Rejected as the default because it creates unnecessary latency, tightly couples every stage, and does not exploit independent discovery work.

### Fully parallel agent swarm

Rejected because it makes conflict resolution, decision ownership, reproducibility, and governance too weak for the target enterprise use case.

### One monolithic creative agent

Rejected because it is difficult to evaluate, test, explain, govern, and replace individual capabilities.

## Implementation implications

- Workflow definitions must declare dependencies explicitly.
- Stages must be idempotent where practical.
- Packages must be immutable and versioned.
- Fusion stages must preserve disagreement and uncertainty.
- The UI must display stage status and lineage without exposing private chain-of-thought.
- Approval stages must be first-class workflow nodes.

## Migration and Rollback

No orchestrator implementation exists yet, so there is nothing to migrate. Replacing the hybrid DAG model after implementation begins requires a superseding ADR.

## Verification

When implemented: workflow definitions declare explicit dependencies; independent stages run concurrently; approval stages are first-class nodes; provenance and lineage are recorded for every stage transition.

## Approval

Accepted by Jarkius (Product owner, Chief Architect), recorded 2026-07-26; acceptance regularized retroactively — the decision has governed the documented architecture since 2026-07-25.

## Related documents

- [`../../MASTER_CONTEXT.md`](../../MASTER_CONTEXT.md)
- [`../SYSTEM_DESIGN.md`](../SYSTEM_DESIGN.md)
- [`../PRD.md`](../PRD.md)
