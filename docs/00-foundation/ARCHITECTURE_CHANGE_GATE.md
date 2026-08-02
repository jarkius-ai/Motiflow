# Motiflow Architecture Change Gate

- **Status:** Accepted governance checklist
- **Owner:** Chief Architect and MEOS
- **Related decision:** ADR-0006
- **Purpose:** Prevent architectural drift when introducing or changing a capability

## Use this gate when

Apply this checklist before work that may:

- add a product capability;
- change a system boundary or dependency direction;
- add a provider, protocol, framework, database, queue, or external platform;
- change a canonical artifact, approval, provenance, workflow, or security contract;
- activate a future roadmap phase;
- introduce browser automation, authenticated acquisition, proxy infrastructure, or external write actions;
- move information between canonical documents.

## Decision path

```text
Need or evidence
      ↓
Fits Project Charter?
      ↓
Fits Master Context and accepted architecture?
      ↓
Exists in Target Platform Blueprint or requires target update?
      ↓
What is its current Capability Map state?
      ↓
Which Roadmap phase and activation gate apply?
      ↓
Is an ADR mandatory?
      ↓
Are contracts, security, data, and human authority resolved?
      ↓
Is there a READY MEOS task?
      ↓
Implement and verify
      ↓
Update capability state and evidence
```

## Checklist

### 1. Product fit

- [ ] Target user and problem are explicit.
- [ ] Expected outcome and business reason are measurable.
- [ ] The change fits the Charter's durable scope.
- [ ] Non-goals and rejected behavior are explicit.
- [ ] Product validation is available or planned where uncertainty is material.

### 2. Architecture fit

- [ ] The change preserves ACDS identity and canonical terminology.
- [ ] Component ownership is explicit.
- [ ] Dependency direction remains valid.
- [ ] No second artifact envelope, workflow-state owner, approval model, provenance system, or policy authority is introduced.
- [ ] Provider-specific behavior remains behind an approved connector or gateway.
- [ ] Expansion occurs through a versioned seam or an accepted new seam.

### 3. Authority and documentation

- [ ] The canonical owner for each changed fact is identified.
- [ ] Charter changes are limited to product purpose or durable scope.
- [ ] Master Context changes are limited to stable architecture.
- [ ] Blueprint changes are limited to target capabilities, boundaries, or seams.
- [ ] Capability Map records current state accurately.
- [ ] Roadmap records phase and activation impact.
- [ ] `START_HERE.md`, `CONTEXT_INDEX.yaml`, and Document Index are updated only when routing changes.
- [ ] No duplicated authoritative copy remains.

### 4. ADR trigger

An ADR is mandatory when any answer is yes:

- [ ] Does the change alter a system boundary or dependency direction?
- [ ] Does it introduce a strategic provider, framework, protocol, database, queue, model platform, or external execution mechanism?
- [ ] Does it change a public, persisted, security-sensitive, or cross-team contract?
- [ ] Does it change approval or human-authority semantics?
- [ ] Does it create a difficult-to-reverse migration?
- [ ] Does it change product/runtime identity or canonical terminology?
- [ ] Does it materially affect security, privacy, reliability, cost, scalability, or operability?

### 5. Security and external technology

- [ ] Data classification and retention are explicit.
- [ ] Credentials and permissions use least privilege.
- [ ] Research and publishing credentials remain separate.
- [ ] External content is treated as untrusted.
- [ ] Prompt-injection and unsafe-content controls are defined where applicable.
- [ ] Browser, authenticated, proxy, or write access has explicit legal/security review.
- [ ] Public read paths cannot silently escalate to higher-risk access.
- [ ] Provider failure, replacement, and disablement are defined.

### 6. Contracts and migration

- [ ] Inputs, outputs, errors, and owned state are defined.
- [ ] Versioning and compatibility classification are explicit.
- [ ] Idempotency and concurrency concerns are addressed.
- [ ] Invalidation and downstream impact are defined.
- [ ] Migration, rollback, or safe-stop behavior is documented.
- [ ] Observability and evidence requirements are defined.

### 7. Delivery readiness

- [ ] The applicable roadmap activation gate passes.
- [ ] Dependencies and environments are available.
- [ ] A bounded MEOS task exists.
- [ ] Definition of Ready passes.
- [ ] Independent reviewer and QA roles are assigned.
- [ ] Acceptance criteria and verification commands are observable.
- [ ] Human decisions are recorded where protected authority applies.

### 8. Completion

- [ ] Required code, schemas, tests, and documentation are complete.
- [ ] Mandatory MEOS quality gates pass.
- [ ] Evidence is reproducible and linked.
- [ ] Capability Map state is updated from evidence—not aspiration.
- [ ] Project Bootstrap reflects any material milestone change.
- [ ] Remaining risks and follow-up work are owned.

## External provider rule

Naming a provider in research or a blueprint does not select it. Provider selection occurs only through the applicable capability contract, architecture/security decision, ready task, and comparative evidence.

This applies to Agent Reach, model providers, reader services, browser bridges, Playwright/CDP, semantic browser tools, publishing platforms, and proxy services.

## Outcome record

```yaml
change_id:
product_fit: PASS | FAIL | PENDING
architecture_fit: PASS | FAIL | PENDING
adr_required: true | false
adr_ref:
capability:
current_state:
target_phase:
security_review:
contract_refs: []
task_ref:
readiness: READY | CONDITIONALLY_READY | NOT_READY | BLOCKED
human_decisions: []
verification: []
remaining_risks: []
next_action:
```
