# ADR-0004: Target Blueprint Authority and Phased Capability Expansion

- **Status:** Proposed
- **Date:** 2026-08-02
- **Decision owners:** Jarkius (Product owner, Chief Architect, Engineering lead)
- **Related work:** Blueprint reconciliation and target-platform planning
- **Supersedes:** None
- **Superseded by:** None

## Context

Motiflow now has two valuable but differently shaped bodies of planning:

1. The repository defines Motiflow as an enterprise creative-intelligence product, ACDS as its product architecture, MEOS as its engineering operating system, a ten-artifact decisive slice, two protected human approval gates, and a deliberately narrow first implementation path.
2. A broader blueprint defines a future platform that includes external knowledge acquisition, Agent Reach integration, channel and provider diagnostics, editorial workflows, Publication Packages, browser and publishing connectors, measurement, learning, and enterprise capability expansion.

Both are useful. Treating either one as the only plan creates material risk:

- Treating the broad blueprint as an immediate repository-generation instruction encourages premature complexity, speculative directories, and implementation before product evidence and contracts are ready.
- Treating the current repository boundary as the complete product vision risks losing the intended expansion path into research, editorial, publication, publishing, measurement, and enterprise functionality.
- Maintaining the blueprint outside the repository creates a competing source of truth and makes future AI sessions dependent on chat history or manually supplied files.

The project needs one explicit relationship between product authority, target architecture, phased delivery, and verified current state.

## Decision drivers

- Preserve the complete Motiflow platform vision.
- Keep the creative-direction decisive slice as the first validated product core.
- Prevent proposed capabilities from being reported as implemented.
- Avoid creating the entire final repository structure before tasks require it.
- Use stable contracts and expansion seams so later capabilities connect without rewriting the validated core.
- Keep repository artifacts authoritative over chat memory and loose external documents.
- Preserve MEOS readiness, independent verification, quality gates, and human authority.
- Make the system understandable to strong and constrained AI agents through explicit routing and state.

## Considered options

### Option A — Replace the repository architecture with the broad blueprint

**Advantages**

- One exhaustive document contains the complete target system.
- Future capabilities and file structures are visible immediately.
- Bootstrap agents receive highly explicit generation instructions.

**Disadvantages**

- Conflicts with the repository's established Motiflow/ACDS/MEOS authority model.
- Encourages implementation breadth before validating the first product outcome.
- Duplicates MEOS governance and canonical architecture documents.
- Makes a large static manifest look like required current state.
- Increases context size and drift risk.

### Option B — Discard the broad blueprint and use only the current repository

**Advantages**

- Maintains a narrow, coherent MVP.
- Avoids speculative architecture and directories.
- Keeps current authority simple.

**Disadvantages**

- Loses a valuable, detailed expansion architecture.
- Leaves acquisition, Agent Reach, editorial, publication, browser, publishing, and measurement direction under-specified.
- Makes later expansion more likely to be reinvented inconsistently.

### Option C — Keep the blueprint external and reference it informally

**Advantages**

- Avoids changing repository authority.
- Retains the complete blueprint for occasional consultation.

**Disadvantages**

- Creates a competing source outside version control.
- Future work depends on chat history, links, or manually transferred files.
- The external copy can drift from accepted repository decisions.
- Agents cannot reliably determine which version is current.

### Option D — Integrate a target-state blueprint into the repository and activate it through phased capability governance

**Advantages**

- Preserves the complete platform vision inside the source of truth.
- Keeps Product Charter, Master Context, accepted ADRs, MEOS, tasks, and evidence authoritative for current work.
- Separates target state from verified current state.
- Turns the broad architecture into connected jigsaw phases.
- Allows directories and components to appear only when activated.
- Retains explicit expansion seams for future development.

**Disadvantages**

- Adds governance documents that must be maintained.
- Requires disciplined updates across capability state, roadmap, context routing, and decisions.
- Some concepts from the original broad blueprint must be adapted or rejected rather than copied directly.

## Decision

Motiflow should adopt **Option D**.

### 1. Repository authority remains layered

The repository retains this authority model:

- `PROJECT_CHARTER.md` controls enduring product intent.
- `MASTER_CONTEXT.md` controls stable ACDS architecture.
- Accepted ADRs control architecture-significant decisions within scope.
- Accepted product requirements and canonical contracts control behavior.
- MEOS controls engineering governance and delivery.
- Ready tasks control bounded implementation.
- Tests, evidence, and operational records prove current behavior.

### 2. The Target Platform Blueprint defines future-state capability direction

`docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md` becomes the repository-native target-state architecture for the complete platform.

It is authoritative for long-term capability direction only where it does not conflict with a higher-authority accepted source. It is not evidence that capabilities are implemented, validated, accepted, or ready.

### 3. Capability activation is phased

The platform expands through the phases defined in `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`:

0. Reconciliation and authority alignment.
1. Contract foundation.
2. Executable creative core through direction approval.
3. Generation, critics, final approval, and provenance.
4. External knowledge acquisition and Agent Reach adapter.
5. Editorial intelligence and Publication Package.
6. Governed publishing connectors.
7. Measurement and governed learning.
8. Platform and enterprise expansion.

Each phase must deliver one useful vertical slice, accepted contracts, failure behavior, verification evidence, and stable expansion seams.

### 4. Capability state is explicit

`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md` records whether a capability is implemented, validated, contracted, review-ready, planned, deferred, experimental, or rejected.

A proposed document, mockup, score, branch, or generated code without accepted evidence must not promote the capability state.

### 5. Reconciliation decisions are explicit

`docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md` maps broad blueprint concepts to existing repository authority using `adopt`, `adapt`, `defer`, or `reject`.

Notable decisions include:

