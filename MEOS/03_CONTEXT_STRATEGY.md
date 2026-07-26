---
id: MEOS-003
title: Context Strategy
status: approved
owner: Chief Architect
version: 1.0
authoritative: true
readers: [all-ai-agents, human-reviewers]
provides: [context-routing, document-precedence, minimum-context-rules]
requires: [MEOS-002, CONTEXT_INDEX]
related: [MEOS/roles.yaml, MEOS/05_TASK_SPECIFICATION.md, MEOS/20_PROJECT_BOOTSTRAP.md]
---

# Context Strategy

## Purpose
Define how humans and AI agents select the minimum authoritative context required for a task without treating the repository as an undifferentiated collection of files.

## Context Questions
Before execution, every agent must answer:
1. Who am I acting as?
2. What task am I performing?
3. Which sources are authoritative for that task?
4. Which dependencies and contracts are affected?
5. What evidence will prove completion?

## Required Read Sequence
This sequence assumes the `START_HERE.md` foundation order (`START_HERE.md` → `PROJECT_CHARTER.md` → `MASTER_CONTEXT.md` → `CONTEXT_INDEX.yaml` → `MEOS/20_PROJECT_BOOTSTRAP.md`) has already been followed.
1. `MEOS/20_PROJECT_BOOTSTRAP.md`
2. `CONTEXT_INDEX.yaml`
3. The role definition in `MEOS/roles.yaml`
4. `MEOS/02_AI_CONSTITUTION.md`
5. `MEOS/05_TASK_SPECIFICATION.md`
6. `MEOS/06_DEFINITION_OF_READY.md`
7. Task-declared references
8. Affected architecture, contracts, code, tests, and ADRs
9. `MEOS/10_QUALITY_GATE.md` before completion

## Context Selection Rules
Include a source when it is:
- explicitly referenced by the task;
- required by the assigned role;
- authoritative for an affected interface, workflow, data model, or policy;
- directly upstream or downstream of the proposed change;
- necessary to verify acceptance criteria.

Exclude a source when it is:
- unrelated background;
- archived or superseded;
- duplicated by a higher-authority source;
- merely similar by wording but unrelated to the task.

## Context Manifest
Before implementation, record:
- role;
- task ID;
- required sources;
- optional sources;
- affected contracts;
- missing context;
- assumptions requiring approval.

The manifest may live in the task description, issue, pull request, or agent work log.

## Conflict Handling
Use the precedence defined in the AI Constitution. Record the conflict and stop when it could change behavior, scope, architecture, security, data, or acceptance criteria.

## Context Budget
Prefer the smallest complete context set. Do not reduce context by omitting authoritative constraints. Summaries may supplement sources but must not replace controlling contracts.

## Chaining and Handoffs
Each handoff must provide:
- task state;
- context manifest;
- decisions made;
- artifacts produced;
- verification evidence;
- unresolved risks;
- next role and expected output.

The receiving agent must verify the handoff rather than assuming it is correct.

## Maintenance
`CONTEXT_INDEX.yaml` is the routing entry point. Document front matter is the durable relationship layer. When paths, authority, or role responsibilities change, update the index and affected metadata in the same change.
