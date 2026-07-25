---
id: MEOS-013
title: Review Standard
status: approved
owner: Engineering Lead
version: 1.0
authoritative: true
readers: [reviewer, qa, security_reviewer, chief_architect, release_manager]
provides: [review-method, review-evidence, approval-rules]
requires: [MEOS-001, MEOS-005, MEOS-010, MEOS-011, MEOS-012]
related: [MEOS/10_QUALITY_GATE.md, MEOS/14_ADR_PROCESS.md, MEOS/19_AI_WORKFORCE_CHARTER.md]
---

# Review Standard

## Purpose
Define how Motiflow changes are independently reviewed and how review evidence supports the Quality Gate. Review is a verification activity, not a stylistic preference exercise.

## 1. Review Objectives
A review must determine whether the change:
- satisfies the approved task and acceptance criteria;
- preserves or intentionally changes declared contracts;
- complies with architecture and coding rules;
- is correct, secure, maintainable, observable, and testable;
- includes sufficient evidence for an independent decision;
- can be safely released and rolled back when applicable.

## 2. Independence and Separation of Duties
- An author may self-review but may not provide the only approval for non-trivial work.
- Architecture-sensitive changes require Chief Architect review.
- Security-sensitive changes require Security Reviewer participation.
- QA independently verifies acceptance criteria for release-critical changes.
- The Release Manager owns the final release-readiness decision.
- AI-generated work follows the same or stricter review standard as human-authored work.

## 3. Required Review Inputs
The reviewer must have access to:
- task specification and acceptance criteria;
- context manifest or authoritative references;
- implementation diff;
- affected contracts and ADRs;
- test and validation results;
- migration and rollback information where applicable;
- documentation changes;
- known assumptions, limitations, and residual risks.

Missing required evidence results in `BLOCKED` or `LOOP`, never speculative approval.

## 4. Review Order
Review in this sequence to avoid polishing fundamentally incorrect work:

1. Scope and requirement alignment
2. Contract and architecture compliance
3. Correctness and state behavior
4. Security and privacy
5. Reliability and failure handling
6. Tests and verification evidence
7. Maintainability and simplicity
8. Performance and observability
9. Documentation and operational readiness
10. Release, migration, and rollback safety

## 5. Scope and Requirement Review
Confirm that:
- the change maps to an approved task;
- every acceptance criterion has evidence or a clear verification plan;
- out-of-scope work has not been introduced;
- assumptions are explicit and approved where necessary;
- no requirement, API, schema, event, or behavior was invented;
- unrelated refactors or formatting are excluded.

## 6. Contract and Architecture Review
Confirm that:
- affected contracts are identified;
- compatibility impact is correctly classified;
- dependencies follow `MEOS/11_ARCHITECTURE_RULES.md`;
- domain boundaries remain coherent;
- architecture-significant decisions have an ADR;
- obsolete decisions are superseded, not silently contradicted;
- data ownership and state transitions are explicit;
- failure, retry, timeout, and idempotency behavior are defined where relevant.

## 7. Correctness Review
Inspect:
- happy paths, boundary cases, and failure paths;
- validation and authorization behavior;
- state transitions and invariants;
- concurrency, duplicate delivery, and retry effects;
- error propagation and recovery;
- time, locale, ordering, and nullability assumptions;
- resource cleanup and transaction boundaries;
- backward compatibility.

A reviewer must not infer correctness solely from clean code or passing unit tests.

## 8. Security and Privacy Review
Check for:
- authentication and authorization gaps;
- injection, unsafe parsing, or untrusted input handling;
- secret or credential exposure;
- excessive privileges;
- sensitive logging or data leakage;
- insecure defaults;
- missing rate limits or abuse controls where applicable;
- unsafe dependency changes;
- privacy, retention, and compliance impact.

Critical security or privacy risk results in `REJECT` or `BLOCKED`.

## 9. Reliability and Operations Review
Confirm that:
- external calls have timeouts and failure handling;
- retries are bounded and safe;
- state-changing operations are idempotent where required;
- logs and metrics make failures diagnosable;
- operational limits are explicit;
- migrations are reversible or have an approved recovery plan;
- rollback triggers are measurable;
- partial failure does not create silent corruption.

## 10. Test Review
Reviewers must assess test quality, not just test quantity.

