# MVP Validation Report — 2026-07-25 Round

**Status:** Open; partial participant evidence recorded (2 of minimum 5 sessions); round incomplete, no product-owner decision recorded
**Owner:** Jarkius — Product owner
**Scope:** Readiness-to-build validation for the decisive creative-direction slice
**Protocol:** [`../MVP_VALIDATION_PLAN.md`](../MVP_VALIDATION_PLAN.md)
**Case catalog:** [`VALIDATION_CASE_CATALOG.md`](VALIDATION_CASE_CATALOG.md)
**Session instruments:** [`VALIDATION_SESSION_INSTRUMENTS.md`](VALIDATION_SESSION_INSTRUMENTS.md)
**Artifact worksheets:** [`VALIDATION_ARTIFACT_WORKSHEETS.md`](VALIDATION_ARTIFACT_WORKSHEETS.md)
**Instrument dry run:** [`2026-07-26-validation-instrument-dry-run.md`](2026-07-26-validation-instrument-dry-run.md) — internal desk check only
**Preparation base revision:** `df7af54`
**`review-candidate commit` SHA for participant sessions:** `efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`; committed packet, not yet presented to participants
**`trace-preparation commit`:** RECORDED; records the candidate SHA but claims no participant evidence or human decision
**`evidence/sign-off commit`:** PENDING; created after evidence and decisions are recorded, then optionally identified by a signed tag
**Restricted evidence location:** Pending; do not store participant identities or confidential inputs here

Naming note: this round is named for its packet-preparation date (2026-07-25);
the frozen `review-candidate commit` SHA above was committed 2026-07-26.

**Scope revision (2026-07-26):** the accountable product owner recorded a
solo-round `REVISE` — the sole intended user is Jarkius, per
[`../MVP_VALIDATION_PLAN.md`](../MVP_VALIDATION_PLAN.md) — and the participant
tables below remain to be executed under that solo scope.

## Decision status

**Current decision:** `NOT RECORDED`
Allowed final decisions: `PROCEED | REVISE | STOP`

**Independent readiness recommendation:** `REVISE` — complete fieldwork, resolve
the contract conflicts, and obtain human sign-off before reconsidering
`PROCEED`. This is not the product-owner decision.

`PROCEED` is invalid until every mandatory exit criterion below has evidence and
the contract acceptance record is signed. Empty cells and `PENDING` values are
failures, not implicit approvals.

## Input coverage

Use 5–10 anonymized cases. Eight is the default. One case may satisfy more than
one coverage requirement.

| Case | External evidence ID | Source type | Channel | Completeness | Ambiguity / contradiction | Brand / policy sensitivity | Expected decision difficulty | Status |
|---|---|---|---|---|---|---|---|---|
| VC-01 | `VCAT-VC-01` | structured brief | paid social static | high | low | low | medium | `CASE_PREPARED` |
| VC-02 | `VCAT-VC-02` | structured brief | landing-page hero | high | low | medium | medium | `CASE_PREPARED` |
| VC-03 | `VCAT-VC-03` | unstructured brief | email header | low | high; incomplete | low | high | `CASE_PREPARED` |
| VC-04 | `VCAT-VC-04` | mixed brief notes | paid social static | medium | contradictory | medium | high | `CASE_PREPARED` |
| VC-05 | `VCAT-VC-05` | structured brief | product-page hero | high | low | high brand sensitivity | high | `CASE_PREPARED` |
| VC-06 | `VCAT-VC-06` | structured brief | paid social static | high | medium | high policy sensitivity | high | `CASE_PREPARED` |
| VC-07 | `VCAT-VC-07` | article-derived brief | editorial illustration | medium | medium | low | high | `CASE_PREPARED` |
| VC-08 | `VCAT-VC-08` | sparse noisy input | display banner | low | high; missing dependency | medium | high | `CASE_PREPARED` |

Coverage exceptions and rationale: none. The catalog covers two well-formed,
two ambiguous/contradictory, two brand/policy-sensitive, one article-derived,
and one edge case. No case has participant execution evidence yet.

`CASE_PREPARED` confirms only that the input packet is usable. The validation
round remains blocked until the controlled setup, participants, restricted
evidence location, and `review-candidate commit` SHA below are recorded.

