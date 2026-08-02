# ADR-0003: Canonical Artifact Envelope and Approval References

- Status: Accepted
- Date: 2026-07-25 (proposed); 2026-07-26 (accepted)
- Decision owners: Jarkius (Product owner, Chief Architect, Engineering lead)
- Related task: `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`
- Supersedes: None
- Superseded by: None

## Context

The decisive-slice architecture currently exposes three incompatible artifact
shapes:

- `docs/02-architecture/DATA_CONTRACTS.md` defines a flat artifact envelope with
  `artifact_id`, `artifact_type`, `workflow_run_id`, plural
  `parent_artifact_ids`, `created_by`, and a level-based confidence object.
- `docs/02-architecture/RUNTIME_CONTRACTS.md` defines a nested envelope under
  `artifact`, renames core fields to `id`, `type`, and `run_id`, uses singular
  `parent_artifact_id`, and adds richer producer, validation, and provenance
  metadata plus a human-gate contract with singular `artifact_ref`.
- `docs/SYSTEM_DESIGN.md` includes an illustrative package example with
  `package_id`, `package_type`, `source_packages`, and score-based confidence.

Task 001 is blocked on these conflicts. The repository cannot safely define v1
schemas, fixtures, a repository validator, or CI enforcement while the decisive
slice has multiple competing artifact and approval-reference shapes.

The decision must preserve the already agreed decisive-slice boundaries:

- the ten canonical artifact names and order;
- exactly two explicit, non-bypassable human gates;
- immutable artifact versions with lineage;
- explicit distinction between human and machine authorship; and
- one repository command that proves structural and semantic contract validity,
  with CI acting only as an enforcement surface for that command.

## Decision Drivers

- One canonical artifact shape for persisted and exchanged decisive-slice
  artifacts
- Explicit support for multi-parent lineage
- Clear separation between accountable human authorship and machine/runtime
  production metadata
- Rich enough confidence, provenance, and validation metadata for future
  enforcement
- Approval records that reference all reviewed evidence without ambiguity
- Pre-implementation compatibility and migration guidance across the three
  current documents
- A rollback path that remains cheap before implementation ships

## Considered Options

### Option A: Use the flat `DATA_CONTRACTS.md` envelope as-is

Pros:

- Keeps the top-level schema simple and direct.
- Matches the likely shape of JSON fixtures and schema-generated types.
- Already supports multi-parent identity through `parent_artifact_ids`.
- Uses explicit `created_by`, which is useful for human-versus-machine
  accountability.

Cons:

- Does not yet capture the richer runtime producer and validation metadata that
  the Kernel and validator need.
- Its confidence model is less expressive than the runtime draft.
- Its parent IDs do not identify artifact type or version, so they cannot prove
  freshness or reject stale parent versions by themselves.
- It does not resolve approval-reference cardinality on its own.

### Option B: Use the nested `RUNTIME_CONTRACTS.md` envelope as-is

Pros:

- Carries stronger producer, provenance, validation, and confidence structure.
- Aligns naturally with runtime orchestration and Kernel enforcement.
- Already includes an explicit human gate contract.

Cons:

- Adds an outer `artifact` wrapper with no demonstrated decisive-slice benefit.
- Breaks cross-document naming consistency with `DATA_CONTRACTS.md`.
- Uses singular `parent_artifact_id`, which does not fit fusion or review
  artifacts that can depend on multiple upstream artifacts.
- Uses singular `artifact_ref`, which cannot represent final approval without
  inventing special-case rules.
- Includes `waived`, which conflicts with the non-bypassable gate requirement.

### Option C: Use the illustrative `SYSTEM_DESIGN.md` package shape as-is

Pros:

- Readable as a high-level example.
- Uses fewer fields and is easy to explain in system-level prose.

Cons:

- Is explicitly illustrative, not a contract source of truth.
- Uses `package_*` terminology that conflicts with the canonical artifact
  vocabulary adopted elsewhere.
- Omits required validation, approval-reference, and compatibility details.
- Cannot anchor Task 001 schemas or validator behavior without substantial
  redesign.

## Decision

Motiflow should adopt a **flat top-level canonical artifact envelope** for the
decisive slice and incorporate the richer nested metadata concepts from
`RUNTIME_CONTRACTS.md` inside named subobjects rather than behind an outer
`artifact` wrapper.

The canonical decisive-slice artifact schema should use these top-level fields:

- `artifact_id`
- `artifact_type`
- `schema_version`
- `artifact_version`
- `project_id`
- `workflow_run_id`
- `parent_artifact_refs`
- `created_at`
- `created_by`
- `producer`
- `source_refs`
- `confidence`
- `provenance`
- `validation`
- `payload`

Normative shape:

