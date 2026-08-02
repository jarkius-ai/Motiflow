# MVP Validation Report — 2026-07-25 Round

**Status:** Open; preparation and participant evidence pending
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
| U-01 | PENDING (Jarkius, solo-round) | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |

Under the 2026-07-26 solo-round scope revision, only U-01 (Jarkius) is in
scope for this round. The original 2–3-participant target (U-02, U-03) is
deferred to the post-build pilot, not tracked here.

## Controlled setup

- Facilitator: Jarkius
- Baseline workflow and allowed tools: PENDING
- Proposed-workflow tools, model/provider versions, and settings: PENDING
- Timing rule and pause handling: `VALIDATION_SESSION_INSTRUMENTS.md` section 4
- Pre-generation constraint-sufficiency check revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 8
- Deterministic review checklist revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 9
- Focused critic rubric revision: `VALIDATION_SESSION_INSTRUMENTS.md` section 10
- `review-candidate commit` SHA: `efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`
- `review-candidate commit` presentation status: PENDING; no participant session has occurred

## Pre-session authorization gate

Do not schedule or run a session until every item is checked. `CASE_PREPARED`
does not satisfy this gate.

- [x] Accountable product owner and facilitator are named.
- [ ] One participant ID (Jarkius, per the 2026-07-26 solo-round scope
  revision), role coverage, consent evidence ID, and session date are
  recorded. The 2–3-participant target is deferred to the post-build pilot.
- [ ] Restricted evidence location, access owner, and retention/deletion rule
  are recorded outside this public packet.
- [ ] Baseline and proposed tool names, versions, and settings are frozen.
- [x] The `review-candidate commit` exists and its SHA is recorded consistently in
  this report and the contract-acceptance packet.
- [x] The `trace-preparation commit` records the candidate SHA across the
  readiness packet before the first participant session.
- [ ] The facilitator confirms that only synthetic or authorized anonymized
  input material will be used.

**Session authorization:** `BLOCKED`

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
| S-01 | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |

## Valid-stop records

Complete one row for every `VST-*` referenced by a session. A blank stop record
ID means the session did not stop under the protocol.

| Stop record ID | Session | Last valid stage | Blocking reason | Classification (`protocol` or `participant`) | Useful failure evidence (`yes` or `no`) | Reviewer and rationale |
|---|---|---|---|---|---|---|
| PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |

## Friction and decisions

| Finding | Session / case | Stage | Severity | In MVP scope? | Evidence | Decision (`keep/change/defer/remove`) | Owner | Status |
|---|---|---|---|---|---|---|---|---|
| F-01 | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING | PENDING |

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
| Median time to approved direction | PENDING | PENDING | PENDING | PENDING | measurable improvement | PENDING |
| Median end-to-end time to final outcome | PENDING | PENDING | PENDING | PENDING | report; improvement preferred | PENDING |
| Median direction revisions | PENDING | PENDING | PENDING | PENDING | report; improvement preferred | PENDING |
| Median candidate revisions | PENDING | PENDING | PENDING | PENDING | report; improvement preferred | PENDING |
| Median direction usefulness | PENDING | PENDING | PENDING | PENDING | report; improvement required in at least one operational measure | PENDING |
| Median rationale clarity | PENDING | PENDING | PENDING | PENDING | report; improvement required in at least one operational measure | PENDING |
| Sessions rating usefulness or clarity 4–5 | n/a | PENDING | n/a | PENDING | at least 70% | PENDING |
| Unprompted two-gate comprehension | n/a | PENDING | n/a | PENDING | at least 80%; every participant assessed; no persistent conflation | PENDING |
| Cases completed without undocumented fields | n/a | PENDING | n/a | PENDING | 100% of completed cases | PENDING |
| Critical/high vocabulary or contract conflicts open | n/a | PENDING | n/a | PENDING | 0 | PENDING |

Per-role variance and interpretation: PENDING

## Exit-criteria evidence

- [ ] 5–10 input cases reach recorded terminal outcomes; a stopped case counts
  only when its failure is evaluated and documented.
- [ ] 1 intended user (Jarkius, the accountable product owner) participated
  under the recorded 2026-07-26 solo-round scope revision with required role
  coverage. The original 2–3-user target remains the standard for the
  post-build pilot, not this round.
- [ ] Baseline and proposed-workflow measures are complete.
- [ ] Gate-comprehension threshold passes.
- [ ] Artifact sufficiency threshold passes.
- [ ] Usefulness/value threshold passes.
- [ ] Critical and high vocabulary or contract findings are resolved.
- [ ] Assumptions, rejected stages, and deferrals are dispositioned.
- [ ] [`../../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) is accepted by the required humans.

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
2026-07-26 using the Asia/Bangkok workspace clock
Preparation evidence: repository inspection; no participant or human-acceptance
evidence was available.
Known limitation: this report records an executable protocol and evidence gaps;
it does not claim that field validation occurred.
