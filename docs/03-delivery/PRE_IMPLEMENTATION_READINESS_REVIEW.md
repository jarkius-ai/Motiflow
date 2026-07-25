# Pre-Implementation Readiness Review

**Status:** `NOT READY`
**Last reviewed:** 2026-07-26 (Asia/Bangkok)
**Method:** BMAD Agentic Flow `PHASE`, `PERSONAS`, `READY`, `STORY`, and `CHECKPOINT`
**Source of truth:** Product validation plan, architecture contracts, MEOS readiness gate, and Task 001

## Outcome first

The documentation now provides an executable validation protocol, eight
prepared synthetic case packets, standard session instruments, a proposed ADR for
the artifact-envelope conflict, an explicit human contract checkpoint, and the
first bounded story packet. A
[`difficult-case desk check`](../01-product/validation/2026-07-26-validation-instrument-dry-run.md)
has verified the instrument structure without claiming participant evidence.
Implementation must not start yet. Participant
evidence, the accountable product-owner decision, accepted architecture and
contract decisions, and required human sign-off are absent.

The reproducible target is **100/100** for the completed evidence package, not
the current result of **37/100**. Per `MEOS/10_QUALITY_GATE.md`, no numerical
score can compensate for a failed mandatory gate.

## Phase and lenses

**Phase:** Planning → Solutioning boundary
**Primary lenses:** Product Manager and Architect
**Supporting lenses:** Analyst, UX Designer, Developer, Technical Writer
**Smallest next artifact:** completed participant session evidence in the dated validation report

Lens findings:

- **Analyst:** the hypothesis, sample size, eight-case catalog, and evidence instruments are explicit, but no field evidence exists.
- **Product Manager:** MVP scope is coherent; the product-owner authority and proceed/revise/stop decision are pending.
- **Architect:** the ten-artifact chain and two gates align; ADR-0003 now proposes one envelope and approval-reference resolution, but human acceptance is pending.
- **Developer:** Task 001 is bounded and verifiable; dependency/toolchain authority and controlling contracts block readiness.
- **UX Designer:** role coverage and gate-comprehension checks are defined; intended-user sessions have not occurred.
- **Technical Writer:** authority links and operational artifacts are explicit; signatures and accepted revisions remain pending.

## Mandatory readiness gates

| Gate | Status | Evidence or missing item |
|---|---|---|
| Product intent and non-goals | PASS | `PROJECT_CHARTER.md`, `docs/PRD.md`, narrowed validation boundary |
| Testable validation protocol | PASS | `docs/01-product/MVP_VALIDATION_PLAN.md` |
| 5–10 representative inputs executed | FAIL | Input matrix and session evidence are pending |
| 2–3 intended users involved | FAIL | Participant matrix and sessions are pending |
| Product-owner decision | FAIL | No named owner or proceed/revise/stop record |
| Human contract acceptance | FAIL | C-01–C-06 and signatories are pending |
| Architecture conflict resolution | FAIL | ADR-0003 is proposed, not accepted; controlling contracts remain unreconciled |
| Required ADR | FAIL | ADR-0003 exists in `Proposed`; Chief Architect acceptance is pending |
| Independently buildable story | PASS (prepared) | `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md` |
| Story Definition of Ready | FAIL | Task prerequisites and owner are pending |
| Verification command named | PASS (contract) | `./tools/validate-decisive-slice-contracts`; implementation does not exist yet |
| Rollback path | PASS | Task-level pre-consumer revert and post-consumer versioning rule |
| Durable trail | PASS | Dated report, acceptance record, task packet, this review |

**Readiness decision:** `NOT READY`

## Evidence-weighted score

The score evaluates readiness to begin Task 001, not prose quality.

This is a supporting pre-implementation rubric. Task implementation and
completion are scored separately by `MEOS/10_QUALITY_GATE.md`. Task 001 raises
that general 90-point floor to a task-specific minimum of 95. Neither score can
override a failed mandatory gate.

Every anchor is all-or-zero: award its exact points only when every listed
evidence requirement is present. Do not award fractional points within an
anchor. Mandatory gates remain independent and can fail even at 100 points.

