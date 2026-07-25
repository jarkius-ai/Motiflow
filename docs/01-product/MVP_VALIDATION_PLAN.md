# MVP Validation Plan

**Status:** Required pre-implementation evidence plan
**Owner:** Product
**Scope:** Validate the creative-direction-first workflow before broad platform implementation

This is the **readiness-to-build validation gate**. It is distinct from the
post-build controlled pilot in [`SUCCESS_METRICS.md`](SUCCESS_METRICS.md), which
measures product outcomes after an executable slice exists.

## Decision to validate

Motiflow's first decisive slice transforms a brief or source article into an explainable creative direction, obtains explicit human direction approval, compiles a Generation Specification, produces candidates through one provider, applies focused critics, and records explicit human final approval with provenance.

This plan does not validate article authoring, SEO adaptation, social variants, CMS publishing, full publication-platform behavior, multi-provider optimization, or an SDK ecosystem.

## Participants and inputs

- 2–3 intended users or design partners representing creative, content, or approval roles
- 5–10 representative briefs or source articles
- at least one ambiguous input that requires clarification
- at least one brand- or policy-sensitive input

Participant coverage must include:

- at least one person who owns or creates creative direction; and
- at least one person who approves business, brand, or production outcomes.

A participant may cover more than one role, but the report must identify the
overlap as reduced evidence for handoff behavior.

## Evidence audiences

Intended users or design partners provide product evidence. They assess brief
and direction usefulness, rationale clarity, gate comprehension, candidate
review, and confidence in approval/provenance records. They do not need to
understand all ten internal artifacts, envelope fields, lineage mechanics, or
schema semantics.

Named architecture and engineering reviewers provide contract evidence. They
review all ten internal artifact boundaries, versioned lineage, approval
references, schema semantics, and validator feasibility. Reviewer evidence is
recorded separately and never counted as intended-user participation.

Every input must be anonymized and tagged by source type, channel, completeness,
ambiguity, sensitivity, and expected decision difficulty. Articles are source
material for brief normalization and creative direction only; article editing,
publication review, CMS export, and social adaptation are not part of this gate.
Use eight inputs by default. A set of five to ten is acceptable only when it
includes:

- two well-formed briefs;
- two ambiguous, incomplete, or contradictory briefs;
- two brand- or policy-sensitive briefs; and
- one article-derived brief when article source material is expected in the pilot.

One input may satisfy multiple coverage requirements. The report must explain
any omitted category.

The session matrix need not be a full participant-by-input cross-product. Every
input must be completed by at least one participant, every participant must
complete at least two inputs, and at least two inputs must be reviewed across
different direction-owner and approval perspectives to exercise the handoff.

## Readiness before the first session

Do not start fieldwork until the validation report records:

- an accountable product owner;
- participant IDs, role coverage, consent status, and scheduled sessions;
- input IDs and coverage tags;
- the facilitator and allowed manual or generation tools;
- the external location for restricted raw notes and source material; and
- the review-candidate commit SHA being presented. Create that candidate commit
  first, then record its SHA in a later evidence/sign-off commit or equivalent
  signed tag; do not require a commit to contain its own SHA.

Use the dated evidence record at
[`validation/2026-07-25-mvp-validation-report.md`](validation/2026-07-25-mvp-validation-report.md)
for the current round. Create a new dated report rather than overwriting a
completed round.

The prepared round inputs and standard instruments are:

- [`validation/VALIDATION_CASE_CATALOG.md`](validation/VALIDATION_CASE_CATALOG.md)
  — eight synthetic, anonymized cases with required coverage; and
- [`validation/VALIDATION_SESSION_INSTRUMENTS.md`](validation/VALIDATION_SESSION_INSTRUMENTS.md)
  — facilitator script, timing rules, rating anchors, deterministic checklist,
  focused critic rubric, evidence IDs, and aggregation rules; and
- [`validation/VALIDATION_ARTIFACT_WORKSHEETS.md`](validation/VALIDATION_ARTIFACT_WORKSHEETS.md)
  — provisional human-readable worksheets for testing the sufficiency of all
  ten artifacts before schema implementation; and
- [`validation/2026-07-26-validation-instrument-dry-run.md`](validation/2026-07-26-validation-instrument-dry-run.md)
  — a difficult-case desk check of the instruments that carries no participant
  evidence credit.

These artifacts complete session preparation only. They are not participant
evidence and do not satisfy an execution or approval gate.