## Participant coverage

Use opaque participant IDs only. Keep names, contact details, consent records,
and raw notes in the declared restricted evidence location.

| Participant | Persona / role | Direction-owner coverage | Business / brand / production approval coverage | Decision authority | Consent evidence ID | Session date | Status |
|---|---|---:|---:|---|---|---|---|
| U-01 | Jarkius; actual role Designer/Content Producer + Reviewer/Approver, not Creative Lead | Designer/Content Producer | Reviewer/Approver | Accountable product owner | not recorded (in-session, no formal consent artifact) | 2026-08-02 | Active |

Under the 2026-07-26 solo-round scope revision, only U-01 (Jarkius) is in
scope for this round. The original 2–3-participant target (U-02, U-03) is
deferred to the post-build pilot, not tracked here.

**Persona-fit finding:** the case catalog's default case order assumes a
Creative Lead / marketing-campaign persona. U-01's real workflow is AI/tech
news curation into a single social image (no marketing-campaign work), which
matches Designer/Content Producer and Reviewer/Approver, not Creative Lead.
Case selection for this participant must favor article-derived cases
(`VC-07`) over campaign-brief cases (`VC-01`–`VC-06`) going forward.

## Controlled setup

- Facilitator: Claude (Sonnet 5, this session), not Jarkius, for sessions
  `S-U01-C01-01` and `S-U01-C07-01`. This is a deviation from the facilitator
  identity originally declared above and is disclosed rather than corrected
  retroactively; see "Pre-session authorization gate" below for the
  consequence.
- Baseline workflow and allowed tools (participant's real current workflow,
  captured once and reused across sessions): Gemini for image-prompt
  drafting, ChatGPT image generation for rendering; ~5–10 minutes total,
  typically 2–3 regenerations per brief; baseline direction usefulness 3/5;
  baseline rationale clarity 5/5. Baseline rework trigger: generated output
  frequently disconnects from the literal content requirement (e.g. a
  product/model name intended as key visual text renders as an abstract
  image instead).
- Proposed-workflow tools, model/provider versions, and settings: not
  applicable — no Motiflow implementation exists; sessions were manual
  walkthroughs of the documented workflow specification only, per
  `VALIDATION_SESSION_INSTRUMENTS.md` section 3.
- Timing rule and pause handling: `VALIDATION_SESSION_INSTRUMENTS.md` section 4.
  Not applied with stopwatch precision in these sessions — conducted as a
  real-time chat conversation, not an in-person timed session. Recorded as a
  known limitation, not a fabricated timing value.
- Pre-generation constraint-sufficiency check revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 8
- Deterministic review checklist revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 9
- Focused critic rubric revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 10
- `review-candidate commit` SHA: `efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`
- `review-candidate commit` presentation status: presented to the participant
  in the two sessions below via the case catalog content only (VC-01, VC-07);
  full ten-artifact contract chain was not exercised end-to-end in either
  session because both stopped before Generation Specification.

## Pre-session authorization gate

Do not schedule or run a session until every item is checked. `CASE_PREPARED`
does not satisfy this gate.

- [x] Accountable product owner and facilitator are named.
- [x] One participant ID (Jarkius, per the 2026-07-26 solo-round scope
  revision), role coverage, and session date are recorded (see Participant
  coverage above). Consent evidence ID is not recorded — see deviation note
  below. The 2–3-participant target is deferred to the post-build pilot.
- [ ] Restricted evidence location, access owner, and retention/deletion rule
  are recorded outside this public packet.
- [x] Baseline tools, versions, and settings are frozen (participant's real
  current workflow; recorded above). Proposed-workflow tools are not
  applicable — no implementation exists.
- [x] The `review-candidate commit` exists and its SHA is recorded consistently in
  this report and the contract-acceptance packet.
- [x] The `trace-preparation commit` records the candidate SHA across the
  readiness packet before the first participant session.
- [x] Only synthetic case-catalog material (`VC-01`, `VC-07`) was used; no
  confidential or real client material entered the session.

**Session authorization:** `CONDITIONALLY_RUN — gate was not fully satisfied
before sessions started`