```yaml
artifact_id: art_<uuid>
artifact_type: creative_direction_package
schema_version: 1.0.0
artifact_version: 1
project_id: prj_<uuid>
workflow_run_id: run_<uuid>
parent_artifact_refs:
  - artifact_id: art_<parent_uuid>
    artifact_type: knowledge_fusion_package
    artifact_version: 2
created_at: 2026-07-25T00:00:00Z
created_by:
  type: human | engine | system
  id: <string>
producer:
  component_id: creative-director
  component_version: 0.1.0
  model_provider: null
  model_name: null
  instruction_version: null
source_refs: []
confidence:
  evidence: 85
  reasoning: 80
  creative: 75
  basis:
    - normalized_brief:communication_objective
    - knowledge_fusion:narrative_evidence
provenance:
  evidence_refs: []
  knowledge_versions: []
  correlation_id: corr_<uuid>
  causation_id: cmd_<uuid>
validation:
  status: passed
  findings: []
payload: {}
```

This recommendation resolves the current conflicts as follows.

### Multi-parent lineage

`parent_artifact_refs` is canonical and always uses an array. Every entry
contains exactly `artifact_id`, `artifact_type`, and a positive integer
`artifact_version`. Single-parent artifacts use a one-element array. Fusion,
evaluation, and approval-adjacent artifacts may reference multiple parents
without inventing per-artifact exceptions.

For every parent reference, semantic validation must prove that the artifact
exists, its stored type matches `artifact_type`, and the referenced version is
the current non-invalidated version for that dependency. An ID-only
`parent_artifact_id` or versionless `parent_artifact_ids` field is migration
input only and is not canonical output. `source_refs` remains the surface for
non-artifact source evidence; it does not substitute for versioned artifact
lineage.

### Human vs machine authorship

`created_by` contains exactly the accountable actor's `type` and `id`.
`created_by.type` is `human`, `engine`, or `system`; `created_by.id` is the
stable actor identifier. Role and authorization claims do not belong in the
envelope. `producer` records the runtime component and model/tooling details
when a machine or system materially produced the artifact.

This split avoids overloading one field with both accountability and execution
metadata:

- human-authored artifacts keep explicit human accountability in `created_by`;
- machine-produced artifacts still identify the originating engine/system in
  `created_by` and add technical production details in `producer`; and
- approvals remain explicit human records rather than inferred runtime events.

### Confidence and validation

The richer runtime concepts are retained:

- `confidence` is structured, not a single categorical level;
- `validation` is a first-class object with status and findings; and
- inapplicable confidence dimensions may be `null` only where the accepted v1
  schema explicitly permits that case.

The canonical schema should treat `confidence`, `provenance`, and `validation`
as decision-relevant contract surfaces, not illustrative annotations.

Confidence dimensions use integer percentage points from `0` through `100`.
Each dimension is either an integer in that range or `null` when the
artifact-specific schema declares the dimension inapplicable. `basis` is an
array of concise evidence or rule references and must be non-empty whenever any
numeric confidence dimension is present. There is no implicit aggregate score.
Changing this range, unit, or nullability after v1 acceptance is a breaking
contract change under `VERSIONING_AND_COMPATIBILITY.md`.

The generic envelope owns identity, lineage, authorship, production,
confidence, provenance, and validation. Artifact-specific business fields,
including approval fields, always live under `payload`. `producer` is `null`
for a purely human-created record and is an object only when a component or tool
materially produced the artifact.

### Approval records and artifact reference cardinality

Approval records must replace singular `artifact_ref` with a non-empty
`artifact_refs` array. Each entry references one concrete current artifact
version. The MVP gate contracts are:

- `direction_approval` references exactly one current
  `creative_direction_package`;
- `final_approval` references exactly one current
  `generated_candidate_set` and exactly one current
  `critic_evaluation_package`.

The normative approval payload is:

```yaml
payload:
  gate_id: direction_approval | final_approval
  decision: approved | rejected | revision_requested
  artifact_refs:
    - artifact_id: art_<uuid>
      artifact_type: creative_direction_package
      artifact_version: 1
  actor:
    actor_id: usr_<uuid>
    actor_role: creative_director
  rationale: <non-empty string>
  conditions: []
```

