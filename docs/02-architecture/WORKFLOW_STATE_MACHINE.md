# Motiflow Workflow State Machine

**Status:** Proposed architecture freeze v0.1  
**Owner:** Chief Architect

## Run states

```text
CREATED
→ VALIDATING
→ VALIDATED
→ DISCOVERY_RUNNING
→ DISCOVERY_COMPLETE
→ FUSION_RUNNING
→ KNOWLEDGE_FUSED
→ SYMBOLIZING
→ SYMBOLIZED
→ DIRECTING
→ DIRECTED
→ DESIGNING
→ DESIGNED
→ COMPILING
→ COMPILED
→ REVIEWING
→ AWAITING_HUMAN_APPROVAL
→ APPROVED
→ GENERATING
→ GENERATED
→ PUBLISHED
```

Exceptional states:

```text
REVISION_REQUIRED
NEEDS_CLARIFICATION
BLOCKED
FAILED
CANCEL_REQUESTED
CANCELLED
```

## Transition rules

Each transition must define:

- current state;
- target state;
- allowed actor or component;
- preconditions;
- validator;
- emitted event;
- retry behavior;
- timeout;
- downstream invalidation behavior;
- audit requirements.

## Core transitions

| From | To | Owner | Preconditions |
|---|---|---|---|
| CREATED | VALIDATING | Orchestrator | Input exists |
| VALIDATING | VALIDATED | Kernel | Input schema and policy pass |
| VALIDATED | DISCOVERY_RUNNING | Orchestrator | Required discovery nodes registered |
| DISCOVERY_RUNNING | DISCOVERY_COMPLETE | Orchestrator | Required nodes succeeded and outputs validate |
| DISCOVERY_COMPLETE | FUSION_RUNNING | Orchestrator | Synchronization barrier reached |
| FUSION_RUNNING | KNOWLEDGE_FUSED | Kernel | Fusion package validates |
| KNOWLEDGE_FUSED | SYMBOLIZING | Orchestrator | Required evidence threshold met |
| SYMBOLIZING | SYMBOLIZED | Kernel | Symbol package validates and one dominant metaphor exists |
| SYMBOLIZED | DIRECTING | Orchestrator | Symbol package accepted |
| DIRECTING | DIRECTED | Kernel | Creative direction package validates |
| DIRECTED | DESIGNING | Orchestrator | Direction gate passed |
| DESIGNING | DESIGNED | Kernel | Required design packages validate |
| DESIGNED | COMPILING | Orchestrator | Target providers selected |
| COMPILING | COMPILED | Kernel | Generation specifications validate and no prompt drift detected |
| COMPILED | REVIEWING | Orchestrator | Required critics registered |
| REVIEWING | AWAITING_HUMAN_APPROVAL | Review Fusion | Critical gates pass or require human resolution |
| AWAITING_HUMAN_APPROVAL | APPROVED | Authorized human | Approval record valid |
| APPROVED | GENERATING | Orchestrator | Generation authorization valid |
| GENERATING | GENERATED | Kernel | Generated asset record validates |
| GENERATED | PUBLISHED | Authorized publishing workflow | Publication approval and connector authorization valid |

## Revision behavior

A critic, validator, or human may route a run to `REVISION_REQUIRED` with:

- failing artifact reference;
- finding code;
- required upstream stage;
- affected paths;
- invalidated downstream artifacts;
- preserved unaffected artifacts.

After revision, the Orchestrator resumes from the earliest invalidated node rather than restarting the full run.

## Clarification behavior

`NEEDS_CLARIFICATION` pauses the run without counting as a failed attempt. The request must specify:

- missing or ambiguous field;
- why execution cannot proceed safely;
- acceptable response structure;
- node that will resume.

## Failure behavior

A run enters `FAILED` only when:

- a non-retryable error occurs;
- retry budget is exhausted;
- a policy violation blocks execution;
- required dependency remains unavailable beyond its timeout;
- state integrity cannot be guaranteed.

Every failure records the last valid state and a safe resume recommendation.

## Cancellation

Cancellation is cooperative:

1. request moves run to `CANCEL_REQUESTED`;
2. Orchestrator stops scheduling new nodes;
3. active idempotent work is cancelled where supported;
4. completed valid artifacts are preserved;
5. run enters `CANCELLED` after cleanup and audit.

## Idempotency

Every node execution uses a stable idempotency key derived from:

- workflow and node version;
- ordered input artifact versions;
- relevant configuration version;
- project policy version.

Retries must not create duplicate canonical artifacts for the same successful execution.

## Human gate integrity

An approval is invalid when:

- it references an outdated artifact version;
- the actor lacks the required role;
- a material downstream or upstream change occurred after approval;
- required critic findings are unresolved;
- approval conditions are unmet.

Material changes invalidate dependent approvals automatically.
