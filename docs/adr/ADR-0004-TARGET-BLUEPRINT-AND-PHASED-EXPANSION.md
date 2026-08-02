# ADR-0004: Target Blueprint Responsibility Model and Phased Expansion

- **Status:** Accepted
- **Date:** 2026-08-02
- **Decision owners:** Jarkius — Product Owner, Chief Architect, Engineering Lead
- **Related change:** Draft PR #7
- **Supersedes:** None
- **Superseded by:** None

## Context

Motiflow has two valuable bodies of work:

1. The existing repository, which defines Motiflow, the Autonomous Creative Direction System (ACDS), the Motiflow Engineering Operating System (MEOS), the decisive creative workflow, contracts, validation gates, and current delivery state.
2. A separately authored v0.5.0 future-platform blueprint, which describes broader acquisition, browser, editorial, publication, publishing, measurement, and enterprise capabilities.

Adopting the external blueprint verbatim would create competing authority, duplicate MEOS responsibilities, encourage speculative repository generation, and risk confusing future capabilities with current implementation.

Discarding it would lose a valuable long-term platform design.

The repository therefore requires an explicit responsibility model that preserves the future destination while keeping current product authority, delivery governance, tasks, and evidence unambiguous.

## Decision drivers

- One clear source of truth for humans and AI agents.
- A complete long-term platform destination without a big-bang implementation.
- A focused creative-direction MVP as the first product.
- No duplicate architecture, artifact, provenance, approval, or workflow-state ownership.
- Explicit separation of vision, architecture, state, sequencing, execution, and evidence.
- Provider neutrality for Agent Reach, browser technologies, APIs, and future connectors.
- Incremental repository growth based on accepted contracts and ready tasks.
- Reduced context load and lower risk of LLM interpretation drift.

## Considered options

### Option A — Replace the repository with the external blueprint

Rejected. It would weaken the repository's layered authority, duplicate MEOS, conflict with the existing ACDS product wedge, and treat a 193-file target manifest as immediate implementation authority.

### Option B — Keep the external blueprint separate

Rejected. Two parallel workspaces would drift and leave future agents uncertain which source controls product and architecture decisions.

### Option C — Import the full blueprint as a second canonical authority

Rejected. It would preserve detail but not responsibility separation. Current state, delivery phases, tasks, and target architecture would remain mixed.

### Option D — Reconcile the blueprint into repository-owned documents with one owner per concern

Accepted.

## Decision

Motiflow adopts the following documentation responsibility model:

| Concern | Canonical owner |
|---|---|
| Why Motiflow exists and durable product scope | `PROJECT_CHARTER.md` |
| Stable product/runtime identity and architecture | `MASTER_CONTEXT.md` |
| Complete future capability destination and expansion seams | `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md` |
| Evidence-based current state of every capability | `docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md` |
| Ordered expansion phases and activation gates | `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md` |
| Mapping from the external blueprint into repository authority | `docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md` and manifest disposition records |
| Consequential architecture decisions | Accepted ADRs |
| Readiness, roles, execution, review, quality, and release | MEOS |
| Today's authorized work | Ready MEOS task specifications |
| What actually exists and works | Implementation, tests, and verification evidence |

The Target Platform Blueprint is the **destination architecture**. It defines capability domains, component responsibilities, trust boundaries, architectural constraints, and stable expansion seams. It does not own delivery phases, task readiness, CI commands, exact test plans, current implementation state, provider installation, or release authorization.

The Capability Expansion Roadmap owns Phase 0 through Phase 8 and the jigsaw delivery sequence. A roadmap phase does not authorize implementation. Every phase still requires accepted decisions, applicable product evidence, contracts, security review, ready tasks, and MEOS verification.

The Capability Map is the only portfolio-level statement of whether a capability is implemented, validated, contracted, review-ready, planned, deferred, experimental, or rejected. Prose in the blueprint cannot promote a capability's state.

## Product and build direction

The first product remains the creative-direction MVP:

```text
Intake Package
→ Normalized Brief
→ Knowledge Fusion Package
→ Creative Direction Package
→ Direction Approval Record
→ Generation Specification
→ Generated Candidate Set
→ Critic Evaluation Package
→ Final Approval Record
→ Provenance Record
```

The build sequence remains:

- Pre-Phase 1: intended-user validation, product decision, contract acceptance, and ADR-0003.
- Phase 1: ten-artifact schema, fixture, validator, and CI contract proof.
- Phase 2: executable creative core through direction approval.
- Phase 3: one-provider generation, critics, final approval, and provenance.
- Phase 4: read-only acquisition and optional Agent Reach adapter.
- Phase 5: editorial intelligence and Publication Package.
- Phase 6: one governed publishing connector and optional browser provider.
- Phase 7: measurement and governed learning.
- Phase 8: enterprise and ecosystem expansion.

Later phases extend accepted seams. They may not bypass or replace the validated creative core.

## Provider and external technology decision

