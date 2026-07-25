# Motiflow Workflow State Machine

**Status:** Review-ready architecture contract v0.3
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
→ DIRECTING
→ CREATIVE_DIRECTION_READY
→ AWAITING_DIRECTION_APPROVAL
→ DIRECTION_APPROVED
→ SPECIFYING_GENERATION
→ GENERATION_SPECIFIED
→ GENERATING
→ GENERATED_CANDIDATES_READY
→ DETERMINISTIC_REVIEWING
→ CRITIC_REVIEWING
→ AWAITING_FINAL_APPROVAL
→ FINAL_APPROVED
→ EXPORTING
→ EXPORTED
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

## Canonical decisive-slice artifact sequence

The decisive workflow slice uses one canonical artifact vocabulary:

```text
Intake Package
→ Normalized Brief
→ Knowledge Fusion Package
→ Creative Direction Package
→ Direction Approval Record
→ Generation Specification
→ Generated Candidate Set
→ Critic Evaluation Package
→ Final Approval Record
→ Provenance Record
```

`Publication Package` is not a canonical MVP workflow artifact. It is an optional post-MVP container assembled only after `FINAL_APPROVED`.

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
| FUSION_RUNNING | KNOWLEDGE_FUSED | Kernel | Knowledge Fusion Package validates |
| KNOWLEDGE_FUSED | DIRECTING | Orchestrator | Required evidence threshold met |
| DIRECTING | CREATIVE_DIRECTION_READY | Kernel | Creative Direction Package validates and is reviewable |
| CREATIVE_DIRECTION_READY | AWAITING_DIRECTION_APPROVAL | Orchestrator | Review materials and diff context exist |
| AWAITING_DIRECTION_APPROVAL | DIRECTION_APPROVED | Authorized human | Direction Approval Record is valid for the current Creative Direction Package version |
| DIRECTION_APPROVED | SPECIFYING_GENERATION | Orchestrator | Direction approval remains current and no invalidating upstream change exists |
| SPECIFYING_GENERATION | GENERATION_SPECIFIED | Kernel | Generation Specification validates and references the approved direction |
| GENERATION_SPECIFIED | GENERATING | Orchestrator | Target providers selected and generation authorization valid |
| GENERATING | GENERATED_CANDIDATES_READY | Kernel | Generated Candidate Set validates, even when it contains one candidate |
| GENERATED_CANDIDATES_READY | DETERMINISTIC_REVIEWING | Orchestrator | Required deterministic checks are registered |
| DETERMINISTIC_REVIEWING | CRITIC_REVIEWING | Kernel | Deterministic checks complete and findings are packaged for critic consumption |
| CRITIC_REVIEWING | AWAITING_FINAL_APPROVAL | Review Fusion | Required critic evaluations complete and Critic Evaluation Package validates |
| AWAITING_FINAL_APPROVAL | FINAL_APPROVED | Authorized human | Final Approval Record is valid for the current Generated Candidate Set and Critic Evaluation Package |
| FINAL_APPROVED | EXPORTING | Orchestrator | Export targets selected |
| EXPORTING | EXPORTED | Kernel | Provenance Record validates and export manifest is reproducible |
The core MVP state machine ends at `EXPORTED`. There is no generation-to-export shortcut: every exported output must pass deterministic review, critic evaluation, final approval, and provenance capture first.

An optional post-MVP publication specialization may begin from `EXPORTED`. Its publishing states and connector contracts are outside this core state machine and must not change the canonical MVP artifact chain.

## Revision behavior

A critic, validator, or human may route a run to `REVISION_REQUIRED` with:

- failing artifact reference;
- finding code;
- required upstream stage;
- affected paths;
- invalidated downstream artifacts;
- preserved unaffected artifacts.

After revision, the Orchestrator resumes from the earliest invalidated node rather than restarting the full run.

Revising an approved Creative Direction Package invalidates the Direction Approval Record, Generation Specification, Generated Candidate Set, Critic Evaluation Package, Final Approval Record, and Provenance Record. Revising generated candidates does not invalidate direction approval unless direction-owned fields change.

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

Direction approval and final approval are independent human gates. Material changes invalidate dependent approvals automatically, and no run may bypass either gate on the path to export or publication.