**Disclosed deviation:** Two sessions (`S-U01-C01-01`, `S-U01-C07-01`) ran
before the restricted evidence location and a formal consent record were in
place, and with Claude (not Jarkius) acting as facilitator. This is recorded
as a deviation, not corrected retroactively by editing the gate checklist to
look clean. Per `MEOS/13_REVIEW_STANDARD.md` and this project's established
pattern for residual risk (see `docs/03-delivery/BLUEPRINT_RECONCILIATION_REVIEW.md`
§12), a disclosed limitation with an explicit acceptance decision is
preferable to a silently corrected record. **This deviation has not yet been
formally accepted by Jarkius as accountable product owner** — that
acceptance, or a decision to discard/rerun these two sessions under a
compliant gate, is outstanding and blocks this round's exit criteria
independent of the two-gate comprehension finding below.

Jarkius holds the Product owner, Facilitator, Chief Architect, and Engineering
lead roles for this round. This records identity only; it is not consent,
participant evidence, a product decision, contract disposition, approval, or
signature. Under the MEOS
[`Separation of Duties`](../../../MEOS/01_ENGINEERING_CONSTITUTION.md#14-separation-of-duties)
and [`Review Standard`](../../../MEOS/13_REVIEW_STANDARD.md#2-independence-and-separation-of-duties),
self-review is not independent approval. Independent Reviewer and QA identities
and evidence remain `PENDING` and are required before readiness can pass; no
second human is inferred.

Post-session revision requirement: the later `evidence/sign-off commit` must
record actual evidence, dispositions, decision links, and signatures. A signed
tag may identify it after verification but does not replace it. This is a
completion requirement, not a pre-session condition.

## Session run sheets

Create one row per participant/input session. Add rows as required. Every input
must appear at least once, every participant must appear at least twice, and at
least two inputs must include distinct direction-owner and approval perspectives.

| Session | Participant | Case | Baseline direction minutes | Baseline total minutes | Baseline direction revisions | Baseline candidate revisions | Baseline usefulness 1–5 | Baseline rationale clarity 1–5 | Proposed direction minutes | Proposed total minutes | Direction revisions | Candidate revisions | Usefulness 1–5 | Rationale clarity 1–5 | Final confidence 1–5 | Approval/provenance confidence 1–5 | Two-gate comprehension | Clarifications | Facilitator interventions | Stop record ID | Outcome |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|---|---|
| S-U01-C01-01 | U-01 | VC-01 | 5–10 | 5–10 | 2–3 | n/a | 3 | 5 | not applicable | not applicable | not applicable | not applicable | not assessed | not assessed | not assessed | not assessed | not assessed | 0 | 1 (case-fit stop) | `VST-S-U01-C01-01` | stopped — persona/case mismatch, before case content was actioned |
| S-U01-C07-01 | U-01 | VC-07 | 5–10 | 5–10 | 2–3 | n/a | 3 | 5 | not recorded (chat-based session, no stopwatch) | not applicable — never reached final approval | 1 (`revision_requested`) | not applicable | not assessed (case stopped before an image existed to rate) | not assessed | not applicable | not applicable | fail — conflated direction and final approval | 1 (missing style/hook) | 0 | none — reached `requires_revision`, not a `VST-*` stop | revision_requested at pre-generation constraint-sufficiency check |

## Valid-stop records

Complete one row for every `VST-*` referenced by a session. A blank stop record
ID means the session did not stop under the protocol.

| Stop record ID | Session | Last valid stage | Blocking reason | Classification (`protocol` or `participant`) | Useful failure evidence (`yes` or `no`) | Reviewer and rationale |
|---|---|---|---|---|---|---|
| `VST-S-U01-C01-01` | S-U01-C01-01 | Baseline capture complete; case presented, not yet actioned | Case `VC-01`'s primary personas (Creative Lead, marketing-campaign context) do not match this participant's real workflow (AI/tech-news curation to single social image) | protocol | yes | not yet independently reviewed; facilitator (Claude) identified the mismatch before the participant was asked to act on unfit content |

## Friction and decisions

| Finding | Session / case | Stage | Severity | In MVP scope? | Evidence | Decision (`keep/change/defer/remove`) | Owner | Status |
|---|---|---|---|---|---|---|---|---|
| F-01 | S-U01-C01-01 / VC-01 | Case selection | medium | yes — case-selection logic, not workflow contracts | `VST-S-U01-C01-01` | change — case-to-participant matching should account for the participant's actual role, not default to Creative Lead cases | Product owner | open |
| F-02 | S-U01-C07-01 / VC-07 | Pre-generation constraint sufficiency | medium | yes — Creative Direction Package content | this report, VC-07 session row | change — packet-level style/visual-hook guidance is under-specified for article-derived cases; consider adding a style/hook field to the article-derived packet shape | Product owner | open |
| F-03 | S-U01-C07-01 / VC-07 | Gate comprehension | high | yes — two-gate model is a core decisive-slice contract | this report, VC-07 session row (direction/final approval answered "mostly same") | change — the two-gate distinction was not self-evident to this participant from doing the workflow once; needs either clearer in-session explanation or a structural simplification, before assuming `at least 80%` unprompted comprehension is achievable | Product owner / Chief architect | open |
| F-04 | S-U01-C07-01 / VC-07 | Closing feedback | low | yes — production-readiness of the direction package | this report, VC-07 closing answers (taste/color/tone/composition unclear; image-to-content layout and icon integration untrusted) | defer — visual-style vocabulary and layout/typographic integration are below the current artifact language's stated scope; record as a candidate contract gap for Phase 2 rather than blocking this round | Product owner | open |
| F-05 | S-U01-C01-01, S-U01-C07-01 | Session setup | medium | no — process/governance, not product content | Controlled setup and Pre-session authorization gate sections above | change — sessions ran with Claude as facilitator and without a completed restricted-evidence-location/consent setup; requires explicit product-owner acceptance or a compliant rerun before this round's evidence can support a `PROCEED` decision | Product owner | open |

## Architecture and engineering review evidence

This review is separate from intended-user sessions. Product participants do
not need to understand or approve all ten internal contracts.

| Reviewer ID | Role | `review-candidate commit` SHA | Ten-artifact boundaries | Versioned lineage and freshness | Approval/schema semantics | Findings evidence ID | Disposition |
|---|---|---|---|---|---|---|---|
| AR-01 | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |
| ER-01 | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |

## Aggregate evidence

| Measure | Baseline | Proposed workflow | Change | Denominator / `n` | Exit threshold | Result |
|---|---:|---:|---:|---|---|---|
| Median time to approved direction | 5–10 min (n=2, same baseline reused) | not computable — zero sessions reached an approved direction | not computable | n=0 (no approved-direction sessions) | measurable improvement | not met — no session has an approved direction yet |
| Median end-to-end time to final outcome | 5–10 min | not computable — zero sessions reached final outcome | not computable | n=0 | report; improvement preferred | not met |
| Median direction revisions | 2–3 (baseline) | not computable — no direction was approved to count post-approval revisions against | not computable | n=0 | report; improvement preferred | PENDING |
| Median candidate revisions | n/a (baseline has no candidate-review step) | not applicable — no session reached candidate generation | not applicable | n=0 | report; improvement preferred | PENDING |
| Median direction usefulness | 3/5 | not assessed — no Creative Direction Package was rated for usefulness in either session | not computable | n=0 | report; improvement required in at least one operational measure | PENDING |
| Median rationale clarity | 5/5 | not assessed | not computable | n=0 | report; improvement required in at least one operational measure | PENDING |
| Sessions rating usefulness or clarity 4–5 | n/a | 0 of 2 sessions reached a rating point | n/a | 0/2 | at least 70% | not met (denominator too small and no rating point reached) |
| Unprompted two-gate comprehension | n/a | 0 of 1 assessed passed | n/a | 0/1 | at least 80%; every participant assessed; no persistent conflation | **fail** — the one comprehension assessment conducted resulted in conflation (F-03) |
| Cases completed without undocumented fields | n/a | 0 of 2 cases completed (1 stopped, 1 sent to revision) | n/a | 0/2 completed | 100% of completed cases | not applicable — no case reached completion |
| Critical/high vocabulary or contract conflicts open | n/a | 1 (two-gate conflation, F-03) plus 1 case-selection gap (F-01) | n/a | — | 0 | **not met** |

Per-role variance and interpretation: not assessable with a single participant and n=2 sessions; the plan's original 2–3-participant target (deferred to the post-build pilot) exists partly to make this measure meaningful.

**Interim read:** with only 2 of the minimum 5 required sessions run, and zero
approved directions, most quantitative exit thresholds are not yet
computable — this is expected at this stage, not a failure of the round
itself. The one measure that *is* computable from what we have — unprompted
two-gate comprehension — failed outright (F-03), which is independently
sufficient to keep this round below the exit bar regardless of how the
remaining sessions turn out.

## Exit-criteria evidence

- [ ] 5–10 input cases reach recorded terminal outcomes; a stopped case counts
  only when its failure is evaluated and documented. **2 of the minimum 5
  recorded** (`S-U01-C01-01` stopped, `S-U01-C07-01` sent to
  `revision_requested`); neither reached full completion.
- [ ] 1 intended user (Jarkius, the accountable product owner) participated
  under the recorded 2026-07-26 solo-round scope revision with required role
  coverage. **Participated, but under a disclosed gate deviation** (see
  Pre-session authorization gate above) requiring product-owner acceptance
  before this counts as satisfying the criterion. The original 2–3-user
  target remains the standard for the post-build pilot, not this round.
- [ ] Baseline and proposed-workflow measures are complete. **Baseline
  complete; proposed-workflow measures not computable** — see Aggregate
  evidence above.
- [ ] Gate-comprehension threshold passes. **Fails** — the one assessment
  conducted resulted in conflation (F-03).
- [ ] Artifact sufficiency threshold passes. **Not assessed** — neither
  session reached artifact generation.
- [ ] Usefulness/value threshold passes. **Not assessed** — no direction was
  rated for usefulness in-session.
- [ ] Critical and high vocabulary or contract findings are resolved.
  **Open** — F-01 through F-04 remain open.
- [ ] Assumptions, rejected stages, and deferrals are dispositioned.
- [ ] [`../../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) is accepted by the required humans.

This round is **not** ready for a `PROCEED` decision. It is partial evidence
toward the minimum sample, with one confirmed gate-comprehension failure and
an unresolved gate-deviation disclosure.

## Product-owner decision

- Accountable product owner: Jarkius
- Decision: `PENDING`
- Rationale tied to evidence: PENDING
- Approved decisive-slice scope: PENDING
- Explicit exclusions: PENDING
- Constraints or required corrections: PENDING
- Rerun scope if `REVISE`: PENDING
- Reviewed `review-candidate commit` SHA: PENDING
- Name / role / date: Jarkius / Product owner / PENDING

## Report integrity

Prepared by: Codex documentation review, 2026-07-25; structurally revised
2026-07-26 using the Asia/Bangkok workspace clock; session evidence for
`S-U01-C01-01` and `S-U01-C07-01` added 2026-08-02 by Claude (Sonnet 5,
facilitator role) from a real-time conversational session with Jarkius
(participant, U-01).
Preparation evidence: repository inspection plus 2 real participant sessions
conducted 2026-08-02. This is genuine participant evidence, not synthetic or
AI-generated evidence presented as participant evidence — Jarkius supplied
every baseline figure, case reaction, and rating recorded above.
Known limitations, disclosed rather than corrected retroactively:
- sessions ran with Claude as facilitator, not Jarkius as originally declared
  in Controlled setup;
- the restricted evidence location and a formal consent artifact were not in
  place before sessions started;
- timing was self-reported in a chat conversation, not stopwatch-measured;
- only 2 of the minimum 5 required sessions have been run;
- `VC-01` was presented to a participant whose real workflow does not match
  its primary personas, before the mismatch was caught (see F-01,
  `VST-S-U01-C01-01`).
This report does not claim readiness to proceed. It records partial genuine
evidence and an unresolved gate-deviation disclosure requiring product-owner
acceptance before further sessions or a `PROCEED`/`REVISE`/`STOP` decision.
