# Motiflow Engineering Operating System (MEOS) — Project Bootstrap

## Purpose

This document is the engineering bootstrap for Motiflow. It provides the verified delivery state, engineering controls, and continuation procedure needed to resume work safely without depending on prior chat history.

It is not the product charter and not the product architecture authority.

- **Motiflow** is the product and repository identity.
- **ACDS** is the product architecture.
- **MEOS** is the engineering governance and delivery system.

Begin at [`START_HERE.md`](../START_HERE.md), which defines the canonical onboarding order.

## Current Project State

### Current Milestone

The initial documentation baseline is merged on `main`, and the project remains at decisive-slice validation and Task 001 readiness. Runtime/application implementation has not yet begun on the default branch.

A target-platform reconciliation package now exists for review. It preserves the complete long-term capability direction while keeping current implementation authority with accepted product decisions, architecture contracts, MEOS, ready tasks, and verified evidence. The reconciliation does not promote Task 001, accept ADR-0003, or authorize future capability phases.

Accepted product and architecture decisions remain controlled by the Product Charter, `MASTER_CONTEXT.md`, accepted ADRs, and other authoritative documents. Delivery-sequencing documents under `docs/03-delivery/` are planning artifacts until a human explicitly accepts or promotes them.

### Completed

- PR #1 merged: repository foundation and canonical onboarding baseline established.
- PR #2 merged: documentation normalization baseline completed.
- PR #3 merged: proposed runtime and architecture contract baseline added for review before implementation.
- PR #4 merged: AI execution layer documentation and proposed implementation sequencing added on `main`.
- Project Charter and foundational architecture context established.
- MEOS engineering and AI constitutions established.
- Context strategy and machine-readable role and task routing established.
- Task Specification and Definition of Ready established.
- Quality Gate and engineering improvement flywheel established.
- Architecture Rules, ADR process, coding standard, review standard, and Golden Path established.
- AI Workforce Charter and machine-readable roles established.
- Foundation standards for document authority, terminology, and repository structure added.
- Repository migration plan, glossary, architecture dependency map, and initial terminology ADR added.
- A review-branch target-platform blueprint, reconciliation matrix, capability map, expansion roadmap, and ADR-0004 proposal have been prepared without changing implementation readiness.

### Current Focus

Execute the MVP validation plan and translate its evidence plus the reconciled authoritative context into the first implementation-ready task without inventing speculative structure. The immediate focus remains readiness for a decisive creative-direction vertical slice: validate the workflow manually, obtain the accountable product-owner decision and required contract review, then define canonical schemas and fixtures, prove one executable workflow, and introduce only the canonical directories required by real code.

In parallel, review the target-platform reconciliation as architecture and planning only. Confirm that it connects the focused MVP to later research, acquisition, editorial, publication, publishing, measurement, and enterprise phases without changing the first implementation gate.

The operational artifacts for the current implementation gate are:

