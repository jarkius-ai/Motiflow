---
id: MEOS-005
title: Task Specification
status: approved
owner: Product and Engineering Leads
version: 1.0
authoritative: true
readers: [all-contributors]
provides: [task-contract, acceptance-structure, handoff-structure]
requires: [MEOS-002, MEOS-003]
related: [MEOS/06_DEFINITION_OF_READY.md, MEOS/10_QUALITY_GATE.md, MEOS/roles.yaml]
---

# Task Specification

## Purpose
Every implementation, investigation, design, migration, or documentation change must begin from a task contract using this structure.

## Canonical Template

```yaml
task_id: TASK-000
title: concise outcome-oriented title
status: proposed
owner: accountable human
assigned_role: backend
priority: medium

objective: >
  The measurable outcome to achieve.

business_reason: >
  Why this work matters.

in_scope:
  - explicitly included work

out_of_scope:
  - explicitly excluded work

acceptance_criteria:
  - id: AC-01
    condition: observable pass condition
    evidence: test, artifact, screenshot, log, or review

inputs:
  - path or approved decision

references:
  - authoritative file or ADR

affected_contracts:
  - API, schema, event, workflow, or UI contract

constraints:
  - compatibility, security, performance, time, or technology rule

dependencies:
  - prerequisite task, decision, system, or person

risks:
  - known risk and mitigation

verification:
  required_tests:
    - test type or command
  quality_gate: MEOS/10_QUALITY_GATE.md

expected_outputs:
  - code, tests, docs, ADR, report, or design artifact

handoff_to: reviewer
stop_conditions:
  - missing contract
  - conflicting requirement
```

## Specification Rules
- State outcomes, not step-by-step implementation unless the method is constrained.
- Acceptance criteria must be observable and independently verifiable.
- In-scope and out-of-scope boundaries are mandatory for non-trivial work.
- Reference exact files, contracts, issues, or decisions whenever available.
- Unknowns must be recorded; they must not be silently converted into assumptions.
- A task that changes architecture must require an ADR.
- A task that changes behavior must identify tests and documentation impacts.

## Execution Contract
The assigned role may choose implementation details only within the declared constraints and authority boundaries. Scope changes require task-owner approval.

## Completion Report
On completion, append or provide:
- result summary;
- acceptance-criteria evidence by ID;
- files and contracts changed;
- tests run and results;
- quality-gate status;
- assumptions;
- residual risks;
- recommended follow-up.