## Manual validation protocol

Run the same protocol, facilitator guidance, rating scales, and allowed tools for
each comparable session. Record facilitator interventions; repeated hidden
interpretation is evidence that an artifact or instruction is insufficient.

1. Record the participant's current workflow, baseline time, revision count, and tool set.
2. Normalize the input into the proposed canonical fields and record every clarification.
3. Produce a Knowledge Fusion Package and Creative Direction Package manually or with the declared tools.
4. Run the pre-generation constraint-sufficiency check. Record
   `revision_requested` when constraints require correction, or create a valid
   stop record when constraint insufficiency prevents a safe evaluation.
5. Only when the check returns `safe_to_generate`, ask the participant to
   approve, reject, or request revision of the direction.
6. Ask the participant to explain the purpose and output of direction approval in their own words.
7. For an approved direction, create a Generation Specification and candidate set using the declared rendering tool or provider.
8. Apply the proposed deterministic checks and focused critic rubric.
9. Ask the participant to approve, reject, or request revision of the candidate
   set; record selected candidate IDs only when the decision is approved.
10. Ask the participant to explain how final-candidate approval differs from direction approval.
11. Capture timing, revisions, ratings, friction, missing information, unnecessary stages, vocabulary confusion, and facilitator interventions.

Stop a case when consent is withdrawn, restricted information cannot be handled
safely, an approval would be fabricated, or the artifact chain cannot proceed
without inventing a material requirement. Record the last valid stage and reason.

## Required measures

- baseline time to approved direction;
- baseline direction revision count;
- baseline direction usefulness rating;
- baseline rationale clarity rating;
- time to approved direction;
- direction revision count;
- direction usefulness rating;
- rationale clarity rating;
- clarification frequency;
- final-candidate revision count;
- confidence in the final approval decision;
- participant confidence in approval and provenance records.

Use a five-point scale for usefulness, rationale clarity, final-approval
confidence, and confidence in approval/provenance records:

| Rating | Anchor |
|---:|---|
| 1 | unusable or actively misleading |
| 2 | major gaps; not safe to use without rework |
| 3 | usable with material clarification or revision |
| 4 | useful and clear with only minor changes |
| 5 | immediately useful, clear, and decision-ready |

Gate comprehension passes only when the participant can state that direction
approval freezes the current Creative Direction Package before generation, while
final approval evaluates the current candidate set plus critic findings before
export. Prompting or correcting the answer makes the result a failure for that
session.

## Exit criteria

The first implementation task may be marked ready only when:

- 5–10 inputs reach a recorded terminal outcome with 2–3 intended users; a stopped case counts only when its failure is itself evaluated and documented, and the round must still contain at least five such outcomes;
- at least 80% of unprompted gate-comprehension checks pass, and no participant leaves both gates conflated after review;
- the product-facing brief, direction, gates, candidate review, and
  approval/provenance records are sufficient for every completed participant
  case, with no undocumented required field or facilitator-created handoff;
- architecture and engineering reviewers find all ten internal artifact
  boundaries, versioned lineage, approval references, and schema semantics
  review-ready without implementer invention;
- all critical and high-severity vocabulary or contract conflicts are resolved;
- baseline and proposed-workflow measurements are recorded for every completed case;
- at least 70% of completed sessions rate direction usefulness or rationale clarity at 4 or 5, and at least one operational measure improves against baseline;
- unresolved assumptions and rejected workflow stages are documented;
- required reviewers accept the two-gate workflow, canonical vocabulary, artifact envelope, approval references, and first contract-proof scope; and
- an accountable product owner records a proceed, revise, or stop decision.

## Evidence record

Store anonymized findings, baseline values, workflow changes, and the product-owner decision in a dated validation report. Do not place confidential source material or participant data in the repository.

The report must contain:

- input and participant coverage matrices;
- one run sheet per participant/input session;
- aggregate measures and per-role variance;
- an assumption and workflow-change decision log;
- references to external raw evidence by opaque ID only;
- the contract-review decision; and
- the named product-owner `PROCEED`, `REVISE`, or `STOP` decision, rationale,
  constraints, date, and reviewed candidate SHA.

`PROCEED` requires every exit criterion and mandatory human review to pass.
`REVISE` requires named changes and a rerun scope. `STOP` records why the wedge
does not justify implementation. A numerical score never overrides a failed
mandatory gate.