Each `artifact_refs` entry contains exactly `artifact_id`, `artifact_type`, and
positive integer `artifact_version`. The referenced artifact must exist, its
stored type must match `artifact_type`, and the version must be current for the
gate when the decision is evaluated. `payload.actor.actor_id` must equal the
envelope's human `created_by.id`, and the envelope must set `created_by.type:
human`. Task 001 can validate that structural and identity-equality rule only.
`actor_role` remains under `payload.actor`; whether that role is authorized for
a project or gate is deferred to runtime authorization-policy work and is
outside the schema proof. `parent_artifact_refs` expresses versioned derivation
lineage, while
`payload.artifact_refs` expresses the evidence explicitly reviewed by the human
decision; one does not substitute for the other.

The canonical MVP decisions are:

- `approved`
- `rejected`
- `revision_requested`

`waived` is removed from the canonical decisive-slice contract because the MVP
gates are non-bypassable. If historical or migration input ever contains
`waived`, it must be handled only by explicit migration logic outside the
canonical decisive-slice schema and validator happy path.

### Authority of current documents

After human acceptance, the three current documents should be reconciled with
these roles:

- `DATA_CONTRACTS.md` becomes the canonical artifact field vocabulary source.
- `RUNTIME_CONTRACTS.md` becomes the canonical runtime interaction and approval
  behavior source, but it must use the same artifact field names and
  `artifact_refs` rules.
- `SYSTEM_DESIGN.md` remains illustrative only and must use examples that are
  consistent with the accepted canonical field names.

## Consequences

Positive:

- Task 001 can define schemas, fixtures, validator rules, and CI enforcement
  against one decisive-slice artifact vocabulary.
- Multi-parent lineage and stale-parent detection are supported without
  downstream special cases.
- Human accountability and machine provenance remain explicit and separable.
- Final approval can reference all reviewed evidence without hidden coupling.
- CI can stay thin by invoking one repository validator command rather than
  re-implementing contract logic.

Negative:

- Existing review-ready docs must be reconciled together once the proposal is
  accepted.
- Some current examples will require field renames before any implementation
  lands.
- Consumers that copied the runtime draft shape would need migration before they
  could interoperate with accepted schemas.

## Risks and Mitigations

- Risk: teams implement against different draft shapes before acceptance.
  Mitigation: keep this ADR in `Proposed`, block Task 001 implementation until
  human acceptance is recorded, and do not treat any current example as schema
  source of truth (mitigation closed at acceptance on 2026-07-26).
- Risk: approval records still under-specify artifact typing or freshness.
  Mitigation: require `artifact_refs` to identify concrete current versions and
  validate gate-specific cardinality semantically, not just structurally.
- Risk: `waived` survives informally in docs or fixtures.
  Mitigation: remove it from the canonical MVP decision enum and reject it in
  decisive-slice fixtures and validator rules.
- Risk: CI grows a second validation implementation.
  Mitigation: keep CI limited to invoking the repository command
  `./tools/validate-decisive-slice-contracts` and reporting its result.

## Migration and Rollback

Migration after human acceptance:

1. Update `DATA_CONTRACTS.md`, `RUNTIME_CONTRACTS.md`, and the illustrative
   example in `SYSTEM_DESIGN.md` in one reviewed change so the documents converge
   on the accepted vocabulary. **Done 2026-08-02:** all three documents now
   state the canonical envelope and approval-reference shape as the sole
   contract text; no conflicting draft variant remains.
2. Define v1 JSON Schemas and fixtures only after those contract docs align.
3. Implement `./tools/validate-decisive-slice-contracts` as the single local and
   CI entrypoint for structural and semantic validation.
4. Add one minimal CI workflow that installs locked dependencies and invokes only
   that repository command.

Compatibility classification:

- Current conflicts are pre-implementation documentation conflicts, not accepted
  API breaks.
- Once accepted, field-name aliases such as `id`, `type`, `run_id`,
  `parent_artifact_id`, versionless `parent_artifact_ids`, `package_id`, and
  singular `artifact_ref` should be treated as migration-only inputs, not
  canonical output.

Rollback before implementation:

- Revert the reconciling documentation, schema, fixture, and validator changes in
  one change set; no production data migration should exist yet.

Rollback after implementation begins:

- Stop dependent work, supersede this ADR with a new proposed ADR, and migrate
  schemas, fixtures, validator rules, and CI together rather than partially
  reintroducing draft aliases.

## Verification

This proposal is correctly implemented only when all of the following are true:

- the accepted contract docs use one canonical artifact envelope and one
  approval-reference shape;
- Task 001 schemas and fixtures encode the accepted field names, cardinality, and
  gate rules;
- `./tools/validate-decisive-slice-contracts` passes valid fixtures and rejects
  invalid fixtures for envelope, versioned lineage, stale parent versions,
  gate-reference, actor-identity, and waiver cases; and
- CI invokes that same repository command without duplicating validation logic.

Pre-acceptance review checks:

- verify that this ADR links cleanly from the decisive-slice acceptance packet;
- verify that C-03, C-04, and C-06 point to the same proposed resolution; and
- verify that no document records this decision as `Accepted` without explicit
  human approval.

## Approval

| Authority | Name | Decision | Date | Notes |
|---|---|---|---|---|
| Product owner | Jarkius | ACCEPT | 2026-07-26 | Explicit human decision recorded in an interactive session and transcribed into `DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md` |
| Chief Architect | Jarkius | ACCEPT | 2026-07-26 | Canonical envelope and approval-reference shape accepted as written |
| Engineering lead | Jarkius | ACCEPT | 2026-07-26 | Validator feasibility accepted; toolchain revised to Python per ADR-0005 |

The approvals above are explicit human decisions made by Jarkius on 2026-07-26
against `review-candidate commit`
`efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`; an AI agent transcribed them but
did not make them. The same-person role overlap is controlled by recorded
independent agent-review evidence and the residual-risk acceptance in
[`DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md);
no second human is assumed.
