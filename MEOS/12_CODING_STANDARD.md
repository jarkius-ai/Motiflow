---
id: MEOS-012
title: Coding Standard
status: approved
owner: Engineering Lead
version: 1.0
authoritative: true
readers: [backend, frontend, ai_engineer, reviewer, qa]
provides: [coding-rules, implementation-baseline, ai-code-policy]
requires: [MEOS-001, MEOS-005, MEOS-011]
related: [MEOS/10_QUALITY_GATE.md, MEOS/13_REVIEW_STANDARD.md, docs/02-architecture/**]
---

# Coding Standard

## Purpose
Define the minimum implementation standard for all human- and AI-authored code in Motiflow. These rules optimize for correctness, clarity, security, maintainability, and verifiable delivery.

## 1. Core Principles
- Prefer the simplest design that satisfies the approved task and contracts.
- Optimize for readability before cleverness.
- Keep business meaning visible in names, types, boundaries, and tests.
- Do not duplicate domain rules across layers.
- Do not invent requirements, APIs, schemas, events, or configuration.
- Every behavior change must be traceable to a task, requirement, contract, or ADR.
- Preserve backward compatibility unless a breaking change is explicitly approved.

## 2. Repository and Module Structure
- Follow the existing repository structure and framework conventions.
- New top-level directories require architecture approval.
- Organize code by clear responsibility; avoid mixed-purpose modules.
- Keep domain logic separate from transport, persistence, UI, and infrastructure concerns.
- Public interfaces must be intentionally small and documented.
- Shared utilities require at least two proven consumers; speculative abstractions are prohibited.

## 3. Naming
- Use names that express domain intent, not implementation trivia.
- Classes, modules, functions, variables, events, commands, and tests must follow the language and framework conventions already used by the repository.
- Avoid vague names such as `data`, `handler`, `manager`, `utils`, `temp`, and `misc` unless their scope is unambiguous.
- Boolean names should read as predicates, such as `isActive`, `hasPermission`, or `canRetry`.
- Names must not encode obsolete implementation details.

## 4. Functions and Classes
- Each function or method should have one clear responsibility.
- Prefer small cohesive units over long procedures.
- Make side effects explicit.
- Use dependency injection or explicit parameters instead of hidden global state.
- Avoid deep nesting; use guard clauses and extraction when it improves clarity.
- Do not create abstractions without a demonstrated need.
- Public behavior must be covered by tests or equivalent executable verification.

## 5. Types and Contracts
- Use the strongest practical type system available.
- Validate all external input at system boundaries.
- Treat API, event, schema, prompt, workflow, and UI contracts as authoritative.
- Contract changes must declare compatibility impact, migration needs, and rollback strategy.
- Never silently coerce invalid business data.
- Unknown or unsupported values must fail safely and visibly.

## 6. Error Handling
- Fail explicitly with actionable errors.
- Distinguish validation errors, business-rule failures, transient infrastructure failures, and unexpected defects.
- Do not swallow exceptions or return ambiguous success states.
- Preserve root-cause context while avoiding exposure of secrets or sensitive data.
- Retry only operations proven to be safe and idempotent.
- Every retry policy must define limits, backoff, timeout, and terminal behavior.
- User-facing errors must be understandable without exposing internal implementation details.

## 7. Logging and Observability
- Log meaningful events, decisions, failures, and state transitions.
- Use structured logs where supported.
- Include correlation or trace identifiers for distributed workflows.
- Never log secrets, credentials, tokens, full sensitive payloads, or unnecessary personal data.
- Avoid noisy logs in hot paths.
- New critical workflows must define useful metrics, alerts, and diagnostic evidence.

## 8. Security and Privacy
- Follow least privilege and deny-by-default behavior.
- Validate authorization independently from authentication.
- Treat all external input as untrusted.
- Use approved secret storage; secrets must never be committed.
- Use parameterized queries and framework protections against injection.
- Protect sensitive data in transit and at rest according to project requirements.
- Security-sensitive changes require review by the security reviewer role.
- Any discovered critical vulnerability, secret exposure, or privacy risk is a stop condition.

## 9. Performance and Reliability
- Meet the performance constraints declared in the task or architecture.
- Measure before optimizing.
- Avoid unbounded loops, queries, queues, retries, payloads, and memory growth.
- Prevent avoidable N+1 access patterns and repeated expensive operations.
- Define timeout and cancellation behavior for external calls.
- Design state-changing operations for idempotency when retries or duplicate delivery are possible.
- Document material performance tradeoffs.

## 10. Testing
- Tests must verify observable behavior and acceptance criteria.
- Use the lowest-cost test level that provides sufficient confidence.
- Critical domain logic requires unit tests.
- Boundaries and integrations require integration or contract tests.
- Critical user journeys require end-to-end verification where practical.
- Bug fixes require a regression test unless technically impossible and explicitly documented.
- Tests must be deterministic, isolated, readable, and safe to run repeatedly.
- Do not weaken or delete tests merely to make a change pass.

## 11. Documentation
- Update documentation in the same change as affected behavior.
- Public interfaces and non-obvious decisions require concise documentation.
- Architecture-impacting changes require an ADR under `MEOS/14_ADR_PROCESS.md`.
- Comments should explain why, constraints, or risk—not restate code.
- Remove stale comments and obsolete documentation.

## 12. Dependencies
- Prefer existing approved dependencies.
- New dependencies require a documented need and evaluation of maintenance, license, security, size, and operational impact.
- Avoid dependencies for trivial functionality.
- Pin or constrain versions according to project tooling.
- Remove unused dependencies promptly.

## 13. AI-Generated Code
AI-generated code is untrusted until independently verified.

An AI agent must:
- read the task specification and required context before editing;
- state assumptions and stop on unresolved ambiguity;
- preserve existing architecture and contracts;
- generate or update relevant tests;
- run available checks and report exact evidence;
- disclose incomplete verification and residual risk;
- avoid broad rewrites unless explicitly authorized;
- never claim a result it did not verify.

AI-generated code must receive independent review for non-trivial, architecture-sensitive, security-sensitive, data-migration, or release-critical work.

## 14. Change Discipline
- Keep changes focused on the approved task.
- Separate unrelated refactors from behavior changes.
- Prefer small, reviewable commits with clear messages.
- Do not reformat unrelated files.
- Preserve public behavior during refactors unless change is explicitly approved.
- Every migration must include forward, rollback, and verification steps.

## 15. Required Completion Evidence
A code change is not complete until it includes:
- task and acceptance-criteria traceability;
- files and contracts changed;
- tests and checks executed with results;
- documentation impact;
- compatibility and migration assessment;
- security and privacy assessment where applicable;
- residual risks and follow-up work;
- quality-gate outcome.

## 16. Enforcement
Violations produce one of the outcomes defined by `MEOS/10_QUALITY_GATE.md`:
- `ACCEPT` — compliant and sufficiently verified;
- `LOOP` — correctable gaps remain;
- `BLOCKED` — required context, decision, or environment is unavailable;
- `REJECT` — unacceptable risk or non-compliance.
