# Pending Work to Ready

**Status:** Active delivery control
**Owner:** Product owner, Chief Architect, and Engineering Lead
**Scope:** Clear the blocked path from pre-implementation readiness to Task 001 implementation
**Last updated:** 2026-07-26

This document is the short operational path through the current blocked state.
It does not replace the validation report, contract acceptance record, ADR, or
MEOS Definition of Ready. It only orders the work required before implementation
may begin.

## Current decision

Motiflow is **not ready for implementation**. The current machine-verifiable
readiness score is **37/100**, and the honest ceiling remains **37/100** until
real participant evidence, human decisions, and sign-off are recorded.

Task 001 stays `proposed` and `BLOCKED` until every gate below passes.

## Phase A — Authorize validation setup

Goal: make the prepared validation round runnable without claiming evidence.

Required outputs:

- named accountable product owner;
- named facilitator;
- two or three opaque participant IDs with role coverage;
- consent evidence IDs stored outside the repository;
- restricted evidence location, access owner, and retention/deletion rule;
- frozen baseline workflow tools and proposed-workflow tools, versions, and
  settings;
- confirmation that all inputs are synthetic, authorized, or anonymized.

Repository updates:

- update `docs/01-product/validation/2026-07-25-mvp-validation-report.md`
  controlled setup, participant coverage, restricted evidence, and pre-session
  authorization rows;
- keep confidential identities, consent records, raw notes, and customer source
  material out of this repository.

Exit condition: `Session authorization` changes from `BLOCKED` only after every
pre-session checkbox passes.

## Phase B — Execute the validation protocol

Goal: replace prepared-case status with actual terminal evidence.

Required outputs:

- each of the eight prepared cases is executed or validly stopped;
- every participant completes at least two sessions;
- every case has a terminal outcome;
- run sheets, valid-stop records, friction decisions, aggregates, denominators,
  and per-role variance are complete;
- two-gate comprehension and artifact-sufficiency thresholds are evaluated.

Repository updates:

- complete the session run sheets, valid-stop records, friction table,
  aggregate evidence, and exit-criteria evidence in
  `docs/01-product/validation/2026-07-25-mvp-validation-report.md`;
- record only opaque evidence IDs and summaries suitable for the repository.

Exit condition: the validation report contains enough evidence for a product
owner to record `PROCEED`, `REVISE`, or `STOP`.

## Phase C — Record the product decision

Goal: turn validation evidence into an accountable product decision.

Required outputs:

- accountable product owner name;
- decision: `PROCEED`, `REVISE`, or `STOP`;
- rationale tied to the evidence;
- approved decisive-slice scope and explicit exclusions;
- constraints or corrections required before implementation;
- reviewed `review-candidate commit` SHA.

Repository updates:

- complete the Product-owner decision section of
  `docs/01-product/validation/2026-07-25-mvp-validation-report.md`.

Exit condition:

- `PROCEED` allows contract acceptance work to continue toward Task 001
  readiness;
- `REVISE` keeps Task 001 blocked and defines the rerun scope;
- `STOP` blocks implementation of the current decisive slice.

## Phase D — Close contract acceptance

Goal: make the first schema and fixture task implement one accepted contract,
not one of several plausible contracts.

Required outputs:

- C-01 canonical vocabulary and order disposition;
- C-02 two human gates disposition;
- C-03 canonical artifact-envelope disposition;
- C-04 approval-reference and decision-set disposition;
- C-05 schema dialect, versioning, and unknown-field policy disposition;
- C-06 validator/toolchain, dependency, lockfile, and owner disposition;
- Chief Architect and Engineering Lead sign-off;
- required corrections merged into controlling contract documents.

Repository updates:

- complete `docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`;
- update
  `docs/adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md`
  from proposed to the accepted, revised, or rejected outcome;
- reconcile accepted corrections in the controlling architecture documents.

Exit condition: contract acceptance outcome is `ACCEPTED`, and no C-01 through
C-06 decision remains `PENDING`.

## Phase E — Create the evidence/sign-off commit

Goal: close the revision trace without pretending that a commit can contain its
own SHA.

Required outputs:

- actual evidence links or opaque evidence IDs;
- final dispositions;
- product, architecture, and engineering signatures;
- accepted `review-candidate commit` SHA;
- optional signed tag after verification.

Repository updates:

- commit the completed validation, acceptance, ADR, and readiness evidence;
- record the resulting commit as the `evidence/sign-off commit` wherever the
  readiness packet requires it.

Exit condition: the revision-trace anchor can be earned.

## Phase F — Promote Task 001 only after Ready passes

Goal: start implementation only when MEOS readiness is real.

Required outputs:

- completed MEOS Definition of Ready report appended to
  `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`;
- frontmatter changed from `status: proposed` to `status: ready-for-dev`;
- frontmatter changed from `readiness: BLOCKED` to `readiness: READY`;
- owner replaced with the accountable human owner;
- required verification command and validator/toolchain authority confirmed.

Repository updates:

- update Task 001 only after Phases A through E pass;
- do not create `packages/`, `evaluations/`, `tools/`, CI, schemas, fixtures, or
  implementation artifacts before this phase passes.

Exit condition: Task 001 is ready to implement the contract proof.

## First implementation after readiness

When Task 001 is promoted, the first implementation is still narrow:

1. ten accepted v1 JSON Schemas;
2. deterministic valid and invalid fixtures;
3. one repository-local validation command:
   `./tools/validate-decisive-slice-contracts`;
4. one CI workflow that runs the same command.

Workflow runtime, persistence, APIs, UI, provider integration, publication, and
platform breadth remain deferred.
