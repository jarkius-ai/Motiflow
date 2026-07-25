---
id: MEOS-005
title: Task Specification
status: approved
owner: Product and Engineering Leads
version: 1.1
authoritative: true
readers: [all-contributors]
provides: [task-contract, acceptance-structure, artifact-contract-link, handoff-structure]
requires: [MEOS-002, MEOS-003]
related: [MEOS/06_DEFINITION_OF_READY.md, MEOS/10_QUALITY_GATE.md, MEOS/11_ARCHITECTURE_RULES.md, MEOS/14_ADR_PROCESS.md, MEOS/roles.yaml, docs/02-architecture/DATA_CONTRACTS.md]
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
review_roles: [reviewer, qa]
priority: medium
risk_class: low

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
    evidence: test, artifact, screenshot, log, metric, or review

inputs:
  documents:
    - authoritative path or approved decision
  artifacts:
    - artifact_id: ART-000
      contract: contract ID or schema path
      version: approved version
      validation: command, schema, or reviewer

references:
  requirements:
    - PRD, issue, or user journey
  architecture:
    - architecture document or ADR
  contracts:
    - API, schema, event, workflow, UI, prompt, or artifact contract

affected_contracts:
  - id: CONTRACT-000
    type: api | data | event | workflow | ui | prompt | artifact
    change: none | compatible | breaking
    migration: required plan or not-applicable

constraints:
  - compatibility, security, performance, cost, time, or technology rule

dependencies:
  - prerequisite task, decision, system, environment, or person

risks:
  - risk: known risk
    mitigation: planned control
    owner: accountable role

verification:
  required_tests:
    - test type or exact command
  independent_review: true
  quality_gate: MEOS/10_QUALITY_GATE.md
  minimum_score: 90

expected_outputs:
  - artifact_id: ART-OUT-000
    type: code | test | doc | adr | report | design | migration | release-note
    contract: schema or governing document
    owner: producing role
    validation: observable validation method

release_impact:
  release_required: true
  migration_plan: path or not-applicable
  rollback_plan: path or not-applicable
  monitoring: metric, check, or not-applicable

handoff_to: reviewer
stop_conditions:
  - missing contract
  - conflicting requirement
  - failed mandatory gate
  - missing human authority
```

## Artifact Contract Rules
Every non-trivial input and output must identify its governing contract or state explicitly why no contract is applicable.

An artifact contract must define, directly or by reference:
- identity and version;
- owner and consumer;
- required fields or structure;
- validation method;
- compatibility expectations;
- failure behavior;
- lifecycle or retention when relevant.

An implementation may not silently redefine an artifact contract. Compatible changes must be documented; breaking changes require migration, versioning, review, and approval.

## Specification Rules
- State outcomes, not step-by-step implementation unless the method is constrained.
- Acceptance criteria must be observable and independently verifiable.
- In-scope and out-of-scope boundaries are mandatory for non-trivial work.
- Reference exact files, contracts, issues, or decisions whenever available.
- Unknowns must be recorded; they must not be silently converted into assumptions.
- A task that changes architecture must apply `MEOS/11_ARCHITECTURE_RULES.md` and require an ADR when triggered.
- A task that changes behavior must identify tests and documentation impacts.
- A release-affecting task must identify migration, rollback, monitoring, and release-note impacts.
- A numerical quality score cannot override a failed mandatory gate.

## Execution Contract
The assigned role may choose implementation details only within the declared constraints and authority boundaries. Scope, contract, acceptance, architecture, and risk-class changes require the appropriate human approval.

## Completion Report
On completion, append or provide:
- result summary;
- acceptance-criteria evidence by ID;
- inputs consumed and outputs produced by artifact ID;
- files and contracts changed, including compatibility classification;
- ADRs created or applied;
- tests and evaluation commands with results;
- security and architecture review status as applicable;
- quality score and every mandatory-gate result;
- migration, rollback, monitoring, and release status;
- assumptions and residual risks;
- recommended follow-up.