---
id: MEOS-006
title: Definition of Ready
status: approved
owner: Product and Engineering Leads
version: 1.0
authoritative: true
readers: [all-contributors]
provides: [readiness-gate, pre-implementation-checklist]
requires: [MEOS-003, MEOS-005]
related: [MEOS/02_AI_CONSTITUTION.md, MEOS/10_QUALITY_GATE.md]
---

# Definition of Ready

## Purpose
Prevent implementation from starting before the task has enough authoritative context to be completed safely and verified objectively.

## Mandatory Readiness Gate
A task is **READY** only when all applicable items pass:

### Outcome
- The objective and business reason are clear.
- Acceptance criteria are observable and testable.
- In-scope and out-of-scope boundaries are stated.

### Authority and Context
- An accountable human owner is identified.
- The assigned role is declared.
- Required context and controlling references are available.
- Conflicting sources have been resolved or explicitly escalated.

### Product and Architecture
- Relevant product requirements exist.
- Affected interfaces, schemas, workflows, and contracts are identified.
- Architectural impact is understood.
- An ADR is required and available when architecture is changed.

### Engineering
- Dependencies and prerequisites are known.
- Constraints are explicit.
- Test expectations and verification evidence are defined.
- Documentation impact is identified.
- Security, privacy, migration, compatibility, and rollback concerns are addressed when applicable.

### Execution
- Expected outputs are listed.
- Stop conditions are declared.
- The task can be completed without inventing material requirements.

## Statuses
- `READY`: all mandatory applicable checks pass.
- `CONDITIONALLY_READY`: a human-approved exception is documented with owner, reason, risk, and expiry or follow-up.
- `NOT_READY`: one or more mandatory checks fail.
- `BLOCKED`: an external dependency or decision prevents readiness.

## Agent Behavior
An AI agent must not begin implementation for a `NOT_READY` or `BLOCKED` task. It may analyze gaps, propose options, or prepare questions without modifying implementation artifacts.

## Readiness Report

```yaml
task_id: TASK-000
status: READY
checked_by: role-or-person
date: YYYY-MM-DD
passed:
  - objective
  - acceptance_criteria
  - context
exceptions: []
missing: []
risks: []
next_action: begin implementation
```

## Exception Rule
Exceptions must never be implicit. They require an accountable human owner, documented risk, compensating control, and follow-up action.