| Category | Points | Objective evidence required for the anchor |
|---|---:|---|
| Scope fidelity | 5 | PRD and validation plan name the same decisive-slice boundary |
| Scope alignment | 5 | Roadmap, architecture packet, and Task 001 link the same ten-artifact/two-gate proposal without contradictory task scope |
| Scope-drift control | 5 | Publication, provider, runtime, persistence, and UI expansion are explicitly excluded from Task 001 |
| Dataset preparation | 5 | Catalog contains 5–10 cases and every required coverage category |
| Dataset execution | 15 | Every counted case has a completed or validly stopped terminal record; at least five outcomes exist and all catalog cases are dispositioned |
| Participant preparation | 3 | Two or three participant IDs have role coverage, consent evidence, and scheduled dates |
| Participant execution | 12 | Every participant completes at least two sessions, every case is covered, and required direction-owner/approver cross-role reviews are recorded |
| Protocol | 5 | One versioned facilitator protocol defines sequence, timing, pauses, clarifications, and stops |
| Ratings and comprehension | 5 | Anchored ratings and unprompted two-gate comprehension rules are versioned |
| Deterministic and critic instruments | 5 | Versioned pre-generation, deterministic, critic, and audience-separation rules exist |
| Controlled setup | 5 | Facilitator, baseline/proposed tools, model/provider versions, settings, and review-candidate SHA are named and frozen |
| Evidence IDs | 2 | Stable opaque ID formats exist for every evidence class |
| Restricted evidence controls | 3 | External storage location, access owner, and retention/deletion rule are recorded |
| Completed evidence | 7 | Run sheets, valid-stop records, friction decisions, aggregates, denominators/sample sizes, and per-role variance are complete |
| Revision trace | 3 | A candidate commit exists and its SHA plus decision links are recorded in a later evidence/sign-off commit or equivalent signed tag |
| Named governance | 3 | Accountable product owner, Chief Architect, and engineering lead are named |
| Contract acceptance | 6 | ADR-0003 and C-01–C-06 are explicitly accepted at the recorded candidate SHA |
| Final decision and DoR | 6 | Product-owner decision, all required signatures, and final Definition of Ready evidence are recorded |

| Category | Maximum | Current | To reach the reproducible target |
|---|---:|---:|---|
| Scope fidelity and wedge clarity | 15 | 15 | Preserve current boundary |
| Dataset execution and coverage | 20 | 5 | Execute the eight prepared cases and record valid terminal outcomes |
| Participant execution and coverage | 15 | 0 | Complete sessions with 2–3 intended users |
| Instrumentation and rubric quality | 20 | 15 | Name the facilitator and tools, then pin the instrument and contract revisions |
| Evidence and traceability | 15 | 2 | Declare restricted storage controls, complete evidence, then record the candidate SHA in a later evidence/sign-off commit or signed tag |
| Sign-off and governance | 15 | 0 | Name authorities, accept ADR-0003 and C-01–C-06, record product decision and signatures |
| **Total** | **100** | **37** | **Target: 100, with every mandatory gate passing** |

The structural review package is substantially complete. The five dataset
points represent catalog coverage, not execution; the instrumentation points
represent versionable instruments, not participant outcomes. The two
traceability points cover only the stable evidence-ID convention; no points are
awarded for pending storage, execution, two-step revision trace, or governance.

The current **37** is exactly: scope fidelity/alignment/drift control `15`,
dataset preparation `5`, protocol `5`, ratings/comprehension `5`, deterministic
and critic instruments `5`, and evidence IDs `2`. Every other anchor is `0`.

## Target score calculation

Because anchors are indivisible, the reproducible readiness target is:

- scope fidelity: 15/15;
- dataset execution: 20/20;
- participant execution: 15/15;
- instrumentation: 20/20;
- evidence and traceability: 15/15; and
- sign-off and governance: 15/15.

This yields **100/100**. Any missing participant, unresolved critical contract
decision, absent product-owner decision, or unsigned required review still makes
the result `NOT READY`, regardless of total.

## Ordered next actions

1. Commit the review candidate, then record its SHA in the later evidence/sign-off commit; product owner also names the facilitator, restricted evidence location, 2–3 intended users, and baseline/proposed tools in the dated report.
2. Facilitator schedules the prepared eight-case catalog across the participant roles and runs the standard instruments.
3. Complete every session row, friction decision, aggregate, and exit-criteria check; do not award execution points for scheduled or partial sessions.
4. Product owner records `PROCEED`, `REVISE`, or `STOP` tied to the evidence.
5. Architecture and engineering reviewers separately assess all ten internal artifacts, versioned lineage, approval references, schema semantics, and validator feasibility; do not transfer that burden to product participants.
6. Product owner, Chief Architect, and engineering lead accept or revise ADR-0003, close C-01–C-06, reconcile the controlling contracts, approve the validator toolchain, and sign the recorded review-candidate SHA.
7. If and only if the decision is `PROCEED` and contract outcome is `ACCEPTED`, run the MEOS Definition of Ready check, append its evidence to Task 001, and promote the task to `ready-for-dev / READY` only when every applicable check passes.

## Human checkpoint

**Orientation:** Review the highest-blast-radius decisions first: envelope shape,
approval references, two-gate semantics, and MVP boundary.

| Risk | Evidence | Human action |
|---|---|---|
| False validation claim | Dated report contains explicit pending state | Supply real participant evidence; do not substitute personas or AI reviews |
| Silent architecture choice | C-03 lists the incompatible envelopes | Select and merge one canonical shape |
| Final approval under-references evidence | C-04 identifies single-reference mismatch | Accept or revise the proposed reference array |
| Unaccepted architecture decision | ADR-0003 is only proposed | Chief Architect accepts, revises, or rejects it explicitly |
| Scope expansion | Publication workspace is marked post-MVP | Keep article/CMS/social behavior out of Task 001 |
| Unapproved dependency | C-06 and Task 001 require explicit approval | Name the validator/toolchain before readiness |

**Checkpoint decision:** `DIG DEEPER` until field evidence and sign-offs are recorded.
