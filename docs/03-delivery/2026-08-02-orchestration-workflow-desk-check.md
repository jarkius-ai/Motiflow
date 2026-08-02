# Orchestration and Workflow Desk Check — 2026-08-02

**Status:** Completed documentation desk check
**Evidence class:** Internal architecture-coherence verification; zero implementation, participant, or product-readiness credit
**Scope:** Whether the specified DAG, state machine, runtime contracts, AI execution layer, and agent-team charter can be traced through a case end-to-end without inventing an undocumented rule
**Execution date/timezone:** 2026-08-02, Asia/Bangkok workspace clock
**Reviewed state:** Not part of any `review-candidate commit`; this is a standalone desk check against `main` at the time of writing

## Non-claim

This is not an implementation, a running system, a test, a participant
session, a product-owner decision, or a substitute for the Task 001 Definition
of Ready. It records whether the orchestration and workflow specification —
`docs/02-architecture/WORKFLOW_ORCHESTRATOR.md`,
`docs/02-architecture/WORKFLOW_STATE_MACHINE.md`,
`docs/02-architecture/RUNTIME_CONTRACTS.md`,
`docs/02-architecture/AI_EXECUTION_LAYER.md`,
`docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md`, `MEOS/19_AI_WORKFORCE_CHARTER.md`,
and `MEOS/roles.yaml` — is internally coherent enough to trace a case without a
facilitator inventing a requirement, a state, or an authority the documents do
not already grant. Task 001 remains `BLOCKED`; no code exists.

## Method

Trace two prepared cases from
[`docs/01-product/validation/VALIDATION_CASE_CATALOG.md`](../01-product/validation/VALIDATION_CASE_CATALOG.md)
through the documented state machine and role/authority model:

1. a well-formed case, to confirm the canonical happy path is fully specified
   from intake to export;
2. an intentionally broken edge case, to confirm the specification has an
   explicit non-`FAILED` outcome for missing-input pressure rather than
   silently requiring invention.

A path fails when tracing it requires inventing a node, a state, an approval
authority, or a contract field the cited documents do not already define.

## Trace A — `VC-01` (well-formed brief, happy path)

| State transition | Node / capability | Artifact produced | Role owner (`MEOS/roles.yaml` mapping via `AUTONOMOUS_AGENT_TEAM_CHARTER.md`) |
|---|---|---|---|
| `CREATED → VALIDATING → VALIDATED` | Orchestrator input check | Intake Package validated | Orchestrator (system) |
| `VALIDATED → DISCOVERY_RUNNING → DISCOVERY_COMPLETE` | `normalize-brief` (`brief_normalization`) | Normalized Brief | `implementer`-owned engine |
| `→ FUSION_RUNNING → KNOWLEDGE_FUSED` | `knowledge-fusion` | Knowledge Fusion Package | `implementer`-owned engine |
| `→ DIRECTING → CREATIVE_DIRECTION_READY` | `creative-direction` | Creative Direction Package (envelope; `confidence.evidence ≥70`, `confidence.reasoning ≥75` per engine contract) | `implementer`-owned engine |
| `→ AWAITING_DIRECTION_APPROVAL` | Gate `direction_approval` | — | Orchestrator assembles review materials |
| `→ DIRECTION_APPROVED` | Human decision: `approved` | Direction Approval Record (`created_by.type == human`) | Human authority |
| `→ SPECIFYING_GENERATION → GENERATION_SPECIFIED` | `generation-specification` | Generation Specification | engine |
| `→ GENERATING → GENERATED_CANDIDATES_READY` | `generate-candidates` via Connector Gateway | Generated Candidate Set | engine + connector |
| `→ DETERMINISTIC_REVIEWING → CRITIC_REVIEWING` | `deterministic-review`, `critic-review` | Critic Evaluation Package | `qa` + critic engine |
| `→ AWAITING_FINAL_APPROVAL → FINAL_APPROVED` | Gate `final_approval` | Final Approval Record | Human authority |
| `→ EXPORTING → EXPORTED` | export | Provenance Record | Orchestrator |

**Desk-check result:** `PASS`. Every node in the state machine's core
transition table has a matching node in the `RUNTIME_CONTRACTS.md` workflow
definition; the two human gates fall exactly where the state machine
mandates; nothing required inventing an undocumented step.

## Trace B — `VC-08` (edge case: no deck, no dimensions, no audience, no brand context)

`VALIDATION_CASE_CATALOG.md` requires the facilitator not to substitute a
deck, invent a size, or infer brand rules for this case.

- `normalize-brief` can still run: a Normalized Brief may legitimately record
  the gaps as unresolved fields instead of failing outright.
- The break point is `creative-direction` (potentially `knowledge-fusion` if
  it needs the deck for grounding): the engine cannot produce a Creative
  Direction Package meeting the required confidence minimums without
  inventing the missing deck, brand, or audience.
- Per `WORKFLOW_STATE_MACHINE.md`'s clarification behavior, this routes to
  `NEEDS_CLARIFICATION`, not `FAILED` — a legitimate missing-input stop, not a
  retryable transient error. The record must specify the missing field, why
  execution cannot proceed safely, the acceptable response structure, and the
  resume node; the specification requires this shape but correctly leaves the
  case-specific content to the actual session.
- The run never reaches `CREATIVE_DIRECTION_READY`, so `direction_approval` is
  never reached and generation is correctly never attempted.

**Desk-check result:** `PASS`. The specification has an explicit, non-`FAILED`
state for exactly this pressure, and nothing in the trace required inventing a
rule the documents do not already give.

## Design confirmation (not a defect)

`VC-06` (policy-sensitive brief) reads as though it needs a dedicated
policy-check node, but `RUNTIME_CONTRACTS.md`'s workflow definition has none.
Tracing it: the safeguard is architecturally the `direction_approval` human
gate itself. `generation-specification` declares `depends_on:
[creative-direction]`, and `creative-direction` carries `approval_gate: true`,
so no candidate generation can start on an unsafe direction until a human
explicitly approves it. This is consistent with the two-gate model in
`RUNTIME_CONTRACTS.md` ("the decisive slice exposes exactly two human gates")
and required cross-referencing three documents to confirm, which is the kind
of question this desk check exists to answer.

## Desk-check conclusion

The orchestration, state machine, runtime contracts, and agent-authority
model as specified are internally coherent enough to trace both a clean case
and a deliberately broken case without inventing an undocumented rule. This
conclusion applies only to specification coherence. It does not verify
runnable code (none exists), real model behavior, real human usability, or
any product decision, and it does not change `readiness_score_current`,
`task_001_status`, or any other machine-verifiable readiness field in
`CONTEXT_INDEX.yaml`.
