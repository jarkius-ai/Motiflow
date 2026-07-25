---
id: MEOS-015
title: Golden Path — Idea to Production
status: approved
owner: Product and Engineering Leads
version: 1.0
authoritative: true
readers: [all-contributors]
provides: [reference-workflow, release-path, evidence-chain]
requires: [MEOS-001, MEOS-002, MEOS-005, MEOS-006, MEOS-010, MEOS-011, MEOS-014, MEOS-019]
related: [CONTEXT_INDEX.yaml, MEOS/roles.yaml]
---

# Golden Path — Idea to Production

## Purpose
Provide one canonical, repeatable route from an idea to a safe production release. Deviations are allowed only when explicitly justified and approved.

## The Path
`Idea -> Product Outcome -> Ready Task -> Context -> Architecture -> Implementation -> Independent Verification -> Quality Gate -> Release -> Observe -> Learn`

## 1. Capture the Product Outcome
**Owner:** Product Owner

Required outputs:
- problem and target user;
- measurable outcome;
- in-scope and out-of-scope boundaries;
- acceptance criteria;
- priority and business reason.

Exit condition: the requested outcome is testable and does not prescribe unnecessary implementation detail.

## 2. Create the Task Contract
**Owner:** Product Owner or Engineering Lead

Use `MEOS/05_TASK_SPECIFICATION.md`. Link all controlling requirements, affected contracts, dependencies, risks, expected artifacts, and verification commands.

Exit condition: `MEOS/06_DEFINITION_OF_READY.md` passes with no unresolved blocking item.

## 3. Build the Context Manifest
**Owner:** Assigned Execution Role

Start at `MEOS/20_PROJECT_BOOTSTRAP.md`, route through `CONTEXT_INDEX.yaml`, load the assigned role from `MEOS/roles.yaml`, and read only the minimum complete context.

Record:
```yaml
task_id:
role:
authoritative_sources:
affected_contracts:
applicable_adrs:
unknowns:
```

Exit condition: no conflicting authoritative source or hidden dependency remains.

## 4. Decide Architecture Before Coding
**Owner:** Chief Architect for architecture-sensitive work

Apply `MEOS/11_ARCHITECTURE_RULES.md`. Create an ADR under `docs/adr/` when triggered by `MEOS/14_ADR_PROCESS.md`.

Exit condition:
- architecture-sensitive changes have accepted human approval;
- dependency direction and system boundaries are explicit;
- migration, rollback, security, and failure behavior are defined.

## 5. Implement the Smallest Complete Change
**Owner:** Backend, Frontend, AI Engineer, Documentation, or other assigned role

Implementation rules:
- remain inside declared scope;
- preserve or intentionally version contracts;
- add tests with the behavior change;
- update operational and user documentation;
- produce observable evidence for each acceptance criterion;
- stop rather than invent missing requirements.

Exit condition: implementation, tests, documentation, and completion report are available.

## 6. Perform Self-Review
**Owner:** Implementer

Verify:
- every acceptance criterion has evidence;
- no unrelated scope entered the change;
- contracts and ADRs are aligned;
- failure paths, security, accessibility, performance, and rollback were considered as applicable;
- commands and test results are recorded honestly.

Exit condition: the task is ready for independent review, not merely believed to be complete.

## 7. Independent Review and Verification
**Owners:** Reviewer, QA, Security Reviewer as routed

The reviewer assesses correctness, architecture, maintainability, scope, and evidence. QA independently verifies acceptance criteria and regression safety. Security review is mandatory for security-sensitive changes.

Possible outcomes:
- `ACCEPT`: all mandatory gates pass;
- `LOOP`: actionable improvements return to the implementer;
- `BLOCKED`: required context, decision, environment, or authority is missing;
- `REJECT`: the solution is unsafe, fundamentally misaligned, or cannot satisfy the task.

Exit condition: independent evidence supports release readiness.

## 8. Run the Quality Gate and Engineering Flywheel
**Owner:** Reviewer

Apply `MEOS/10_QUALITY_GATE.md`.

For `LOOP`:
`Analyze -> Improve -> Retest -> Re-review`

Stop looping when:
- the score is at least 90 and every mandatory gate passes;
- further improvement is not measurable and a human decision is required;
- the task is blocked by missing context or authority;
- continuing would violate an approved rule or contract.

A score cannot compensate for a failed build, test, security, architecture, documentation, migration, or human-approval gate.

## 9. Prepare and Authorize Release
**Owner:** Release Manager; approval by authorized human

Required evidence:
- accepted Quality Gate report;
- test and evaluation results;
- release notes;
- deployment or publication plan;
- migration and rollback plan when applicable;
- monitoring and rollback triggers;
- known residual risks and owners.

Exit condition: human release authorization is recorded.

## 10. Deploy, Observe, and Learn
**Owners:** Release Manager and accountable service owner

After release:
- validate critical production behavior;
- observe errors, latency, cost, security, user impact, and business metrics as applicable;
- execute rollback when a declared trigger is reached;
- capture defects, decisions, and lessons as repository artifacts;
- update tasks, contracts, ADRs, tests, and context routing when knowledge changes.

Exit condition: the release is stable or safely rolled back, and new knowledge is retained.

## Reference Completion Report
```yaml
task_id:
result:
acceptance_evidence:
changed_artifacts:
contracts_changed:
adrs:
tests:
security_review:
quality_score:
mandatory_gates:
release_decision:
residual_risks:
follow_up:
```

## Golden Path Acceptance Test
MEOS v1.0 is usable only when a qualified contributor or AI agent can follow this path from the repository alone, identify its authority and required context, complete a ready task, provide independent evidence, and reach an unambiguous release decision without relying on hidden chat history.