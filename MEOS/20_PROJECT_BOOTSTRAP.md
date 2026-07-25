# Motiflow Engineering Operating System (MEOS)

## Purpose
This document is the mandatory entry point for every human engineer and AI agent working on Motiflow.

Its job is to provide enough trusted context to resume work safely without depending on prior chat history.

## Mission
Build Motiflow as an AI-native creative workflow platform using predictable, traceable, and verifiable engineering practices.

## Current Project State

### Current milestone
MEOS v1.0 governance and documentation baseline are complete and ready to guide implementation.

### Completed
- Project Charter and documentation hierarchy established.
- MEOS engineering and AI constitutions approved.
- Context strategy and machine-readable context routing established.
- Task Specification and Definition of Ready established.
- Quality Gate and engineering improvement flywheel established.
- Architecture Rules and ADR Process established.
- Coding Standard and Review Standard established.
- Golden Path from idea to production established.
- AI Workforce Charter and machine-readable roles established.
- MEOS v1.0 release-readiness assessment and project changelog created.

### Current focus
Move from governance design to real product delivery by applying MEOS end-to-end to the first concrete Motiflow feature.

### Next priorities
1. Select and specify the first implementation-ready Motiflow feature.
2. Execute that feature through the Golden Path using a complete Task Specification.
3. Implement and verify the feature in a real Git workspace with build, test, review, and release evidence.
4. Create a lean MEOS Validator for repository structure, metadata, links, context routing, and release checks.
5. Add CI enforcement only for rules proven valuable through real feature delivery.
6. Design the Agent Runtime and managed Git workspace after the manual workflow is validated.

### Deferred until justified by real use
- Full knowledge graph platform.
- Autonomous multi-agent orchestration.
- Large custom Context Engine.
- Broad automated governance beyond proven checks.

## How to Continue in a New Chat or Agent Session

A new AI session must not rely on conversation memory. It should:

1. Read this file completely.
2. Read `PROJECT_CHARTER.md`.
3. Read `CONTEXT_INDEX.yaml` and follow the route matching the task and role.
4. Read the applicable PRD, architecture, contracts, ADRs, standards, and current task.
5. Confirm the current milestone, task scope, acceptance criteria, constraints, and required evidence before editing.
6. Follow `MEOS/15_GOLDEN_PATH.md` and finish through `MEOS/10_QUALITY_GATE.md`.
7. Stop and ask for clarification when authoritative sources conflict or required context is missing.
8. Update this Current Project State section when a milestone materially changes.

A recommended continuation prompt is:

> Read `MEOS/20_PROJECT_BOOTSTRAP.md`, then `PROJECT_CHARTER.md` and `CONTEXT_INDEX.yaml`. Load the minimum authoritative context for the current task, summarize the verified project state, identify missing inputs, and continue from the next priority without inventing requirements.

## Authoritative Read Order
1. `MEOS/20_PROJECT_BOOTSTRAP.md`
2. `PROJECT_CHARTER.md`
3. `CONTEXT_INDEX.yaml`
4. Applicable MEOS standards and role definitions
5. Applicable product requirements and architecture
6. Applicable contracts and ADRs
7. Current task specification and acceptance criteria
8. Current implementation and verification evidence

When documents conflict, use authority, status, version, and explicit supersession rules. Do not silently choose the most convenient interpretation.

## Non-Negotiable Rules
- Never bypass architecture or approved contracts.
- Never invent requirements, APIs, schemas, events, or configuration.
- Every implementation task starts from a ready Task Specification.
- Every behavior change includes appropriate tests or explicitly documented verification limits.
- Every architecture-significant change requires an ADR.
- Documentation and operational evidence are part of the deliverable.
- AI-generated work is untrusted until independently verified.
- Never claim a build, test, commit, push, deployment, or validation that was not actually observed.

## Engineering Flywheel
Think → Plan → Build → Verify → Critique → Improve → Retest → Document → Learn → Repeat.

Stop the loop when:
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

When a real Git workspace is unavailable, clearly distinguish between:
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
Motiflow is successful when valuable product changes can move from approved intent to production through a repeatable, understandable, and evidence-backed workflow—not merely when documentation exists or code appears complete.
