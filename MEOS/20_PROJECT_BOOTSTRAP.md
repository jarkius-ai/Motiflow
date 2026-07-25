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

Documentation and architecture baseline work is complete on `main`. The repository is now in pre-implementation readiness for the first executable slice: pull requests #1 through #4 are merged, `origin/main` is at `dbce311`, and runtime/application implementation has not yet begun on the default branch.

### Completed

- PR #1 merged: repository foundation and canonical onboarding baseline established.
- PR #2 merged: documentation normalization baseline completed.
- PR #3 merged: runtime and architecture contract baseline frozen before implementation.
- PR #4 merged: AI execution layer documentation and implementation sequencing accepted on `main`.
- Project Charter and foundational architecture context established.
- MEOS engineering and AI constitutions established.
- Context strategy and machine-readable role and task routing established.
- Task Specification and Definition of Ready established.
- Quality Gate and engineering improvement flywheel established.
- Architecture Rules, ADR process, coding standard, review standard, and Golden Path established.
- AI Workforce Charter and machine-readable roles established.
- Foundation standards for document authority, terminology, and repository structure added.
- Repository migration plan, glossary, architecture dependency map, and initial terminology ADR added.

### Current Focus

Translate the accepted documentation and architecture baseline into the first implementation-ready task without inventing speculative structure. The immediate focus is Phase 4A readiness: scope the first executable slice, define its verification plan, and introduce only the canonical directories required by real code.

### Next Priorities

1. Select and scope the first implementation slice from the accepted roadmap, expected to begin with provider-neutral Model Gateway contracts plus supporting schemas and tests.
2. Write or refine the task specification, acceptance criteria, and verification plan for that slice under `MEOS/06_DEFINITION_OF_READY.md`.
3. Introduce only the canonical implementation directories required by the first real code change; avoid speculative repository skeletons.
4. Implement the first contracts-and-testability slice with build, test, and review evidence.
5. Follow with mock adapter, validation, prompt-control, and routing work in the accepted AI execution order.
6. Preserve the documentation baseline while implementation begins; structural migration remains incremental and evidence-driven.
7. Add lean automation only after a rule has proven valuable through real implementation work.

### Deferred Until Justified by Real Use

- Full knowledge-graph platform.
- Autonomous multi-agent engineering governance.
- Large custom context engine.
- Broad automated enforcement beyond proven checks.

These deferrals apply to engineering-governance automation. They do not change the approved ACDS product architecture, which includes workflow orchestration and specialist creative engines.

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

## How to Continue in a New Chat or Agent Session

A new session must not rely on conversation memory. It should:

1. read `START_HERE.md` and complete the foundation reading order;
2. follow the minimum task- and role-specific route in `CONTEXT_INDEX.yaml`;
3. confirm the current milestone, scope, acceptance criteria, constraints, decision authority, and required evidence;
4. apply `MEOS/15_GOLDEN_PATH.md` and finish through `MEOS/10_QUALITY_GATE.md`;
5. stop and escalate when authoritative sources conflict or required context is missing;
6. update this Current Project State section when a milestone materially changes.

Recommended continuation prompt:

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Load the minimum authoritative context for the current task, summarize the verified project state, identify assumptions or conflicts, and continue from the next approved priority without inventing requirements.

## Non-Negotiable Rules

- Never bypass accepted architecture or approved contracts.
- Never invent requirements, APIs, schemas, events, or configuration.
- Every implementation task starts from a ready Task Specification.
- Every behavior change includes appropriate tests or documented verification limits.
- Every architecture-significant change requires an ADR.
- Documentation and operational evidence are part of the deliverable.
- AI-generated work is untrusted until independently verified.
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
- a decision exceeds the assigned role's authority; or
- human approval is explicitly required.

## Success Metric

MEOS succeeds when valuable Motiflow changes move from approved intent to production through a repeatable, understandable, and evidence-backed workflow—not merely when documentation exists or code appears complete.
