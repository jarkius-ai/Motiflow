# Motiflow Quality Gate and Engineering Flywheel

## Status
Version: 1.0  
Applies to: Every implementation task, pull request, architecture change, contract change, migration, and release

## Objective
The Quality Gate converts “done” from an opinion into an evidence-based decision. A contribution is accepted only when all mandatory gates pass and the weighted quality score reaches at least 90/100.

A score below 90 is not a final rejection by default. It returns the work to the Engineering Flywheel for diagnosis, correction, and re-verification.

## Engineering Flywheel

`Understand → Plan → Implement → Verify → Critique → Improve → Re-verify → Document → Submit`

The responsible contributor must retain evidence from each verification cycle.

## Decision Outcomes

### ACCEPT
Use only when:
- all applicable mandatory gates pass;
- quality score is at least 90;
- no unresolved blocker or material risk is hidden;
- required human approvals are complete.

### LOOP
Use when:
- a gate fails but the contributor has enough information and authority to correct it;
- the score is below 90;
- verification evidence is incomplete but obtainable;
- review identifies actionable defects.

The contributor must identify the lowest-scoring or failed area, apply a focused correction, and rerun all affected checks.

### BLOCKED
Use when autonomous correction is unsafe or impossible because of:
- ambiguous or conflicting requirements;
- missing product decision;
- missing or conflicting canonical contract;
- protected architecture decision;
- unavailable environment, credentials, or dependency;
- security, privacy, legal, or irreversible data risk;
- three consecutive iterations without measurable improvement.

A blocked report must state the exact decision needed, options, recommendation, evidence, and impact.

### REJECT
Use when:
- engineering integrity is violated;
- the contribution intentionally bypasses mandatory controls;
- scope or acceptance criteria were weakened to manufacture a pass;
- meaningful tests were deleted or disabled without approval;
- a known critical security or data-integrity issue remains;
- the work repeatedly ignores an explicit review decision.

## Mandatory Gates
A failed mandatory gate cannot be offset by the numerical score.

| Gate | Pass condition | Typical evidence |
|---|---|---|
| Requirement | Scope and acceptance criteria are satisfied | Traceability checklist, acceptance test results |
| Build | Project builds in the supported environment | CI build log |
| Static correctness | Type checks, linting, and required analysis pass | CI report |
| Automated tests | Applicable unit, integration, contract, and end-to-end tests pass | Test report |
| Architecture | Boundaries, ownership, and approved patterns are preserved | Architecture review |
| Contract | APIs, events, schemas, and compatibility rules are valid | Schema/contract validation |
| Security | No unresolved critical/high-risk issue; controls are implemented | Scan and security review |
| Data safety | Migration, rollback, idempotency, and integrity are verified | Migration test and recovery evidence |
| Documentation | Authoritative docs reflect the implemented behavior | Changed-document review |
| Review independence | Required independent reviews and approvals are complete | Review record |

A gate may be marked `Not Applicable` only with a written reason.

## Weighted Quality Score
Score each category from 0 to its maximum.

| Category | Maximum | Evaluation focus |
|---|---:|---|
| Correctness | 20 | Behavior matches requirements; edge cases and errors are handled |
| Architecture | 15 | Boundaries, contracts, ownership, and extensibility are sound |
| Test quality | 15 | Tests are meaningful, deterministic, appropriately layered, and maintainable |
| Maintainability | 10 | Code is understandable, cohesive, and avoids unnecessary complexity |
| Security and privacy | 10 | Threats, authorization, validation, secrets, tenancy, and sensitive data are handled |
| Reliability and data safety | 10 | Retries, idempotency, concurrency, failure recovery, and migrations are safe |
| Documentation and traceability | 10 | Intent, contracts, decisions, operations, and evidence are current and linked |
| Performance and efficiency | 5 | Resource use and latency are appropriate and measured where material |
| Operability | 5 | Logs, metrics, errors, diagnostics, and rollback support production operation |
| **Total** | **100** | Acceptance threshold: **90** |

## Scoring Anchors