The architecture defines provider-neutral capability interfaces rather than vendor commitments.

### Agent Reach

Agent Reach is a deferred optional Phase 4 acquisition-provider adapter behind the Connector Gateway. It is not part of the core runtime and does not own Motiflow contracts, workflow state, credentials, normalization, provenance, policy, approval, or learning.

It is not installed or authorized by this ADR. Activation requires a security and supply-chain review, accepted acquisition contracts, a bounded proof of concept, and a ready task.

### Browser execution

Extension Bridge, CDP/Playwright, and semantic browser technologies are deferred provider options behind a browser/execution connector seam. No browser provider is selected or authorized by this ADR.

### Proxy infrastructure

Proxy infrastructure is not a target requirement and is not authorized. Any legitimate future use requires a separately documented product need, security/legal review, accepted policy and contracts or ADR, and a ready task. Automatic escalation from a public read path to a proxy or authenticated path is prohibited.

## Repository introduction rule

The external blueprint's 193-file manifest is retained as historical design inventory and disposition evidence. It is not a current path allow-list and must not be used for mass repository generation.

A new file, directory, package, connector, schema, registry, workflow, script, or template is introduced only when:

- an accepted contract requires it;
- an accepted architecture decision requires it;
- a ready task owns it;
- executable code, governed fixtures, or durable evidence will live there; or
- an authoritative document requires that exact artifact.

## Context-routing decision

Every human or AI session begins with:

```text
START_HERE.md
→ PROJECT_CHARTER.md
→ MASTER_CONTEXT.md
→ CONTEXT_INDEX.yaml
→ MEOS/20_PROJECT_BOOTSTRAP.md
→ task-specific authorities and evidence
```

The target blueprint and roadmap are loaded only for future-capability planning, architecture expansion, reconciliation, or phase activation. They are not part of every implementation task's default context.

When documents conflict or state is unclear, work stops and the repository authority and ADR process are applied. Agents must not infer implementation from target architecture.

## Consequences

### Positive

- The external blueprint becomes useful without becoming a competing constitution.
- Every major document has one canonical responsibility.
- The full platform remains visible while implementation stays incremental.
- Future LLMs can distinguish product, architecture, current state, roadmap, engineering governance, tasks, and evidence.
- Provider technologies remain replaceable.
- The repository avoids speculative structure and duplicate systems.

### Negative

- Some information must move from the target blueprint into the roadmap, capability map, MEOS, tasks, engineering documents, or evidence reports.
- Cross-references must be maintained when responsibilities change.
- Future architecture proposals require updates to multiple correctly owned documents rather than one monolithic file.

These costs are accepted because they reduce long-term ambiguity and drift.

## Migration

1. Refactor `TARGET_PLATFORM_BLUEPRINT.md` into a pure destination-architecture document.
2. Keep phases and activation gates in `CAPABILITY_EXPANSION_ROADMAP.md`.
3. Keep current state in `TARGET_PLATFORM_CAPABILITY_MAP.md`.
4. Keep implementation rules and readiness in MEOS.
5. Keep bounded work in task specifications.
6. Keep verification truth in evidence and implementation artifacts.
7. Update `START_HERE.md`, `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, the Document Index, reconciliation documents, and PR description.
8. Record the accepted direction without changing Task 001 readiness.

## Verification

This decision is implemented correctly when:

- every major document states its responsibility and non-responsibilities;
- the blueprint contains no detailed delivery phase, task, CI, or current-state ownership;
- the roadmap owns the complete phase sequence;
- the capability map owns all portfolio state claims;
- MEOS remains the only engineering governance system;
- `START_HERE.md` clearly explains Motiflow, ACDS, MEOS, ADRs, the blueprint, roadmap, capability map, tasks, and evidence;
- all 193 external fixed-file records retain explicit dispositions;
- Agent Reach, browsers, and proxies are not represented as currently active;
- Task 001, ADR-0003, and product-validation gates remain unchanged; and
- independent architecture and documentation review confirms no silent scope or authority conflict.

## Approval

The following authorized human direction was recorded in the project conversation on 2026-08-02: **ACCEPT DIRECTION**.

| Authority | Name | Decision | Date | Notes |
|---|---|---|---|---|
| Product Owner | Jarkius | ACCEPTED | 2026-08-02 | Accept product-to-platform relationship and phased expansion |
| Chief Architect | Jarkius | ACCEPTED | 2026-08-02 | Accept documentation responsibility and architecture ownership model |
| Engineering Lead | Jarkius | ACCEPTED | 2026-08-02 | Accept incremental delivery and repository introduction rule |
| Independent Reviewer | Pending assignment | PENDING | PENDING | Required before PR is ready to merge under current MEOS review controls |
| QA / Verification | Pending assignment | PENDING | PENDING | Required to verify links, states, and non-authorization claims |

ADR acceptance establishes direction. It does **not** promote Task 001, prove product validation, authorize a future phase, or mark any runtime capability implemented.
