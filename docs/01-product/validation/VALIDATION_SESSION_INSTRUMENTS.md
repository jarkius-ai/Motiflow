# Validation Session Instruments

**Status:** Review-ready facilitation kit
**Owner:** Product
**Scope:** Standard session script, scoring, review, evidence, and aggregation rules for MVP validation

This document defines the operational instruments for the protocol in
[`../MVP_VALIDATION_PLAN.md`](../MVP_VALIDATION_PLAN.md). It aligns session
behavior with the decisive slice in [`../../PRD.md`](../../PRD.md), the quality
layers in [`../../04-ai/EVALUATION_FRAMEWORK.md`](../../04-ai/EVALUATION_FRAMEWORK.md),
and the role coverage in [`../PERSONAS.md`](../PERSONAS.md).

Use this document with
[`VALIDATION_CASE_CATALOG.md`](./VALIDATION_CASE_CATALOG.md) and the dated round
report [`2026-07-25-mvp-validation-report.md`](./2026-07-25-mvp-validation-report.md).

## Audience boundary

Intended-user participants assess brief/direction usefulness, rationale, gate
comprehension, candidate review, and approval/provenance confidence. Do not quiz
them on all ten internal artifacts, envelope metadata, lineage algorithms, or
schema semantics. A trained facilitator records session mechanics; named
architecture and engineering reviewers separately assess the full internal
artifact chain and contract semantics.

## 1. Session Packet

Every scheduled session must have:

- one participant ID such as `U-01`
- one case ID such as `C-03`
- one session ID such as `S-U01-C03-01`
- one facilitator ID
- one reviewed contract revision
- one declared tool set for baseline capture
- one declared tool set for the proposed workflow exercise

## 2. Evidence IDs

Use opaque IDs only. Do not store participant identity or restricted source
material in the repository.

| Evidence type | Format | Example | Purpose |
|---|---|---|---|
| Session packet | `VPK-<session>` | `VPK-S-U01-C03-01` | Session-level instrument bundle |
| Consent record | `VCR-<participant>` | `VCR-U-01` | External consent evidence |
| Baseline capture | `VBL-<session>` | `VBL-S-U01-C03-01` | Baseline timing, revisions, tools |
| Intake notes | `VIN-<session>` | `VIN-S-U01-C03-01` | Clarifications and missing fields |
| Direction package | `VDP-<session>` | `VDP-S-U01-C03-01` | Creative Direction Package under review |
| Direction approval | `VDA-<session>` | `VDA-S-U01-C03-01` | Direction approval outcome |
| Generation spec | `VGS-<session>` | `VGS-S-U01-C03-01` | Approved-direction compilation |
| Candidate review | `VCRV-<session>` | `VCRV-S-U01-C03-01` | Candidate set plus revision requests |
| Critic review | `VCE-<session>` | `VCE-S-U01-C03-01` | Deterministic and focused critic findings |
| Final approval | `VFA-<session>` | `VFA-S-U01-C03-01` | Final approval or rejection outcome |
| Stop record | `VST-<session>` | `VST-S-U01-C03-01` | Auditable valid-stop outcome |
| Raw notes pointer | `VRN-<session>` | `VRN-S-U01-C03-01` | External restricted notes reference |

## 3. Facilitator Script

Use the same script for comparable sessions. Read prompts verbatim unless the
participant asks for plain-language restatement. Record any restatement as a
facilitator intervention.

### Opening

1. Confirm participant ID, case ID, consent status, and scheduled time window.
2. Say: "This session tests whether the proposed Motiflow workflow and artifact
   language are understandable and decision-ready before implementation."
3. Say: "We are evaluating the workflow, not your performance. Please flag any
   wording, assumptions, or artifacts that do not make sense."
4. Say: "I will record timings, clarification points, and where the workflow
   requires intervention."

### Baseline capture

1. Ask: "How would you normally handle this kind of brief today?"
2. Ask for the participant's normal tool set, elapsed time estimate to approved
   direction and final outcome, and usual direction and candidate revision
   counts.
3. Ask what usually causes rework, approval delay, or loss of confidence.
4. Ask the participant to rate the usefulness of the direction and clarity of
   its rationale in their current workflow using the section 6 anchors.
5. Record the baseline under the `VBL-*` evidence ID before the proposed
   workflow starts.

### Proposed workflow exercise

1. Present the synthetic case exactly as written.
2. Ask the participant to identify missing, contradictory, or sensitive inputs.
3. Normalize the case into canonical fields and record every clarification. If
   the participant asks for information absent from the packet, say: "No
   additional source information is available for this case." Record the
   unresolved field. Continue only when the participant states that the gap is
   not material to the evaluation; otherwise stop under section 11. Do not let
   the participant or facilitator invent authoritative source facts.
4. Produce or present the Knowledge Fusion Package and Creative Direction
   Package using the declared tools only.
5. Run the pre-generation constraint-sufficiency check in section 8, then ask
   the participant to `approve`, `reject`, or `request revision` of the
   direction.