- Adopt the repository's Motiflow/ACDS/MEOS identity and authority model.
- Adopt the ten-artifact decisive slice and two human gates.
- Adapt acquisition, Agent Reach, browser, editorial, publication, publishing, and measurement concepts into existing ACDS boundaries.
- Defer later capabilities to their activation phases.
- Reject immediate generation of a complete speculative file tree.
- Reject Agent Reach as a core runtime authority; keep it replaceable behind the Connector Gateway.

### 6. Files and directories are introduced incrementally

The target repository structure defines ownership boundaries, not a bootstrap command to create every future path.

A new directory or implementation artifact is introduced only when an accepted contract, ready task, executable implementation, governed fixture, or authoritative document requires it.

### 7. The existing MVP gate remains unchanged

This decision does not authorize Task 001 or any runtime implementation.

The existing intended-user validation, product-owner decision, C-01 through C-06 acceptance, ADR-0003 decision, toolchain approval, Definition of Ready, independent review, and QA requirements remain mandatory.

### 8. Future capabilities connect through stable seams

Later phases must extend versioned contracts such as:

- canonical artifact envelope;
- workflow definition;
- engine and critic capability contracts;
- Connector and Model Gateway contracts;
- knowledge acquisition and source provenance;
- approval and evidence contracts;
- Publication Package;
- publishing connector; and
- measurement event.

They may not bypass the Creative Kernel, Workflow Orchestrator, Connector Gateway, protected approval gates, or accepted artifact lineage.

## Consequences

### Positive

- One repository clone contains both the current product core and complete target direction.
- The team can build a narrow MVP without losing long-term architecture.
- Future agents can distinguish planned, contracted, implemented, and validated capabilities.
- Agent Reach and browser automation receive a clear integration boundary and phase.
- Product expansion can proceed one complete jigsaw piece at a time.
- Existing MEOS governance is reused rather than duplicated.
- The repository avoids speculative mass generation while retaining ownership boundaries.

### Negative

- The new blueprint, map, roadmap, matrix, Context Index, and Project Bootstrap must remain synchronized.
- Phase changes may require additional ADRs and product validation.
- Some original blueprint details will remain deferred for a long period.
- Reviewers must resist treating the target blueprint as current implementation scope.

## Risks and mitigations

### Risk: target-state documentation is mistaken for current behavior

**Mitigation:** capability-state vocabulary, Context Index routing, Project Bootstrap current state, task evidence, and explicit non-authorization language.

### Risk: the roadmap becomes a fixed waterfall

**Mitigation:** phases define dependency and activation gates, not calendar commitments. Product evidence may revise, stop, reorder, or narrow later phases through explicit decisions.

### Risk: the creative MVP becomes too narrow to support future expansion

**Mitigation:** every phase must expose the declared versioned expansion seams. Architecture review checks that current implementation does not hard-code one provider or close future connector boundaries.

### Risk: the broad blueprint recreates duplicate governance

**Mitigation:** MEOS remains the sole engineering-delivery authority. The target blueprint references MEOS rather than redefining task readiness, quality gates, or release rules.

### Risk: too many documents create navigation burden

**Mitigation:** `START_HERE.md`, `CONTEXT_INDEX.yaml`, and the Document Index route the minimum complete context. Tasks reference only applicable phase and capability documents.

### Risk: Agent Reach or another upstream tool becomes foundational

**Mitigation:** all external tools remain replaceable connectors behind Motiflow-owned contracts, policy, normalization, provenance, and state.

## Migration and rollback

### Migration

1. Add the Target Platform Blueprint.
2. Add the Blueprint Reconciliation Matrix.
3. Add the Target Platform Capability Map.
4. Add the Capability Expansion Roadmap.
5. Add this ADR in `Proposed` state.
6. Update `CONTEXT_INDEX.yaml`, `MEOS/20_PROJECT_BOOTSTRAP.md`, and the Document Index to route the new artifacts.
7. Perform link, terminology, current-state, and scope-drift review.
8. Record human acceptance, revision, or rejection.

### Compatibility

This is a documentation and governance reconciliation before runtime implementation. It does not change accepted runtime behavior, schema versions, public APIs, or production data.

### Rollback before acceptance

Revert the reconciliation branch or remove the proposed documents and routing updates as one change set. The current repository authority and blocked MVP path remain intact.

### Rollback after acceptance

Create a superseding ADR. Update the target blueprint, capability map, roadmap, reconciliation matrix, context routing, and affected tasks together. Do not leave a partially superseded authority model.

## Verification

This decision is implemented correctly only when:

- all reconciliation documents exist and link to one another;
- the Document Index and Context Index route them correctly;
- the Project Bootstrap distinguishes current MVP work from future target capabilities;
- no document marks ADR-0004 accepted without explicit human authority;
- Task 001 remains blocked until its existing prerequisites pass;
- no future capability is marked implemented without evidence;
- repository terminology remains consistent;
- no speculative runtime directories are created by this documentation change; and
- independent review finds no silent change to the first MVP scope.

## Approval

This ADR remains `Proposed` until explicit human approval is recorded. AI agents may draft, critique, and revise it, but may not mark it `Accepted`.

| Authority | Name | Decision | Date | Notes |
|---|---|---|---|---|
| Product owner | Jarkius | PENDING | PENDING | Confirm product and expansion relationship |
| Chief Architect | Jarkius | PENDING | PENDING | Confirm authority and dependency model |
| Engineering lead | Jarkius | PENDING | PENDING | Confirm phased delivery and repository introduction rule |
| Independent reviewer | PENDING | PENDING | PENDING | Review scope, contradictions, and maintainability |
| QA / verification | PENDING | PENDING | PENDING | Verify links, states, and non-authorization claims |

The named owner roles assign accountability only. They do not constitute acceptance or independent approval.
