# Validation Artifact Worksheets

**Status:** Proposed manual-validation instrument; not an accepted runtime contract
**Owner:** Product and Architecture
**Scope:** Human-readable worksheets for testing the sufficiency of the ten-artifact decisive slice before JSON Schemas exist

Use these worksheets with the
[`VALIDATION_CASE_CATALOG.md`](VALIDATION_CASE_CATALOG.md),
[`VALIDATION_SESSION_INSTRUMENTS.md`](VALIDATION_SESSION_INSTRUMENTS.md), and
dated [`2026-07-25-mvp-validation-report.md`](2026-07-25-mvp-validation-report.md).

The worksheets deliberately remain editable during validation. A field that is
missing, confusing, redundant, or dependent on facilitator invention is a
finding, not permission to hide the gap. These worksheets do not settle the
canonical envelope proposed in
[`ADR-0003`](../../adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md)
and must not be copied into schemas until the ADR and contract packet are
accepted.

## Review audiences

Intended-user participants assess the product-facing surfaces: brief clarity,
creative-direction usefulness and rationale, distinction between the two gates,
candidate review, and confidence in approval/provenance records. They are not
required to understand all ten internal artifact boundaries or schema semantics.

Architecture and engineering reviewers complete the full ten-artifact chain,
proposed envelope, versioned lineage, approval references, and schema-semantics
review. Facilitators may capture worksheet data, but must identify which
audience supplied each finding.

## Common proposed-envelope header

Complete for every worksheet. These fields deliberately mirror the proposed
ADR-0003 envelope so reviewers can identify missing, confusing, or excessive
metadata before acceptance; their presence here does not accept the ADR.

- Session ID:
- Case ID:
- `artifact_id`:
- Artifact name:
- `artifact_type`:
- `artifact_version` (positive integer):
- `schema_version` (`manual-draft` until a schema is accepted):
- `project_id`:
- `workflow_run_id`:
- `parent_artifact_refs`: zero or more entries containing exactly
  `artifact_id`, `artifact_type`, and `artifact_version`:
- Worksheet revision:
- `source_refs` / evidence references:
- `created_by.type` (`human`, `engine`, or `system`) and `created_by.id` for the
  accountable actor:
- `producer` tool/provider/model/version, or `null` for human-only work:
- `created_at`:
- `confidence` dimensions and basis, or documented not-applicable dimensions:
- `provenance` references:
- `validation` status and findings:
- Assumptions introduced:
- Unresolved questions:
- Facilitator interventions:

## 1. Intake Package

- Raw submitted input, preserved without normalization:
- Source-material evidence IDs:
- Requested channel and deliverable, if supplied:
- Submitted audience, objective, and constraints, if supplied:
- Attachments present or missing:
- Restricted-data classification:
- Intake gaps visible to the participant:

## 2. Normalized Brief

- Communication objective:
- Intended audience:
- Business objective or success signal:
- Channel and deliverable:
- Required message/content:
- Brand constraints:
- Policy constraints:
- Prohibited elements:
- Available references:
- Missing information:
- Contradictions:
- Explicit assumptions:
- Clarification request and response:
- Ready to continue: `yes | no | needs clarification`

## 3. Knowledge Fusion Package

- Narrative findings and evidence IDs:
- Audience findings and evidence IDs:
- Business-context findings and evidence IDs:
- Brand/policy findings and evidence IDs:
- Confidence by finding:
- Material disagreements:
- Unresolved questions:
- Rejected or weakly supported claims:
- Recommended constraints carried forward:

## 4. Creative Direction Package

Fields follow `FR-005` in [`../../PRD.md`](../../PRD.md):

- Communication objective:
- Dominant narrative:
- Dominant metaphor:
- Symbolism:
- Visual hierarchy:
- Composition intent:
- Material and lighting language:
- Palette logic:
- Prohibited elements:
- Rationale with evidence IDs:
- Confidence and basis:
- Alternative considered, if any:
- Open issue blocking approval, if any:

Participant sufficiency check:

- Can the participant approve or reject direction without seeing generated candidates?
- Which field is missing, confusing, unnecessary, or too prescriptive?
- Did the facilitator add unrecorded creative interpretation?