6. Ask the gate-comprehension question for direction approval before moving on.
7. If direction approval is valid, create the Generation Specification and
   candidate set.
8. Apply the deterministic checklist and focused critic rubric.
9. Ask the participant to `approve`, `reject`, or `request revision` of the
   candidate set. When approved, record selected candidate IDs separately.
10. Ask the gate-comprehension question for final approval.
11. Capture ratings, friction points, missing information, vocabulary
    confusion, and confidence in the approval/provenance record.

Record participant language verbatim, then map it to the proposed canonical
approval contract. `request revision` maps to `revision_requested`; candidate
selection is recorded only with an `approved` final decision. No participant
action maps to `waived`.

### Closing

1. Ask: "What felt unnecessary, unclear, or risky in this workflow?"
2. Ask: "What would need to change before you would trust this in production?"
3. Confirm whether any follow-up or unresolved issue should be logged as a
   contract or vocabulary finding.

## 4. Timing And Pause Rules

- Start both proposed-workflow clocks when the participant begins reviewing the
  case.
- Stop `proposed_minutes_to_direction_outcome` when direction is approved,
  rejected, sent for revision, or validly stopped.
- Stop `proposed_total_minutes` when final approval is approved, rejected, sent
  for revision, or the case is validly stopped. Leave this value `not
  applicable` when the case never passes direction approval.
- Pause the timer only for non-workflow interruptions longer than 30 seconds:
  connectivity issue, room interruption, or participant break.
- Do not pause for clarification, review, debate, or facilitator explanation.
  Those are part of the measured workflow.
- Record each pause with start time, end time, reason, and whether it changed
  the participant's context.
- Record facilitator interventions separately from pauses.
- If more than two facilitator reinterpretations are required to keep the case
  moving, flag the session as `artifact insufficiency risk` even if it
  completes.

## 5. Baseline Capture Fields

Capture these fields before the exercise:

| Field | Requirement |
|---|---|
| `participant_role` | Map to one or more roles in `PERSONAS.md` |
| `current_workflow_summary` | One concise paragraph |
| `baseline_tools` | Named tools or manual workflow only |
| `baseline_minutes_to_approved_direction` | Numeric estimate |
| `baseline_total_minutes_to_final_outcome` | Numeric estimate if the current workflow includes candidate approval |
| `baseline_direction_revision_count` | Numeric estimate |
| `baseline_candidate_revision_count` | Numeric estimate if applicable |
| `baseline_direction_usefulness_1_5` | Rating using section 6 anchors |
| `baseline_rationale_clarity_1_5` | Rating using section 6 anchors |
| `baseline_confidence_notes` | Main reasons for confidence or doubt |
| `baseline_rework_triggers` | Top causes of delay or confusion |

## 6. Ratings (1-5)

Use the same five-point scale across direction usefulness, rationale clarity,
final approval confidence, and confidence in approval/provenance records.

| Rating | Anchor |
|---:|---|
| 1 | Unusable or actively misleading |
| 2 | Major gaps; not safe without substantial rework |
| 3 | Usable with material clarification or revision |
| 4 | Useful and clear with only minor changes |
| 5 | Immediately useful, clear, and decision-ready |

Record each rating separately. Do not average away a blocking failure.

## 7. Gate-Comprehension Check

Ask both questions without coaching:

1. "In your own words, what does direction approval mean in this workflow?"
2. "How is final approval different from direction approval?"

Pass conditions:

- Direction approval answer states that the current Creative Direction Package
  is being accepted or frozen before generation.
- Final approval answer states that the current candidate set is being judged
  after deterministic and critic review, before export or downstream use.
- The participant does not conflate direction approval with final visual
  approval.

Failure conditions:

- The facilitator prompts the participant toward the answer.
- The participant still conflates the two gates after the second question.

## 8. Pre-Generation Constraint-Sufficiency Check

Run this check before a Direction Approval Record can authorize generation. It
is decision support inside the direction gate, not a third approval gate.

- Required brand, policy, prohibited-element, audience, channel, and source
  constraints are explicit or explicitly not applicable.
- No unresolved high- or critical-severity constraint finding remains.
- The participant confirms whether their role is competent to assess each
  sensitive constraint; missing approval expertise is recorded as a blocker.
- The Creative Direction Package introduces no unsupported claim, depiction, or
  requirement.

Record exactly one result:

- `safe_to_generate` — direction approval may be evaluated;
- `requires_revision` — deterministically record the approval decision
  `revision_requested`; generation is not authorized; or
- `stopped_constraint_insufficiency` — create a `VST-*` record and end the case
  before Generation Specification work.

## 9. Deterministic Review Checklist

Run this checklist after the Generation Specification or candidate set exists.
The facilitator or architecture/engineering reviewer completes it; the
intended-user participant is not required to interpret schema or lineage
mechanics. Any blocking failure stays blocking regardless of average scores.

