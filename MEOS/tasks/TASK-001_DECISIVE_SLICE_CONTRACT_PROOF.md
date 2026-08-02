---
task_id: TASK-001
title: Prove the decisive-slice contracts before runtime implementation
status: PROPOSED
readiness: BLOCKED
owner: Jarkius
assigned_role: backend
review_roles: [reviewer, qa, chief_architect]
priority: high
risk_class: medium

objective: >
  Deliver ten accepted JSON Schemas, deterministic valid and invalid fixtures,
  one repository command, and one CI workflow that prove structural, gate,
  lineage, and provenance rules before runtime implementation.
business_reason: >
  Prevent later workflow code from embedding incompatible assumptions about
  artifact names, envelopes, approvals, or lineage.
in_scope:
  - ten canonical decisive-slice schemas and accepted shared definitions
  - deterministic valid and invalid fixtures
  - one offline-after-install repository validation command
  - one CI workflow that invokes the same repository validation command
  - structural and semantic contract tests
out_of_scope:
  - workflow, kernel, provider, persistence, API, or UI implementation
  - publication, article authoring, CMS, social, or export integrations
  - type generation, registry services, SDKs, or broad validation frameworks
acceptance_criteria:
  - {id: AC-01, condition: exactly ten accepted v1 artifact schemas exist, evidence: schema inventory}
  - {id: AC-02, condition: structural valid and invalid cases behave as declared, evidence: contract tests}
  - {id: AC-03, condition: one complete ten-artifact chain validates, evidence: happy-path test}
  - {id: AC-04, condition: direction-gate structure and human actor identity are enforced without runtime role authorization, evidence: negative fixtures}
  - {id: AC-05, condition: invalid final-gate chains fail, evidence: negative fixtures}
  - {id: AC-06, condition: versioned parent references reject stale downstream lineage, evidence: invalidation fixtures}
  - {id: AC-07, condition: one stable command proves the entire contract set locally and in CI, evidence: clean-environment transcript and CI run}
  - {id: AC-08, condition: scope and documentation pass independent review, evidence: review record}
inputs:
  documents:
    - docs/01-product/validation/2026-07-25-mvp-validation-report.md
    - docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md
    - docs/02-architecture/DATA_CONTRACTS.md
    - docs/02-architecture/RUNTIME_CONTRACTS.md
    - docs/02-architecture/WORKFLOW_STATE_MACHINE.md
    - docs/02-architecture/VERSIONING_AND_COMPATIBILITY.md
    - docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md
  artifacts: []
references:
  requirements: [docs/PRD.md, docs/01-product/MVP_VALIDATION_PLAN.md]
  architecture: [docs/SYSTEM_DESIGN.md, docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md, docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md]
  contracts: [docs/02-architecture/DATA_CONTRACTS.md, docs/02-architecture/RUNTIME_CONTRACTS.md, docs/02-architecture/WORKFLOW_STATE_MACHINE.md]
affected_contracts:
  - {id: decisive-slice-artifacts-v1, type: artifact, change: compatible, migration: not-applicable-before-first-consumer}
constraints:
  - no new dependency without explicit approval and a committed lockfile
  - no network access during validation after dependency installation
  - synthetic or anonymized fixture data only
  - no scope beyond the accepted decisive slice
dependencies:
  - completed validation report with product-owner PROCEED decision
  - accepted C-01 through C-06 contract decisions
  - accepted ADR-0003 architecture decision
  - merged canonical envelope and approval-reference corrections
  - approved validator toolchain and accountable owner
risks:
  - {risk: schema encodes an unresolved envelope, mitigation: acceptance and merged correction are prerequisites, owner: chief architect}
  - {risk: ungoverned validation dependency, mitigation: explicit approval and lockfile, owner: engineering lead}
  - {risk: gate bypass hidden by happy path, mitigation: AC-04 through AC-06 negative fixtures, owner: qa}
  - {risk: one person holds product owner, facilitator, chief architect, and engineering lead roles, mitigation: independent reviewer and QA evidence are mandatory and cannot be supplied by the accountable owner alone, owner: reviewer}
verification:
  required_tests:
    - ./tools/validate-decisive-slice-contracts
    - project-native lint and static checks introduced by the approved toolchain
  independent_review: true
  quality_gate: MEOS/10_QUALITY_GATE.md
  minimum_score: 95