### 0–49: Unacceptable
Major requirements are absent, behavior is unverified, or architecture/security risks are severe.

### 50–69: Incomplete
Some behavior exists, but important evidence, tests, contracts, or operational concerns are missing.

### 70–79: Functional but weak
The happy path may work, but quality, edge cases, maintainability, or production readiness is insufficient.

### 80–89: Nearly ready
The work is credible but still contains specific gaps that must be corrected before acceptance.

### 90–95: Accepted
All mandatory gates pass and the implementation is robust, maintainable, and supported by evidence.

### 96–100: Exceptional
The work is unusually clear, resilient, well-tested, operable, and improves reusable project knowledge without unnecessary scope.

A score of 100 is not expected and must not encourage over-engineering.

## Iteration Policy
When the result is `LOOP`, the contributor must create an iteration record containing:

```text
Iteration:
Current score:
Failed gates:
Primary root cause:
Changes made:
Evidence rerun:
New score:
Remaining risks:
Next action:
```

Rules:
1. Fix root causes rather than hiding symptoms.
2. Rerun every check affected by the change.
3. Do not assume an earlier passing result remains valid after related code changes.
4. Track whether the score measurably improves.
5. After three non-improving iterations, declare `BLOCKED` and escalate.

## Test Expectations
Select tests according to risk and architecture rather than chasing a universal coverage percentage.

Expected layers where applicable:
- unit tests for domain behavior and transformations;
- contract tests for APIs, events, and schemas;
- integration tests for persistence and external adapters;
- end-to-end tests for critical user workflows;
- migration tests for state changes;
- negative tests for validation, authorization, and failure paths;
- regression tests for resolved defects.

Coverage is supporting evidence, not proof of correctness. High coverage with weak assertions does not earn a passing test-quality score.

## Security Severity Rule
- Critical unresolved issue: automatic `REJECT`.
- High unresolved issue: mandatory security gate fails unless a formally approved exception exists.
- Medium issue: must have an owner, mitigation, and due date before acceptance.
- Low issue: document and prioritize according to risk.

## Quality Report Template
Every material contribution should provide:

```markdown
## Quality Gate Result

Outcome: ACCEPT | LOOP | BLOCKED | REJECT
Score: __ / 100

### Mandatory Gates
- Requirement: PASS/FAIL/N/A — evidence
- Build: PASS/FAIL/N/A — evidence
- Static correctness: PASS/FAIL/N/A — evidence
- Automated tests: PASS/FAIL/N/A — evidence
- Architecture: PASS/FAIL/N/A — evidence
- Contract: PASS/FAIL/N/A — evidence
- Security: PASS/FAIL/N/A — evidence
- Data safety: PASS/FAIL/N/A — evidence
- Documentation: PASS/FAIL/N/A — evidence
- Review independence: PASS/FAIL/N/A — evidence

### Category Scores
- Correctness: __/20
- Architecture: __/15
- Test quality: __/15
- Maintainability: __/10
- Security and privacy: __/10
- Reliability and data safety: __/10
- Documentation and traceability: __/10
- Performance and efficiency: __/5
- Operability: __/5

### Remaining Risks
- ...

### Verification Evidence
- ...

### Decision
- ...
```

## Anti-Gaming Rules
The following are prohibited:
- changing acceptance criteria after implementation without product approval;
- marking a gate `Not Applicable` to avoid corrective work;
- replacing meaningful assertions with superficial tests;
- suppressing errors or warnings without documented justification;
- excluding failing files from checks merely to pass CI;
- reporting a score without supporting evidence;
- allowing the implementer to provide the only final approval for material work.

## Human Authority
Humans retain final authority for:
- product trade-offs;
- acceptance of material residual risk;
- exceptions to this policy;
- protected architectural changes;
- production release authorization until explicitly delegated.

Human approval does not make failed evidence pass. Approved exceptions must be documented, owned, time-bounded, and reviewable.

## Success Criterion
The Quality Gate succeeds when every accepted contribution has traceable requirements, reproducible verification, transparent risk, and no failed mandatory gate—and when sub-90 work is improved through the loop rather than prematurely delivered.