| Check | Pass rule | Blocking |
|---|---|---:|
| Case traceability | Case ID, session ID, and artifact IDs are present and linked | Yes |
| Normalized Brief completeness | Required fields are present or explicitly marked unresolved | Yes |
| Contradictions surfaced | Contradictions are recorded, not silently normalized away | Yes |
| Constraint preservation | Brand, policy, prohibited elements, and channel limits survive into direction and generation artifacts | Yes |
| Direction rationale references evidence | Rationale cites brief or source inputs rather than unsupported claims | Yes |
| Generation scope control | Generation Specification uses only approved direction content | Yes |
| Candidate lineage | Candidate set references the reviewed Generation Specification | Yes |
| Critic citation quality | Each critic finding names the affected artifact field or constraint | Yes |
| Approval separation | Direction approval and final approval records are distinct | Yes |
| Provenance recordability | The session can point to the required evidence IDs without identity leakage | No |

## 10. Focused Critic Rubric

Use this rubric to structure critic findings. Critics must cite evidence and
recommend action, not just assign scores.

| Critic lens | Key question | Severity options | Blocking rule |
|---|---|---|---|
| Narrative fit | Does the direction express the stated communication objective and audience? | `low`, `medium`, `high`, `critical` | `critical` blocks |
| Metaphor and symbolism | Are the metaphor and symbolism coherent, explainable, and non-random? | `low`, `medium`, `high`, `critical` | `critical` blocks |
| Brand alignment | Does the output stay within explicit brand constraints and prohibited elements? | `low`, `medium`, `high`, `critical` | `high` or `critical` blocks |
| Business alignment | Does the direction support the business goal, channel, and call-to-action context? | `low`, `medium`, `high`, `critical` | `critical` blocks |
| Production readiness | Would a designer or producer know what to make next without hidden interpretation? | `low`, `medium`, `high`, `critical` | `critical` blocks |
| Policy and safety | Are restricted claims, unsafe implications, or disallowed depictions avoided? | `low`, `medium`, `high`, `critical` | `high` or `critical` blocks |
| Cross-artifact consistency | Do brief, direction, generation, critic findings, and approval logic still agree? | `low`, `medium`, `high`, `critical` | `critical` blocks |

For every critic finding, record:

- affected artifact and field
- supporting evidence reference
- severity
- confidence
- recommended action: `keep`, `revise`, `reject`, or `defer`

## 11. Stop Conditions

Stop a case immediately when:

- consent is withdrawn
- restricted information cannot be handled safely
- the artifact chain cannot proceed without inventing a material requirement
- an approval would need to be fabricated
- the participant refuses to continue because the workflow is too unclear to
  evaluate
- policy or brand risk is identified that the declared session setup cannot
  safely review

Record:

- stop record ID (`VST-*`)
- last valid stage
- blocking reason
- whether the stop was protocol-driven or participant-driven
- whether the stop itself counts as useful failure evidence

## 12. Aggregation Rules

Aggregate only completed or validly stopped sessions recorded in the dated
validation report.

- Use median, not mean, for time to approved direction and revision counts.
- Report the contributing session count (`n`) for every median and the
  numerator/denominator for every percentage.
- Include only sessions with an approved direction in the comparative
  `minutes to approved direction` median. Report rejected, revision-requested,
  and stopped direction outcomes separately; never encode them as zero minutes.
- Include only sessions with a recorded final outcome in end-to-end time and
  candidate-revision aggregates.
- Compute the `usefulness or clarity threshold` as the percentage of completed
  sessions where direction usefulness or rationale clarity is rated `4` or `5`.
- Compute `gate comprehension pass rate` from unprompted passes only.
- Record a gate question that could not be asked as `not assessed`, not as a
  pass. Every participant must have at least one completed two-gate
  comprehension assessment for the round to pass.
- Count a stopped case only when the stopping reason is documented and reviewed
  as evidence.
- Do not average critical or blocking failures into passing aggregate scores.
- Report per-role variance for direction-owner and approval-oriented
  participants separately when the sample allows it.
- If a case required undocumented facilitator interpretation, mark
  `artifact sufficiency` as failed for that session.
- A round cannot produce `PROCEED` unless all mandatory exit criteria in
  `MVP_VALIDATION_PLAN.md` pass, regardless of favorable aggregate scores.

## 13. Minimal Session Log Template

Use this row shape in the dated validation report:

| Session | Participant | Case | Baseline direction minutes | Baseline total minutes | Baseline direction revisions | Baseline candidate revisions | Baseline usefulness 1-5 | Baseline rationale clarity 1-5 | Proposed direction minutes | Proposed total minutes | Direction revisions | Candidate revisions | Usefulness 1-5 | Rationale clarity 1-5 | Final confidence 1-5 | Approval/provenance confidence 1-5 | Two-gate comprehension | Clarifications | Facilitator interventions | Stop record ID | Outcome |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|---|---|
| `S-U01-C03-01` | `U-01` | `C-03` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` | `PENDING` |