For an approval record, `created_by.type` must be `human` and
`created_by.id` must equal `payload.actor.actor_id`; a facilitator who only
transcribes the decision is recorded under facilitator interventions, never as
the approval creator. Role stays under `payload.actor.actor_role`, not
`created_by`.

## 5. Direction Approval Record

- `payload.artifact_refs`: exactly one Creative Direction Package entry with
  `artifact_id`, `artifact_type`, and `artifact_version`:
- Gate ID: `direction_approval`
- Decision: `approved | rejected | revision_requested`
- `payload.actor.actor_id`:
- `payload.actor.actor_role`:
- Pre-generation constraint-sufficiency result and rationale:
- Rationale:
- Conditions:
- Decision timestamp:
- Current-version check:
- Downstream work authorized: `yes | no`

## 6. Generation Specification

- Approved direction reference:
- Target channel and dimensions:
- Provider-neutral subject/content specification:
- Composition and hierarchy:
- Camera/viewpoint, when applicable:
- Material and lighting treatment:
- Palette constraints:
- Required elements:
- Prohibited elements:
- Text/layout constraints:
- Accessibility or policy constraints:
- Deterministic checks required:
- Declared provider/tool adaptation:
- Fields derived beyond the approved direction, with rationale:

## 7. Generated Candidate Set

- Referenced Generation Specification ID and version:
- Candidate IDs:
- Provider/tool and version:
- Generation settings reference:
- Candidate asset evidence IDs:
- Technical metadata:
- Failed or omitted candidates and reasons:
- Reproducibility limitations:

## 8. Critic Evaluation Package

- Reviewed candidate-set ID and version:
- Deterministic findings:
- Focused critic findings:
- Affected artifact field or constraint for every finding:
- Evidence ID for every finding:
- Severity and confidence:
- Blocking status:
- Recommended action:
- Unresolved disagreement:

Use sections 9 and 10 of
[`VALIDATION_SESSION_INSTRUMENTS.md`](VALIDATION_SESSION_INSTRUMENTS.md) as the
controlling manual checklist and rubric for this round.

## 9. Final Approval Record

- `payload.artifact_refs`: exactly one Generated Candidate Set and one Critic
  Evaluation Package entry, each with `artifact_id`, `artifact_type`, and
  `artifact_version`:
- Gate ID: `final_approval`
- Decision: `approved | rejected | revision_requested`
- Selected candidate IDs, when approved:
- `payload.actor.actor_id`:
- `payload.actor.actor_role`:
- Rationale addressing blocking findings:
- Conditions:
- Decision timestamp:
- Current-version checks:
- Export authorized: `yes | no`

## 10. Provenance Record

- Ordered artifact IDs and versions from Intake Package through Final Approval Record:
- Source/evidence IDs:
- Human actor IDs and roles:
- Tools, providers, models, and versions:
- Worksheet/instruction/rubric versions:
- Direction and final approval references:
- Critic and deterministic-check references:
- Superseded or rejected paths:
- Correlation/session ID:
- Known provenance gaps:
- Reproducible export manifest possible: `yes | no`

## Intended-user sufficiency review

- Was the Normalized Brief clear enough to expose missing or contradictory
  requirements?
- Was Creative Direction useful, explainable, and approvable without seeing
  generated candidates?
- Could the participant distinguish direction approval from final approval?
- Could the participant review candidates and express an approval decision with
  adequate rationale?
- Did the approval/provenance record increase or reduce decision confidence?

## Architecture and engineering sufficiency review

- Were all ten internal artifacts distinguishable to architecture and
  engineering reviewers?
- Could both approval decisions be made without an undocumented field?
- Did every decision-relevant claim retain an evidence reference?
- Did every parent dependency carry an ID, type, and current artifact version?
- Did any worksheet duplicate another artifact without adding a distinct decision boundary?
- Which fields should be added, removed, renamed, or deferred?
- Which finding changes product scope, an architecture contract, or only facilitator guidance?
- Does the case produce a valid terminal outcome under the validation protocol?

Record every proposed worksheet change in the dated report's friction and
decision table before applying it to a later worksheet revision.