- [`../docs/01-product/validation/2026-07-25-mvp-validation-report.md`](../docs/01-product/validation/2026-07-25-mvp-validation-report.md) — open evidence record; participant evidence pending;
- [`../docs/01-product/validation/VALIDATION_CASE_CATALOG.md`](../docs/01-product/validation/VALIDATION_CASE_CATALOG.md) — eight prepared synthetic case packets; round authorization still pending;
- [`../docs/01-product/validation/VALIDATION_SESSION_INSTRUMENTS.md`](../docs/01-product/validation/VALIDATION_SESSION_INSTRUMENTS.md) — controlled facilitator, measurement, deterministic-review, and critic instruments;
- [`../docs/01-product/validation/VALIDATION_ARTIFACT_WORKSHEETS.md`](../docs/01-product/validation/VALIDATION_ARTIFACT_WORKSHEETS.md) — provisional ten-artifact manual worksheets for field validation;
- [`../docs/01-product/validation/2026-07-26-validation-instrument-dry-run.md`](../docs/01-product/validation/2026-07-26-validation-instrument-dry-run.md) — internal difficult-case protocol check; not participant evidence;
- [`../docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](../docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md) — review packet; human acceptance pending;
- [`../docs/adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md`](../docs/adr/ADR-0003-CANONICAL_ARTIFACT_ENVELOPE_AND_APPROVAL_REFERENCES.md) — proposed envelope and approval-reference resolution; Chief Architect acceptance pending;
- [`tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`](tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md) — first bounded story; blocked until its prerequisites pass; and
- [`../docs/03-delivery/PRE_IMPLEMENTATION_READINESS_REVIEW.md`](../docs/03-delivery/PRE_IMPLEMENTATION_READINESS_REVIEW.md) — current BMAD readiness evidence and score.

The target-platform review artifacts are:

- [`../docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`](../docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md) — complete target-state capability architecture;
- [`../docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](../docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md) — explicit current and future capability states;
- [`../docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`](../docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md) — adopt, adapt, defer, and reject mapping;
- [`../docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`](../docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md) — connected vertical-slice phases and activation gates; and
- [`../docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](../docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md) — proposed authority and phased-expansion decision.

The `review-candidate commit` for the decisive-slice validation packet is
`efc4b5e2bb71b6da2e2ee39ce187fd39bd117411`. The `trace-preparation commit`
records that SHA without claiming field evidence, decisions, or signatures. The
`evidence/sign-off commit` and its optional signed tag remain pending.

### Next Priorities

1. Review the target-platform reconciliation and record an explicit accept, revise, or reject decision for ADR-0004; this review does not replace the decisive-slice human validation gate.
2. Run `docs/01-product/MVP_VALIDATION_PLAN.md` with 5–10 representative inputs and 2–3 intended users or design partners.
3. Complete the dated validation report with baseline measures and an accountable product-owner proceed, revise, or stop decision without committing confidential participant material.
4. Resolve the artifact-envelope and approval-reference conflicts and obtain the required human acceptance of the two-gate state machine, canonical ten-artifact vocabulary, and first contract-proof boundary; review-ready status is not acceptance.
5. Run `MEOS/06_DEFINITION_OF_READY.md` against Task 001 and promote it from blocked to ready only when every prerequisite passes.
6. Introduce only the canonical implementation directories required by that task; avoid speculative repository skeletons and do not create a `packages/ai/` subtree.
7. Implement one executable workflow before broadening infrastructure.
8. Add a thin Model Gateway only after the workflow shape is proven, limited to an interface, deterministic mock, and one real provider.
9. Complete generated candidates, critics, final approval, and provenance evidence before activating external acquisition or publication phases.
10. Preserve the documentation baseline while implementation begins; structural migration remains incremental and evidence-driven.

### Deferred Until Justified by Real Use

- Full knowledge-graph platform.
- Autonomous multi-agent engineering governance beyond MEOS's bounded role model.
- Large custom context engine.
- Broad automated enforcement beyond proven checks.
- External acquisition and Agent Reach runtime integration before the creative MVP is accepted.
- Authenticated social research channels.
- Multi-provider routing and fallback mesh.
- Cost, token, latency, and validation dashboards.
- Editorial authoring and Publication Package implementation before Phase 5 activation.
- Browser, CMS, and social publishing connectors before Phase 6 activation.
- SDK ecosystem expansion.
- Enterprise marketplace and broad platform infrastructure.

These deferrals apply to implementation sequencing. They do not remove capabilities from the target ACDS architecture; they postpone unproven breadth until the preceding vertical slices demonstrate demand and pass their gates.

## Target Platform and Expansion Context

The target blueprint provides future direction but does not authorize work. For a question or task about future capabilities, read the minimum relevant set selected by `CONTEXT_INDEX.yaml`:

1. `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md` for target boundaries.
2. `docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md` for current state.
3. `docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md` for repository disposition.
4. `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md` for phase and activation gate.
5. `docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md` for the proposed decision state.
6. Applicable accepted ADRs, product evidence, contracts, and ready tasks.

Do not read the target blueprint and infer that all listed packages, providers, connectors, agents, or directories should be created. Introduce a capability only through its accepted phase, contract, and ready task.

## Canonical Read Order

The repository navigation authority is [`START_HERE.md`](../START_HERE.md).

The foundation order is:

1. `START_HERE.md`
2. `PROJECT_CHARTER.md`
3. `MASTER_CONTEXT.md`
4. `CONTEXT_INDEX.yaml`
5. `MEOS/20_PROJECT_BOOTSTRAP.md`
6. applicable MEOS standards and role definitions
7. applicable product requirements and architecture
8. applicable contracts and ADRs
9. current task specification and acceptance criteria
10. current implementation and verification evidence

The target blueprint and expansion documents are loaded only when the task concerns future capability planning, architecture expansion, or phase activation.

## How to Continue in a New Chat or Agent Session

A new session must not rely on conversation memory. It should:

1. read `START_HERE.md` and complete the foundation reading order;
2. follow the minimum task- and role-specific route in `CONTEXT_INDEX.yaml`;
3. confirm the current milestone, scope, acceptance criteria, constraints, decision authority, and required evidence;
4. distinguish current work from target-platform capability direction;
5. apply `MEOS/15_GOLDEN_PATH.md` and finish through `MEOS/10_QUALITY_GATE.md`;
6. stop and escalate when authoritative sources conflict or required context is missing; and
7. update this Current Project State section when a milestone materially changes.

Recommended continuation prompt:

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Load the minimum authoritative context for the current task, distinguish accepted decisions from review-ready planning artifacts and target-state capabilities, summarize the verified project state, identify assumptions or conflicts, and continue from the next approved priority without inventing requirements.

## Non-Negotiable Rules

- Never bypass accepted architecture or approved contracts.
- Never invent requirements, APIs, schemas, events, or configuration.
- Every implementation task starts from a ready Task Specification.
- Every behavior change includes appropriate tests or documented verification limits.
- Every architecture-significant change requires an ADR.
- Documentation and operational evidence are part of the deliverable.
- AI-generated work is untrusted until independently verified.
- Never claim a target capability is implemented because it appears in the blueprint or roadmap.
- Never claim a build, test, commit, push, deployment, or validation that was not observed.

## Engineering Flywheel

Think → Plan → Build → Verify → Critique → Improve → Retest → Document → Learn → Repeat.

Stop when:

- all mandatory gates pass;
- no meaningful improvement remains;
- a human decision is required;
- required context or environment is unavailable; or
- continuing would violate architecture, security, privacy, or approved scope.

## Definition of Ready

Implementation may begin only when requirements, acceptance criteria, dependencies, affected contracts, constraints, risks, test approach, and decision authority are sufficiently clear under `MEOS/06_DEFINITION_OF_READY.md`.

Target phase placement does not make a task ready.

## Definition of Done

A task is complete only when requirements are satisfied, checks are executed with recorded evidence, documentation is updated, independent review is complete where required, compatibility and rollback are assessed, and the Quality Gate produces an acceptable outcome.

## Verification Discipline

Conversation is not evidence. Verification must come from observable artifacts such as:

- repository contents and Git history;
- build, lint, type-check, test, and security output;
- contract and migration checks;
- review reports;
- deployment and rollback evidence;
- release-readiness records.

When a real Git workspace is unavailable, distinguish between:

- confirmed through the GitHub API;
- inferred from documents;
- proposed but not implemented; and
- unverified because execution access is unavailable.

## Stop Conditions

Stop and escalate when:

- requirements or authoritative documents conflict;
- architecture or a contract would be violated;
- security, privacy, data-loss, or irreversible migration risk is unresolved;
- required access, tooling, context, or evidence is unavailable;
- a decision exceeds the assigned role's authority;
- a future phase's activation gate has not passed; or
- human approval is explicitly required.

## Success Metric

MEOS succeeds when valuable Motiflow changes move from approved intent to production through a repeatable, understandable, and evidence-backed workflow—not merely when documentation exists, a future capability is described, or code appears complete.