expected_outputs:
  - {artifact_id: ART-SCHEMAS-V1, type: code, contract: accepted C-01 through C-05 decisions, owner: backend, validation: ./tools/validate-decisive-slice-contracts}
  - {artifact_id: ART-FIXTURES-V1, type: test, contract: AC-03 through AC-06, owner: qa, validation: ./tools/validate-decisive-slice-contracts}
  - {artifact_id: ART-VALIDATOR-V1, type: code, contract: accepted C-06 decision, owner: backend, validation: clean-environment transcript}
  - {artifact_id: ART-CI-V1, type: code, contract: AC-07, owner: backend, validation: CI invokes ./tools/validate-decisive-slice-contracts}
release_impact:
  release_required: false
  migration_plan: not-applicable-before-first-consumer
  rollback_plan: revert the task commit before consumers; version after consumers exist
  monitoring: not-applicable
handoff_to: reviewer
stop_conditions:
  - validation decision is not PROCEED
  - contract acceptance is not ACCEPTED
  - envelope or approval-reference conflict remains open
  - validator dependency or toolchain lacks authority
  - mandatory verification or independent review fails
---

# Task 001 — Decisive-Slice Contract Proof

## Story

As the team implementing Motiflow's first vertical slice, I want the ten
canonical artifacts expressed as executable JSON Schemas with deterministic
positive and negative fixtures, so that later workflow code cannot reinterpret
the two approval gates, lineage, or package vocabulary.

Jarkius is the accountable task owner and holds the Product owner, Facilitator,
Chief Architect, and Engineering lead roles. This assignment is not a product
decision, contract disposition, approval, signature, or implementation
authorization. `review_roles`, `verification.independent_review`, and the QA
handoff remain mandatory; independent Reviewer and QA evidence must come from a
separate reviewer/agent role and may not be inferred from Jarkius's self-review.

## Objective

Deliver the narrowest executable proof of the accepted artifact contract: ten
versioned schemas, one complete valid artifact chain, focused invalid fixtures,
one repository command that validates structural and semantic rules, and one CI
workflow that runs that exact command.

The ten schemas are for:

- Intake Package;
- Normalized Brief;
- Knowledge Fusion Package;
- Creative Direction Package;
- Direction Approval Record;
- Generation Specification;
- Generated Candidate Set;
- Critic Evaluation Package;
- Final Approval Record; and
- Provenance Record.

Their order and machine names must come from the accepted C-01 decision rather
than this story alone.

## Business reason

This converts the review-ready workflow into an independently verifiable
boundary before workflow, model-gateway, provider, persistence, or UI work can
embed incompatible assumptions.

## Prerequisites

All are mandatory:

