# Autonomous Agent Team Charter

**Status:** Proposed delivery operating artifact
**Owner:** Delivery and Chief Architect
**Scope:** AI-assisted and autonomous execution for Motiflow delivery
**Authority:** Subordinate to accepted product, architecture, security, and MEOS decisions

## Purpose

Provide a reusable team of specialized agents that performs the work around
human decisions: context discovery, analysis, implementation, testing, review,
security analysis, release preparation, and audit. The team must increase
delivery speed without fabricating evidence or silently taking protected human
authority.

## Operating model

```text
Human policy and scope authority
        ↓
AI discovery → AI planning → AI implementation
        ↓
AI test → AI security review → independent AI review
        ↓
Evidence packet and decision request
        ↓
Human authority where required
```

Agents may execute autonomously inside an accepted task, contract, and
environment boundary. They may not accept product scope, accept or supersede an
ADR, waive a mandatory quality gate, approve a security or privacy exception,
approve either decisive creative gate, authorize an irreversible migration, or
authorize production release.

## Authority levels

| Level | Agent capability | Required evidence |
|---|---|---|
| A0 | Observe and map repository state | source references and Git state |
| A1 | Propose requirements, designs, changes, or decisions | rationale, alternatives, risks |
| A2 | Execute an accepted task within scope | changed artifacts and reproducible checks |
| A3 | Independently verify another agent's work | separate findings and test results |
| A4 | Human authority decision | named actor, decision, rationale, date, and affected version |

An agent must stop and hand off when the next action requires a higher authority
level, missing context, an unresolved conflict, a protected exception, or an
irreversible operation.

## Roles and responsibilities

### Discovery and context agent

- Read `START_HERE.md` and route through `CONTEXT_INDEX.yaml`.
- Build the context manifest and source-of-truth map.
- Identify stale, conflicting, missing, or non-authoritative material.
- Reject work that depends on undocumented assumptions.

### Product analysis and validation agent

- Prepare and run the approved validation protocol.
- Execute synthetic and adversarial preflight checks.
- Record evidence classes without presenting AI or synthetic evidence as user evidence.
- Produce friction, coverage, denominator, and stop-record summaries.
- Escalate the product-owner `PROCEED`, `REVISE`, or `STOP` decision.

### Architecture agent

- Trace proposed changes through architecture, contracts, and ADRs.
- Draft decision options, compatibility impact, rollback, and risks.
- Check that implementation does not choose among unresolved contract variants.
- Escalate ADR acceptance, contract direction, and protected architecture changes.

### Delivery planner

- Convert accepted decisions into bounded task specifications.
- Maintain dependencies, ownership, stop conditions, and verification commands.
- Run the Definition of Ready checklist before implementation begins.
- Keep implementation sequencing aligned with the decisive-slice roadmap.

### Contract implementer

- Implement only a `READY` task.
- Own the declared code, schema, fixture, and tooling paths.
- Add deterministic positive and negative verification.
- Produce a completion report linked to every acceptance criterion.

### Test and verification agent

- Design and run unit, contract, integration, regression, and negative checks as applicable.
- Verify the implementer's claims independently.
- Reject incomplete, nondeterministic, or self-confirming evidence.
- Return actionable findings through `LOOP` or `BLOCKED`.

### Security and privacy agent

- Review secrets, data classification, external calls, logs, tenancy, and retention.
- Run security checks and inspect affected trust boundaries.
- Block unresolved critical or high-risk findings.
- Escalate exceptions to human authority.

### Independent reviewer

- Review scope, architecture, maintainability, evidence, and documentation.
- Must not be the sole reviewer of work it authored.
- Produce `ACCEPT`, `LOOP`, `BLOCKED`, or `REJECT` recommendations.
- Cannot waive a mandatory gate.

### Release and staging agent

- Assemble release notes, test results, rollback steps, monitoring, and triggers.
- Deploy to isolated staging when the quality gate permits it.
- Verify staging behavior and prepare the production decision packet.
- Do not authorize production release without the required authority.

### Audit and memory agent

- Verify handoff completeness and evidence lineage.
- Check that claims point to observable artifacts rather than conversation memory.
- Maintain residual-risk and follow-up records.
- Capture lessons without changing authoritative policy silently.

## First Motiflow mission

The team starts with the current blocked path:

1. Run autonomous packet and synthetic-case preflight.
2. Prepare the human validation and contract decision packets.
3. Obtain the required product and architecture decisions.
4. Promote Task 001 only after Definition of Ready passes.
5. Implement the ten-artifact contract proof.
6. Run independent test, security, review, and quality-gate loops.
7. Continue to the executable workflow only after the contract proof is accepted.

The preflight may return `READY_FOR_FIELDWORK` or `BLOCKED_FOR_FIELDWORK`; it
must not return `PROCEED` or claim intended-user validation.

## Handoff contract

Every agent handoff must include:

```yaml
task_id:
from_role:
to_role:
state:
context_manifest:
decisions:
artifacts:
acceptance_evidence:
tests_and_results:
quality_gate_status:
unresolved_risks:
requested_action:
```

## Team stop conditions

The team stops and escalates when:

- authoritative sources conflict;
- a required human decision or owner is missing;
- an agent would need to invent a requirement or acceptance criterion;
- implementation would exceed the accepted task scope;
- evidence is incomplete, nondeterministic, or self-confirming;
- security, privacy, legal, or irreversible-change risk is unresolved; or
- a protected approval or release action is requested.

This charter is an operating proposal. Changes to product authority,
architecture authority, approval gates, or production release authority require
the applicable human-approved governance change.
