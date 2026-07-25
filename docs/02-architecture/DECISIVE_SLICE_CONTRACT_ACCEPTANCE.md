# Decisive-Slice Contract Acceptance

**Status:** Review-ready; human acceptance pending
**Owner:** Product and Chief Architect
**Scope:** Pre-implementation freeze for the ten-artifact, two-gate MVP contract
**Related authority:** [`DATA_CONTRACTS.md`](DATA_CONTRACTS.md), [`RUNTIME_CONTRACTS.md`](RUNTIME_CONTRACTS.md), [`WORKFLOW_STATE_MACHINE.md`](WORKFLOW_STATE_MACHINE.md), [`VERSIONING_AND_COMPATIBILITY.md`](VERSIONING_AND_COMPATIBILITY.md), [`../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md)
**Preparation base revision:** `df7af54`
**`review-candidate commit` SHA:** `efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`; committed and awaiting human review evidence
**`trace-preparation commit`:** RECORDED; records the candidate SHA only
**`evidence/sign-off commit`:** PENDING; required after actual review and acceptance decisions

## Acceptance rule

This record is accepted only when every decision below has one disposition,
required corrections are merged, and the named product and architecture owners
sign the resulting revision. Review-ready status is not acceptance.

Allowed dispositions are `ACCEPT`, `REVISE`, and `REJECT`. `PENDING` blocks the
first implementation task. A comment, meeting, or chat acknowledgement does not
count unless it is transcribed into the sign-off section with the reviewed
revision.

Revision recording follows the three stages governed by
[`MVP_VALIDATION_PLAN.md`](../01-product/MVP_VALIDATION_PLAN.md): the
`review-candidate commit` freezes the review packet without attempting to
contain its own SHA; the `trace-preparation commit` records that SHA while
leaving unobserved evidence and decisions pending; and, after human review, the
`evidence/sign-off commit` records actual decision links, dispositions, and
signatures against the `review-candidate commit` SHA. A signed tag may identify the verified
`evidence/sign-off commit`, but does not replace it. No file must contain the
SHA of the commit that first introduces that same file content.

## Review surface

The review freezes only:

1. the ten canonical decisive-slice artifact names and order;
2. the two non-bypassable human gates;
3. the canonical v1 artifact envelope and approval-reference shape proposed in [`ADR-0003`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md);
4. downstream invalidation and lineage rules;
5. initial schema-versioning and unknown-field behavior; and
6. the scope and location of the first schema/fixture validation proof.

Provider selection, workflow runtime implementation, persistence, UI, article
authoring, publication packaging, CMS behavior, and platform expansion are not
part of this acceptance.

## Decision register

### C-01 — Canonical vocabulary and order

**Proposed decision:** Accept exactly:

`Intake Package` → `Normalized Brief` → `Knowledge Fusion Package` →
`Creative Direction Package` → `Direction Approval Record` →
`Generation Specification` → `Generated Candidate Set` →
`Critic Evaluation Package` → `Final Approval Record` → `Provenance Record`.

Legacy aliases are migration inputs only. `Publication Package` is post-MVP.

**Disposition:** `PENDING`
**Required correction:** PENDING or none

### C-02 — Two human gates

**Proposed decision:** Direction approval must reference the current Creative
Direction Package before generation. Final approval must reference the current
Generated Candidate Set and Critic Evaluation Package before export. Neither
gate may be inferred from successful execution or critic scores.

**Disposition:** `PENDING`
**Required correction:** PENDING or none

### C-03 — Canonical artifact envelope

**Conflict requiring decision:** The current sources define incompatible shapes:

- `DATA_CONTRACTS.md` uses a flat JSON envelope with `artifact_id`,
  `artifact_type`, `workflow_run_id`, plural `parent_artifact_ids`, `created_by`,
  and level-based confidence.
- `RUNTIME_CONTRACTS.md` wraps fields under `artifact`, uses `id`, `type`,
  `run_id`, singular `parent_artifact_id`, `producer`, validation metadata, and
  three numeric confidence dimensions.
- `SYSTEM_DESIGN.md` contains a third illustrative shape using `package_id`,
  `package_type`, `source_packages`, and score-based confidence.

**Recommended decision:** Adopt the proposed canonical shape in
[`ADR-0003`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md):
a flat top-level artifact envelope that keeps `DATA_CONTRACTS.md` field naming
for identity, replaces versionless parent IDs with versioned
`parent_artifact_refs` entries containing `artifact_id`, `artifact_type`, and
`artifact_version`, incorporates the richer `producer`, `confidence`,
`provenance`, and `validation` subobjects from `RUNTIME_CONTRACTS.md`, and
treats the `SYSTEM_DESIGN.md` package example as illustrative only.
`created_by` contains only `type` and `id`; role stays under approval
`payload.actor`. No schemas may be generated from any current example until
human approval is recorded.

**Disposition:** `PENDING`
**Selected shape or corrections:** PENDING

### C-04 — Approval decisions and reference cardinality

**Conflict requiring decision:** `RUNTIME_CONTRACTS.md` defines one
`artifact_ref`, but final approval requires both a candidate set and critic
package. It also lists `waived` while the state machine describes both gates as
non-bypassable.

**Recommended decision:** Use the proposed approval contract in
[`ADR-0003`](../adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md):
approval records carry a non-empty `artifact_refs` array, direction approval
references exactly one current Creative Direction Package, final approval
references exactly one current Generated Candidate Set and one current Critic
Evaluation Package, and the MVP decision set is `approved`, `rejected`, and
`revision_requested`. `waived` is removed from the canonical decisive-slice
contract and contained, if needed at all, as migration-only legacy input outside
the MVP schema and validator happy path.

Task 001 proves only that an approval actor is structurally human and that
`created_by.id == payload.actor.actor_id`. Project-role and gate-authorization
policy for `payload.actor.actor_role` is deferred to runtime authorization work;
it is not part of C-06 or the schema proof.

**Disposition:** `PENDING`
**Selected shape or corrections:** PENDING

### C-05 — Schema and unknown-field policy

**Proposed decision:** Initial schemas use JSON Schema 2020-12 and semantic
version `1.0.0`. Decision-bearing objects reject unknown properties. Explicit
extension objects, if accepted, must be non-decision-bearing and namespaced.
Structural validation is followed by semantic lineage and gate validation.

**Disposition:** `PENDING`
**Required correction:** PENDING or none

### C-06 — First contract-proof scope and command

**Proposed decision:** The first implementation task owns exactly four
deliverables:

- ten canonical artifact schemas plus shared definitions under `packages/schemas/`;
- deterministic valid and invalid fixtures under `evaluations/fixtures/decisive-slice/`; and
- one stable entrypoint: `./tools/validate-decisive-slice-contracts`; and
- one minimal CI workflow that installs locked dependencies and invokes that
  same entrypoint.

The entrypoint must not require a network connection after dependencies are
installed and must return non-zero for any structural or semantic failure. The
CI deliverable is an enforcement surface only: it must not duplicate validation
logic already owned by that repository command. The
validator implementation dependency requires explicit approval in the task or
repository dependency policy before implementation begins.

**Proposed validator/toolchain:** Use a plain PHP 8.3+ CLI entrypoint with
Composer and `opis/json-schema:^2` for structural JSON Schema 2020-12
validation. Task 001 must not bootstrap Laravel or require an application
container. Keep gate, freshness, versioned lineage, and invalidation rules in a
small repository-owned semantic validator invoked by the same wrapper command. Opis
documents support for JSON Schema 2020-12 and PHP 7.4+ (PHP 8 recommended):
[`opis.io/json-schema/2.x`](https://opis.io/json-schema/2.x/). Pin the accepted
version in `composer.lock`; do not download dependencies inside the validation
command or CI validation step.

Alternatives considered for C-06 review:

- a Node/Ajv-only validator would introduce a second runtime before the
  repository has selected a Node package boundary for backend tooling; and
- a custom JSON Schema implementation would duplicate a standard validator and
  create avoidable compliance risk.

This is a reviewed proposal, not dependency approval. Approval must name the
dependency range, lockfile policy, and owner below.

**Disposition:** `PENDING`
**Approved validator/toolchain:** PENDING; proposed plain PHP 8.3+ CLI /
Composer / `opis/json-schema:^2` plus repository-owned semantic checks, without
Laravel bootstrap

## Required human sign-off

| Authority | Name | Decision | `review-candidate commit` SHA | Date | Constraints / rationale |
|---|---|---|---|---|---|
| Accountable product owner | PENDING | PENDING | PENDING | PENDING | PENDING |
| Chief architect | PENDING | PENDING | PENDING | PENDING | PENDING |
| Engineering lead | PENDING | PENDING | PENDING | PENDING | PENDING |

Product signs scope, gates, and workflow intent. Architecture signs envelope,
references, invalidation, and versioning. Engineering signs feasibility,
locations, validator/toolchain, and the single-command contract.

## Acceptance outcome

**Outcome:** `PENDING`
Allowed outcomes: `ACCEPTED | REWORK | REJECTED`

**Accepted `review-candidate commit` SHA:** PENDING
**`evidence/sign-off commit`:** PENDING; optional signed tag also pending
**Residual risks accepted by:** PENDING
**Required follow-up:** PENDING

## Checkpoint walkthrough

| Concern | Why it matters | Review stop |
|---|---|---|
| Product boundary | Prevents publication-platform scope from entering the first build | C-01, C-02 |
| Contract integrity | Prevents implementers from silently choosing among three envelopes | C-03 |
| Gate safety | Makes final approval reference all reviewed evidence and prohibits waiver ambiguity | C-04 |
| Compatibility | Fixes the dialect and unknown-field behavior before v1 schemas exist | C-05 |
| Build feasibility | Fixes ownership, command, dependency authority, and CI as thin enforcement of the one repository command | C-06 |

**Human checkpoint decision:** `APPROVE | REWORK | DIG DEEPER` — PENDING