- [ ] [`../../docs/01-product/validation/2026-07-25-mvp-validation-report.md`](../../docs/01-product/validation/2026-07-25-mvp-validation-report.md) records completed field evidence and a product-owner `PROCEED` decision.
- [ ] [`../../docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../../docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) records `ACCEPTED` with all C-01–C-06 decisions closed.
- [ ] [`../../docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md`](../../docs/adr/ADR-0003-canonical-artifact-envelope-and-approval-references.md) records the Chief Architect's accepted envelope and approval-reference decision.
- [ ] The canonical envelope and approval-reference corrections are merged into the controlling contract documents.
- [ ] The validator implementation/toolchain and any new dependency are explicitly approved.
- [ ] The accountable human owner is named in this task.

Until these pass, analysis and review may continue but implementation artifacts
must not be created. When they pass, run the readiness check in
[`../06_DEFINITION_OF_READY.md`](../06_DEFINITION_OF_READY.md) and append its
dated evidence here. Set frontmatter `status: READY` (MEOS/19 task-state vocabulary) and `readiness:
READY` only after every applicable readiness item passes.

## In scope

- JSON Schemas for the ten canonical decisive-slice artifacts and accepted shared definitions.
- Stable `$id`, JSON Schema dialect, semantic version, and explicit unknown-field behavior.
- One deterministic valid chain with all ten artifacts and internally consistent references.
- Invalid fixtures for structural, approval-gate, version, lineage, and provenance failures.
- A repository-local validation entrypoint at `./tools/validate-decisive-slice-contracts`.
- Contract tests for command exit codes and deterministic output.
- One minimal CI workflow that installs locked dependencies and invokes only the
  canonical validation entrypoint for this contract proof.
- Minimal documentation for adding a schema or fixture without bypassing the command.

## Out of scope

- Workflow execution or orchestration.
- Creative Kernel, persistence, queues, APIs, or UI.
- Model Gateway, provider adapters, model calls, or generated media.
- Publication Package, article authoring, CMS, social, or export integrations.
- Type generation, schema registry services, or SDKs.
- Project-role, tenant, or gate-authorization policy enforcement.
- Application-framework bootstrap or application-container integration.
- Broad reusable validation framework beyond the accepted decisive slice.
- Unrelated repository automation or a general-purpose CI platform redesign.

## Acceptance criteria

### AC-01 — Canonical schema set

Given the accepted contract revision, when the schema directory is inspected,
then exactly one v1 schema exists for each canonical artifact and every schema
uses only accepted names, fields, versions, and shared definitions.

**Evidence:** schema inventory emitted by the validation command.

### AC-02 — Structural enforcement

Given every valid fixture, when the command runs, then all artifacts validate
against the accepted JSON Schema dialect and version. Given a fixture with a
missing required field, forbidden unknown field, malformed identifier, invalid
enum, or incompatible version, the command returns non-zero and identifies the
artifact and JSON path.

**Evidence:** automated contract tests and command transcript.

### AC-03 — Complete valid chain

Given the happy-path fixture set, when semantic validation runs, then it proves
an internally consistent chain from Intake Package through Provenance Record,
including current versions, versioned `parent_artifact_refs`, source references,
both approvals, and the final provenance closure.

**Evidence:** deterministic happy-path test.

### AC-04 — Direction gate integrity

Given generation with no direction approval, a non-approved decision, a stale
direction reference, a malformed approval actor, `created_by.type` other than
`human`, or `created_by.id != payload.actor.actor_id`, when validation runs,
then the chain fails before Generation Specification or generated candidates
are accepted. The fixture proves structural human-actor validity and actor-ID
equality only. Whether `payload.actor.actor_role` is authorized for a tenant,
project, or gate is deferred to runtime authorization-policy work and is not an
AC-04 validator responsibility.

**Evidence:** one named invalid fixture per failure class.

### AC-05 — Final gate integrity

Given export/provenance with no final approval, a stale candidate reference, a
missing critic-package reference, unresolved blocking critic findings, or a
non-approved decision, when validation runs, then the chain fails.

**Evidence:** one named invalid fixture per failure class.

### AC-06 — Invalidation and lineage

Given a revised Creative Direction Package, Generation Specification, candidate
set, or critic package, when any downstream `parent_artifact_refs` entry names
an old `artifact_version`, mismatches the stored `artifact_type`, or names an
invalidated dependency version, then semantic validation fails at the earliest
invalid reference and identifies the expected current version.

**Evidence:** deterministic invalidation fixtures.

### AC-07 — One validation command locally and in CI

Given installed, lockfile-pinned dependencies, when a contributor runs
`./tools/validate-decisive-slice-contracts` from the repository root, then all
schema, semantic, and fixture tests run without network access; the command
returns `0` only when every expected-valid case passes and every expected-invalid
case fails for its declared reason. Given the CI workflow, when it runs for a
change affecting the contract proof, then it installs the same locked
dependencies and invokes that exact entrypoint without duplicating validation
logic in workflow YAML.

**Evidence:** clean-environment command transcript and passing CI run.

### AC-08 — Scope and documentation

Given the task diff, when independently reviewed, then it contains no workflow,
provider, persistence, UI, publication, or speculative framework code; schema
ownership, compatibility, fixture conventions, and the validation command are
documented and linked from the document index.

**Evidence:** independent scope review and documentation check.

## Expected file map

Only the directory ownership and version boundary are proposed here. Exact
schema filenames and shared-definition boundaries must be added from the
accepted C-01, C-03, and C-05 decisions before this task can become ready.

```text
packages/schemas/
  decisive-slice/
    <accepted-v1-version>/
      <accepted-shared-definitions>
      <one-schema-per-canonical-artifact>
evaluations/fixtures/decisive-slice/<accepted-v1-version>/
  valid/
  invalid/
tools/
  validate-decisive-slice-contracts
.github/workflows/
  decisive-slice-contracts.yml
```

## Inputs and affected contracts

- Product: `docs/PRD.md`, `docs/01-product/MVP_VALIDATION_PLAN.md`, accepted dated validation report.
- Architecture: `docs/02-architecture/DATA_CONTRACTS.md`, `RUNTIME_CONTRACTS.md`, `WORKFLOW_STATE_MACHINE.md`, `VERSIONING_AND_COMPATIBILITY.md`.
- Evaluation: `docs/04-ai/EVALUATION_FRAMEWORK.md`.
- Governance: `MEOS/05_TASK_SPECIFICATION.md`, `MEOS/06_DEFINITION_OF_READY.md`, `MEOS/10_QUALITY_GATE.md`.
- Contract change: new v1 machine-readable artifact contracts; compatibility classification `compatible` with the accepted pre-implementation documentation baseline.

## Constraints

- No new dependency without explicit approval and a committed lockfile.
- The approved validator boundary is a plain Python 3.12+ CLI with
  `jsonschema>=4.21,<5` pinned in a committed lockfile, per ADR-0005 and the
  accepted C-06 record; it must not bootstrap the application framework. This remains
  a proposal until the engineering lead approves the dependency and lockfile.
- No network access during the validation command after dependency installation.
- Fixtures contain synthetic or anonymized data only.
- Approval and provenance examples use deterministic identifiers and timestamps.
- Invalid fixtures declare the failure code/path they are expected to produce.
- JSON-valid is not semantically valid; gate and lineage checks are required.
- A numerical quality score cannot override a failed contract or review gate.

## Risks and mitigations

| Risk | Mitigation | Owner |
|---|---|---|
| Schemas encode one of the unresolved envelope variants | C-03 acceptance and merged contract correction are prerequisites | Chief architect |
| Validator choice creates an ungoverned dependency | Require explicit toolchain approval and lockfile | Engineering lead |
| Happy-path fixtures conceal gate bypass | Require focused negative cases in AC-04–AC-06 | QA |
| First task expands into runtime infrastructure | Enforce out-of-scope list and independent review | Reviewer |
| Fixtures expose participant or client material | Use synthetic/anonymized values only | Product owner |

## Verification

- `./tools/validate-decisive-slice-contracts` — all declared valid fixtures pass and all invalid fixtures fail for the expected reason.
- CI contract workflow — installs locked dependencies and invokes
  `./tools/validate-decisive-slice-contracts` without separate validation logic.
- Project-native lint/static checks introduced with the chosen toolchain — pass.
- Independent contract review — confirms traceability to C-01–C-06 and AC-01–AC-08.
- `MEOS/10_QUALITY_GATE.md` — all applicable mandatory gates pass and score is at least 95 for this task.

## Security and privacy

N/A for this task. Scope is limited to JSON Schemas, deterministic fixtures,
a local validator command, and a CI workflow that invokes it; no runtime
service, external connector, secret, or participant/personal data is
introduced. Security review applies once a runtime component or connector is
implemented against these schemas.

## Rollback

Before downstream consumers exist, revert the task commit as one unit. After a
schema version has consumers, follow `VERSIONING_AND_COMPATIBILITY.md`; do not
rewrite an accepted version in place.

## Stop conditions

- Validation decision is not `PROCEED`.
- Contract acceptance is not `ACCEPTED`.
- Envelope or approval-reference conflict remains open.
- Required dependency or toolchain lacks authority.
- An acceptance criterion would require workflow/provider/publication scope.
- Mandatory verification or independent review fails.

## Agent record

- Created by: Codex planning review
- Date: 2026-07-25
- `review-candidate commit` SHA: `efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`
- `trace-preparation commit`: RECORDED; records only the candidate SHA and
  keeps participant evidence, decisions, and signatures pending
- `evidence/sign-off commit`: PENDING; must contain real evidence and human
  decisions before this task can satisfy its readiness prerequisites
- Implementation notes: none; task is blocked at the human/evidence gate
- Completion notes: not started
- File list: not applicable
- Change log: initial review-ready story packet; CI made an explicit milestone deliverable
