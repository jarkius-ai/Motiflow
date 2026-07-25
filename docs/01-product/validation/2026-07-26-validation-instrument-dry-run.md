# Validation Instrument Dry Run — 2026-07-26

**Status:** Completed documentation desk check
**Evidence class:** Internal protocol verification; zero participant-evidence credit
**Scope:** Difficult-case paths, measurement fields, stop records, and contract traceability
**Execution date/timezone:** 2026-07-26, Asia/Bangkok workspace clock
**Reviewed state:** Current uncommitted review packet; rerun after the packet is frozen

## Non-claim

This is not a participant session, intended-user opinion, product-owner
decision, contract acceptance, or substitute for field validation. It records a
desk check of whether the prepared instruments can capture those things without
facilitator or implementer invention.

## Method

Trace the prepared packets for `C-03`, `C-04`, `C-06`, and `C-08` through:

1. baseline capture;
2. clarification and normalization;
3. the ten manual artifact worksheets;
4. pre-generation constraint sufficiency;
5. direction and final approval decisions;
6. valid-stop handling;
7. session logging and aggregation; and
8. ADR-0003 identity, version, authorship, lineage, and approval references.

A path fails when the facilitator would need to invent source information,
translate an undocumented decision, generate before a blocking constraint is
resolved, lose a valid-stop reason, or calculate an aggregate without a defined
denominator.

## Difficult-case trace

| Case | Intended pressure | Required protocol behavior | Desk-check result |
|---|---|---|---|
| `C-03` | Missing audience, objective, dimensions, and success criteria | State that no additional source information is available; record the unresolved field; proceed only when the gap is explicitly judged non-material, otherwise create a valid-stop record | `PASS AFTER CORRECTION` |
| `C-04` | Contradictory audiences, tones, density, and palette | Preserve contradictions; fail pre-generation sufficiency; record `revision_requested` or a valid stop without creating a Generation Specification | `PASS AFTER CORRECTION` |
| `C-06` | Policy-sensitive financial-wellness framing | Evaluate constraints before generation; unresolved high/critical policy risk blocks direction authorization and produces revision or a valid stop | `PASS AFTER CORRECTION` |
| `C-08` | Missing referenced deck, dimensions, audience, and brand context | Do not substitute or infer the dependency; record the last valid stage and an auditable `VST-*` outcome | `PASS AFTER CORRECTION` |

No row records how a real participant would respond.

## Defects found and closed

| ID | Defect | Correction | Verification surface |
|---|---|---|---|
| `DR-01` | Policy or brand insufficiency had no formal stop before generation | Added the section 8 pre-generation constraint-sufficiency check with `safe_to_generate`, `requires_revision` (which maps to `revision_requested`), and `stopped_constraint_insufficiency` outcomes | Session instruments, Direction Approval worksheet, dated report setup |
| `DR-02` | Participant-facing decision terms did not map cleanly to the proposed approval enum | Reduced both gates to approve, reject, or request revision; candidate selection is separate data on an approved final decision; `waived` has no mapping | Validation plan and facilitator script |
| `DR-03` | Baseline ratings and end-to-end timing could not be compared with the proposed workflow | Added baseline usefulness/rationale ratings, direction and total clocks, candidate revision counts, and aggregation sample sizes | Session instruments and report run sheet |
| `DR-04` | Valid stops were compressed into a generic outcome cell | Added `VST-*` evidence IDs, a linked stop-record field, and a required stop-record table | Session instruments and dated report |
| `DR-05` | Clarification behavior differed when the case packet had no answer | Added a fixed no-additional-information response and an explicit continue-or-stop rule | Facilitator script |
| `DR-06` | Manual worksheets were looser than the proposed envelope and approval reference contract | Added identity, version, authorship/producer, lineage, confidence, provenance, validation, and typed `artifact_refs` fields while keeping ADR-0003 proposed | Artifact worksheets |
| `DR-07` | Aggregates could hide non-approved or non-assessed sessions | Added `n`/denominator rules, excluded non-approved outcomes from time-to-approved medians, and required at least one full gate assessment per participant | Session instruments and report aggregate table |

## Remaining controls before fieldwork

The dry run does not clear the pre-session authorization gate. Before any real
session, the dated validation report must still record:

- the accountable product owner and facilitator;
- two or three intended-user participant IDs, role coverage, consent evidence,
  and dates;
- the restricted evidence location, access owner, and retention/deletion rule;
- frozen baseline and proposed tools, versions, and settings; and
- a committed review candidate whose SHA is recorded in the later
  evidence/sign-off commit shared by the validation and contract packets.

## Desk-check conclusion

The difficult-case paths are now internally executable without a documented
need for facilitator invention. This conclusion applies only to instrument
structure. Human usability, value, comprehension, approval confidence, product
decision, and contract acceptance remain unverified.