Tests should:
- map to acceptance criteria and risks;
- verify externally observable behavior;
- cover regression cases for fixed defects;
- include negative and boundary scenarios;
- be deterministic and repeatable;
- avoid overspecifying implementation details;
- use realistic contract and integration behavior;
- fail for the intended reason before the fix when practical.

The reviewer must record exact commands or evidence used. Unrun tests must be labeled unverified.

## 11. Maintainability Review
Confirm that:
- names express business intent;
- responsibilities are cohesive;
- duplication is not introduced;
- abstractions are justified by current needs;
- complexity is proportional to the problem;
- code follows `MEOS/12_CODING_STANDARD.md`;
- comments explain constraints and decisions rather than restating code;
- future maintainers can diagnose and safely modify the implementation.

## 12. Performance Review
When performance is relevant, confirm that:
- constraints and expected load are stated;
- queries, loops, payloads, retries, and memory are bounded;
- expensive operations are not repeated unnecessarily;
- measurements support optimization claims;
- performance tradeoffs are documented;
- degradation and capacity risks are observable.

## 13. AI-Specific Review
For AI, prompt, retrieval, agent, or model changes, verify:
- input and output contracts;
- deterministic constraints where required;
- evaluation criteria and representative test cases;
- hallucination and unsupported-claim handling;
- prompt injection and data-exfiltration controls;
- privacy and model-provider data handling;
- cost, latency, fallback, and timeout behavior;
- human-review boundaries;
- model or prompt version traceability;
- explicit disclosure of probabilistic limitations.

## 14. Documentation Review
Confirm that:
- changed behavior and interfaces are documented;
- task, contract, ADR, and code references resolve;
- authoritative documents do not conflict;
- obsolete guidance is removed or archived;
- context routing and metadata are updated when needed;
- release notes describe user-visible or operational impact.

## 15. Finding Severity
Use the following levels:

### Critical
Could cause severe security exposure, data loss, irreversible corruption, major compliance failure, or unsafe release. Blocks approval.

### High
Likely correctness, architecture, security, or reliability failure with significant impact. Blocks approval.

### Medium
Material maintainability, test, observability, performance, or edge-case gap. Normally requires correction before approval unless explicitly accepted by the accountable human.

### Low
Minor clarity, consistency, or polish issue with limited operational impact. May be resolved now or tracked.

### Question
A request for clarification, not a defect. Approval cannot rely on an unanswered material question.

## 16. Review Outcomes
Every review ends with exactly one outcome:

### ACCEPT
All mandatory gates pass, evidence is sufficient, and no unresolved blocking finding remains.

### LOOP
The direction is valid, but correctable deficiencies remain. Return to the implementer with specific required changes.

### BLOCKED
The reviewer cannot complete verification because required context, decision, environment, access, or evidence is unavailable.

### REJECT
The change violates non-negotiable requirements, introduces unacceptable risk, or requires fundamental redesign.

## 17. Review Report Template

```yaml
review:
  task_id: TASK-000
  reviewer: role-or-human
  independence_confirmed: true
  outcome: ACCEPT | LOOP | BLOCKED | REJECT
  reviewed_commit_or_diff: reference

  acceptance_criteria:
    - id: AC-01
      status: pass | fail | unverified
      evidence: reference

  findings:
    - id: FINDING-01
      severity: critical | high | medium | low | question
      area: correctness | architecture | security | reliability | test | performance | documentation | scope
      description: concise observable issue
      required_action: explicit correction or decision

  checks:
    architecture: pass | fail | not-applicable
    contracts: pass | fail | not-applicable
    security: pass | fail | not-applicable
    tests: pass | fail | unverified
    documentation: pass | fail | not-applicable
    migration_and_rollback: pass | fail | not-applicable

  residual_risks:
    - risk and accountable owner

  notes: concise decision rationale
```

## 18. Approval Rules
- Approval must reference evidence, not confidence or reputation.
- A passing automated check does not replace human or independent review where mandated.
- No reviewer may silently weaken acceptance criteria.
- No unresolved Critical or High finding may ship.
- Accepted Medium findings require explicit risk ownership and follow-up.
- A change may not be approved when the reviewer cannot explain its behavior, failure modes, and rollback path.

## 19. Review Completion
Review is complete only when:
- findings are recorded and resolved or explicitly accepted;
- acceptance evidence is traceable;
- the review outcome is unambiguous;
- required specialists participated;
- the Quality Gate can consume the review result;
- the next owner and action are identified.
