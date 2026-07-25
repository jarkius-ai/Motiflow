# Motiflow Engineering Constitution

## Status
Version: 1.0  
Authority: Mandatory for all human and AI contributors  
Scope: Product, architecture, code, tests, infrastructure, documentation, and releases

## Purpose
This constitution defines the non-negotiable rules used to build and evolve Motiflow. It exists to prevent architectural drift, unverifiable work, incompatible agent decisions, and short-term shortcuts that damage the platform.

## 1. Business Meaning Before Implementation
Every change must trace to an approved product objective, user outcome, defect, operational need, or architectural decision. Code without a documented reason must not be merged.

Required traceability:

`Objective → Requirement → Task → Implementation → Verification`

## 2. Contracts Before Components
Agents and engineers must not invent APIs, events, schemas, states, or cross-module behavior during implementation.

Before dependent components are built, their contract must define:
- owner and consumers;
- inputs and outputs;
- validation rules;
- error behavior;
- versioning expectations;
- compatibility expectations.

Contract changes require impact review and, when architectural, an ADR.

## 3. Architecture Before Convenience
Implementation must follow approved boundaries and ownership rules. A locally convenient shortcut is not acceptable when it increases coupling, duplicates business logic, bypasses orchestration, or leaks infrastructure concerns into domain logic.

The following require explicit architectural review:
- new service or major module;
- new external dependency;
- new persistent data store;
- new integration pattern;
- movement of ownership between modules;
- change to a canonical artifact contract;
- change affecting security, tenancy, identity, or auditability.

## 4. Small, Reversible Changes
Work must be divided into the smallest coherent increments that can be independently reviewed, tested, and reverted.

Each change must:
- have one primary purpose;
- avoid unrelated refactoring;
- identify migration impact;
- provide rollback or recovery guidance when state or deployment behavior changes.

## 5. Verification Is Part of Implementation
Generated or written code is untrusted until verified.

A task is not complete because code exists. It is complete only when objective evidence demonstrates expected behavior.

Evidence may include:
- automated tests;
- build output;
- static analysis;
- contract validation;
- migration verification;
- security checks;
- performance measurements;
- documented manual validation where automation is not yet practical.

Claims such as “should work” or “looks correct” are not verification.

## 6. Mandatory Gates Cannot Be Averaged Away
The total quality score is supplemental. Mandatory failures cannot be offset by stronger scores elsewhere.

The following must pass when applicable:
- requirements and acceptance criteria;
- build and type checks;
- automated tests;
- contract compatibility;
- architecture conformance;
- security controls;
- data migration safety;
- documentation accuracy;
- human approval for protected decisions.

## 7. Iterate Until Accepted or Blocked
When a quality gate fails, the responsible agent must diagnose, improve, and rerun verification.

The loop continues until one of these conditions is met:
1. every mandatory gate passes and the quality score is at least 90;
2. a blocker requires human or product authority;
3. three consecutive iterations produce no measurable improvement;
4. further work would violate architecture, security, scope, or an approved contract.

The agent must not conceal failures, lower standards, delete meaningful tests, or narrow acceptance criteria merely to obtain a passing result.

## 8. One Source of Truth
Repository artifacts are authoritative over chat history, transient prompts, and undocumented assumptions.

When documents conflict, apply this precedence unless an approved ADR states otherwise:
1. Project Constitution and approved ADRs;
2. Product requirements and acceptance criteria;
3. Architecture and canonical contracts;
4. MEOS policies and standards;
5. task specification;
6. implementation comments and local notes.

A conflict must be resolved in the repository before implementation continues.

## 9. Documentation Changes With the System
Documentation is part of the implementation, not post-work cleanup.

A change must update all affected authoritative documents, including as applicable:
- contracts;
- architecture diagrams or descriptions;
- operational instructions;
- configuration references;
- test strategy;
- migration and rollback procedures;
- decision records.

## 10. Security and Privacy by Design
Security, privacy, tenancy, authorization, secrets handling, and auditability must be considered during design rather than added after implementation.

Contributors must:
- apply least privilege;
- validate all external input;
- avoid secrets in code, prompts, logs, examples, and fixtures;
- protect tenant and user boundaries;
- avoid logging sensitive payloads without an approved need;
- surface unresolved risks before merge.

## 11. Observability Is a Product Requirement
Production behavior must be diagnosable. Important workflows require sufficient logs, metrics, traces, correlation identifiers, and actionable error messages.

Observability must explain:
- what happened;
- where it failed;
- which workflow or request was affected;
- whether retry is safe;
- what an operator should do next.

## 12. Preserve Compatibility Deliberately
Breaking changes are not assumed acceptable.

For public or shared contracts, contributors must define:
- compatibility impact;
- migration path;
- deprecation period where appropriate;
- consumer update plan;
- rollback strategy.

## 13. Explicit Ownership
Every module, contract, task, and review decision must have an accountable owner. Shared ownership does not mean absent ownership.

Agents may recommend changes outside their authority but must not silently make protected decisions.

## 14. Separation of Duties
The creator of a change must perform self-review, but self-review is not independent approval.

For material changes, implementation and final review should be performed by separate roles or agents. Architecture, security, and release approval must remain independent when risk warrants it.

## 15. Stop Rather Than Guess
A contributor must stop and escalate when:
- requirements conflict or remain materially ambiguous;
- an authoritative contract is missing;
- required credentials or environments are unavailable;
- a protected architectural decision is needed;
- user data, security, or irreversible state may be at risk;
- evidence cannot support a completion claim.

Escalation must identify the blocker, attempted resolution, available options, recommendation, and impact of delay.

## 16. Definition of Engineering Integrity
Engineering integrity means:
- no fabricated test results;
- no hidden failures;
- no invented repository state;
- no claims of execution without evidence;
- no silent scope changes;
- no weakening of controls to make a gate pass.

Violating engineering integrity automatically rejects the contribution regardless of score.

## Enforcement
Any contribution that violates this constitution is rejected or returned to the Engineering Flywheel for correction.

Exceptions require:
1. documented rationale;
2. explicit owner;
3. risk assessment;
4. expiry or review date;
5. approval through the ADR or governance process.

## Contributor Acknowledgement
By contributing to Motiflow, a human or AI agent agrees to follow this constitution, disclose uncertainty, preserve repository truth, and submit only work supported by verifiable evidence.
