# Motiflow Capability Expansion Roadmap

- **Status:** Review-ready delivery planning artifact
- **Owner:** Product, Chief Architect, and Delivery
- **Target architecture:** `../02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- **Capability state:** `../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- **Engineering execution:** MEOS

## Purpose

This roadmap translates Motiflow's complete target architecture into connected, independently useful build phases. It is the bridge between the current creative-direction MVP and the full research, content, publication, publishing, measurement, and enterprise platform.

The roadmap does not authorize implementation by itself. A phase becomes executable only through accepted decisions, ready tasks, required human authority, and MEOS verification.

## Jigsaw delivery model

Motiflow is not built by implementing a thin fragment of every future subsystem. It is built by completing one useful vertical slice at a time.

Each phase must produce:

1. A clear product outcome.
2. Versioned input and output contracts.
3. A working end-to-end path inside the phase boundary.
4. Negative and failure-path verification.
5. Explicit human approval where required.
6. Observable evidence.
7. Stable expansion seams for the next phase.
8. A list of intentionally deferred scope.

The next phase may extend an accepted seam but must not bypass or silently reinterpret it.

## Roadmap overview

```text
Phase 0  Reconcile authority and target architecture
   ↓
Phase 1  Prove decisive-slice contracts
   ↓
Phase 2  Execute creative direction through Gate 1
   ↓
Phase 3  Generate, review, and approve through Gate 2
   ↓
Phase 4  Add grounded external knowledge acquisition
   ↓
Phase 5  Assemble governed editorial and Publication Packages
   ↓
Phase 6  Publish through one authorized connector
   ↓
Phase 7  Measure outcomes and govern learning
   ↓
Phase 8  Expand into an enterprise platform
```

## Global activation gate

A phase may begin only when all applicable conditions pass:

```yaml
product_outcome_defined: true
accountable_owner_named: true
scope_and_non_goals_explicit: true
required_product_evidence_complete: true
contracts_accepted: true
architecture_decisions_accepted: true
security_and_data_policy_resolved: true
dependencies_available: true
tasks_ready: true
verification_defined: true
rollback_or_safe_stop_defined: true
independent_review_routed: true
protected_human_authority_recorded: true
```

A score cannot compensate for a failed mandatory gate. Review-ready documentation is not permission to implement.

# Phase 0 — Reconciliation and Authority Alignment

## Product outcome

Every contributor and AI agent can distinguish:

- current product scope;
- current verified implementation state;
- complete future-state architecture;
- the phase in which each capability belongs; and
- the exact authority required to activate it.

## Components and documents

- Target Platform Blueprint.
- Blueprint Reconciliation Matrix.
- Target Platform Capability Map.
- Capability Expansion Roadmap.
- ADR-0004 proposal.
- Context Index routing updates.
- Project Bootstrap and Document Index updates.

## Contracts

No runtime contract is introduced. The phase establishes document authority and capability-state semantics.

## Acceptance evidence

- All new files exist on one review branch.
- Repository-local links resolve.
- Terminology uses Motiflow, ACDS, MEOS, Creative Kernel, Workflow Orchestrator, Connector Gateway, and Model Gateway consistently.
- Current Task 001 state remains blocked and unchanged.
- Future capabilities are not described as implemented.
- Independent documentation and architecture review identifies no silent MVP scope expansion.

## Expansion seams

- Capability state model.
- Phase identifiers.
- Reconciliation dispositions.
- Target architecture references from tasks and ADRs.

## Deferred scope

- No schemas.
- No application code.
- No runtime directories.
- No Agent Reach installation.
- No provider integration.

## Exit trigger

ADR-0004 is accepted, revised, or explicitly rejected by authorized humans. The reconciliation package is linked from canonical navigation.

# Pre-Phase 1 — Existing Human Validation and Contract Decision Gate

This gate is already defined by the repository and is not replaced by the roadmap.

Required completion includes:

- intended-user validation sessions;
- dated evidence and baseline measures;
- product-owner `PROCEED`, `REVISE`, or `STOP` decision;
- C-01 through C-06 contract dispositions;
- ADR-0003 decision;
- accepted artifact-envelope and approval-reference direction;
- approved validator toolchain;
- independent reviewer and QA evidence; and
- Task 001 Definition of Ready.

If the decision is `REVISE`, update the product and contract path before activating Phase 1. If the decision is `STOP`, do not implement the decisive slice merely because the target blueprint exists.

# Phase 1 — Contract Foundation

## Product outcome

The decisive creative workflow is represented by one executable and independently verifiable artifact contract set before runtime code embeds assumptions.

## Components

- Ten canonical v1 JSON Schemas.
- Shared accepted definitions.
- One complete valid ten-artifact fixture chain.
- Focused invalid fixtures.
- Semantic lineage, stale-reference, gate, and provenance validator.
- One repository validation command.
- One CI workflow invoking that command.

## Canonical artifacts

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

## Contracts

- Canonical artifact envelope.
- Versioned `parent_artifact_refs`.
- Approval `artifact_refs` and gate cardinality.
- Authorship and producer metadata.
- Validation and confidence semantics.
- Invalidation and compatibility rules.

## Acceptance evidence

- Every declared valid fixture passes.
- Every declared invalid fixture fails for its expected reason and path.
- Direction and final gate bypass attempts fail.
- Stale downstream lineage fails.
- The same repository command runs locally and in CI.
- No workflow, provider, persistence, API, UI, publication, or speculative framework code enters the task.
- Independent review and the MEOS Quality Gate pass.

## Expansion seams

- Schema identifiers and version ranges.
- Artifact repository interface requirements.
- Kernel validation boundary.
- Workflow input/output package references.

## Deferred scope

Everything outside the Task 001 contract proof remains deferred.

## Exit trigger

Task 001 is accepted with complete evidence and no unresolved contract or architecture blocker.

# Phase 2 — Executable Creative Core

## Product outcome

A user can submit a brief, receive a grounded Creative Direction Package, and explicitly approve, reject, or request revision before generation.

## Vertical slice

```text
Intake Package
→ Normalized Brief
→ Knowledge Fusion Package
→ Creative Direction Package
→ Direction Approval Record
```

## Components

- Thin Creative Kernel.
- Thin Workflow Orchestrator.
- Artifact repository and immutable version handling.
- Workflow state and idempotency enforcement.
- Deterministic mock engines for normalization, fusion, and direction.
- Project and brief API boundary.
- Minimal Studio surfaces for brief and direction review.
- Direction approval service and record creation.
- Run events, logs, errors, and evidence.

## Contracts

- Kernel validation interface.
- Workflow definition and node execution contract.
- Specialist engine contract.
- Artifact repository interface.
- Direction approval authorization contract.
- Error and clarification contracts.

## Acceptance evidence

- A deterministic fixture runs end to end through `AWAITING_DIRECTION_APPROVAL`.
- An authorized human decision creates the correct record and resumes or revises the workflow.
- A stale approval is rejected.
- Revision invalidates only declared downstream artifacts.
- Cancellation and safe resume preserve the last valid state.
- UI or API evidence shows the rationale, confidence, sources, alternatives, and decision history without exposing hidden chain-of-thought.
- Architecture, contract, security, tests, documentation, and independent review pass.

## Expansion seams

- `SpecialistEngine` capability interface.
- Workflow-node registry.
- Approval service.
- Artifact repository.
- Connector Gateway port without a real provider dependency.

## Deferred scope

- Real model calls.
- Candidate generation.
- External acquisition.
- Editorial authoring.
- Publishing.

## Exit trigger

The creative-direction path through Gate 1 is product-usable, verified, and accepted.

# Phase 3 — Generation, Critic Review, and Final Approval

## Product outcome

An approved creative direction produces reviewable visual candidates through one provider, receives deterministic and critic evaluation, and ends with an explicit final human decision and closed provenance.

## Vertical slice

```text
Direction Approval Record
→ Generation Specification
→ Generated Candidate Set
→ Critic Evaluation Package
→ Final Approval Record
→ Provenance Record
```

## Components

- Thin Model Gateway.
- Deterministic mock adapter.
- One approved real provider adapter.
- Provider-neutral Generation Specification compiler.
- Candidate-set normalization and storage.
- Deterministic visual checks.
- One or two focused critics.
- Review fusion that preserves dimension findings.
- Final review workspace.
- Final approval service and provenance closure.

## Contracts

- Model request/result and capability contract.
- Generation connector contract.
- Provider usage and provenance record.
- Critic input/output contract.
- Final approval authorization and evidence contract.

## Acceptance evidence

- Mock runs are deterministic.
- One real provider path succeeds without provider SDK leakage into engines or workflows.
- Provider timeout, invalid output, safety failure, and retry exhaustion are tested.
- Candidate artifacts remain immutable.
- Critics do not mutate candidates.
- A failed mandatory critic dimension cannot be hidden by an aggregate score.
- Final approval references the current candidate set and critic package.
- Provenance reproduces the accepted inputs, versions, provider, model, configuration, and decisions.
- One representative brief completes the entire creative MVP without manual artifact copying.

## Expansion seams

- Model Gateway capability interface.
- Generation connector interface.
- Critic registration interface.
- Approved artifact chain available to publication specialization.

## Deferred scope

- Multi-provider routing.
- Provider fallback mesh.
- External research channels.
- Publication and social platforms.

## Exit trigger

The complete creative-direction MVP demonstrates useful product value and passes acceptance and operational gates.

# Phase 4 — External Knowledge Acquisition

## Product outcome

Motiflow can ground creative and later editorial work in normalized, traceable external sources without coupling workflows to individual channels or tools.

## Initial channels

- General web.
- YouTube transcripts and metadata.
- GitHub public repositories and related source material.
- RSS/Atom.

## Components

- Acquisition Request and Result contracts.
- Normalized Source Record.
- Source Bundle and citation contract.
- Source hash and retrieval evidence.
- Rights, classification, and retention metadata.
- Connector capability descriptors.
- Provider health contract.
- `motiflow doctor` diagnostics.
- Four read-only providers.
- Optional Agent Reach adapter behind the Connector Gateway.
- Prompt-injection and untrusted-source controls.

## Agent Reach sequence

1. Review dependency, license, install behavior, configuration, and credential handling.
2. Wrap installation planning and diagnostics; do not make it the runtime authority.
3. Normalize upstream outputs through Motiflow contracts.
4. Pin and test supported versions.
5. Compare direct provider integration with the wrapper.
6. Retain the ability to disable or replace it without changing workflow contracts.

## Contracts

- `KnowledgeAcquisitionProvider`.
- Channel descriptor.
- Provider health result.
- Credential reference without raw secret values.
- Source provenance and citation.
- Provider-selection policy.

## Acceptance evidence

- One fixture and one controlled real source succeed for each initial channel.
- Every result normalizes into the same source contract.
- Retrieval evidence includes provider, time, source URI, hash where applicable, and policy context.
- Prompt-injection fixtures cannot change workflow instructions or access secrets.
- Provider failure degrades explicitly.
- Automatic fallback does not escalate into authenticated or higher-risk access.
- Diagnostics produce machine-readable results and actionable remediation.
- Research credentials are isolated from publishing credentials.

## Expansion seams

- New read-only channel providers.
- Source records feed Intake Package or Knowledge Fusion Package through declared references.
- Editorial research can consume Source Bundles.

## Deferred scope

- Authenticated X, Reddit, Facebook, Instagram, or LinkedIn automation.
- Comments, engagement, posting, or account modification.
- Uncontrolled proxy or anti-detection systems.

## Exit trigger

The four-channel read-only acquisition capability is secure, reliable enough for its declared use, and improves the grounded creative workflow.

# Phase 5 — Editorial Intelligence and Publication Package

## Product outcome

Motiflow can turn approved research and creative artifacts into one factual, visually coherent, reviewable, and reproducible publication package.

## Vertical slice

```text
Source Bundle
→ Research Brief
→ Editorial Draft
→ Claim and Citation Map
→ Editorial/Factual/Brand Review
+ Approved Creative Artifact Chain
→ Publication Package
→ Package Approval
→ Markdown/HTML Export
```

## Components

- Research Brief contract.
- Claim extraction and source mapping.
- Editorial drafting engine.
- Editorial critic.
- Factual-review capability.
- Brand-review capability.
- Publication Package schema.
- Publication composer.
- Markdown exporter.
- Sanitized HTML exporter.
- Selected visual and crop references.
- Social variants as derived optional outputs.
- Package-level approval and version pinning.

## Contracts

- Research Brief.
- Content Draft.
- Claim and Citation Map.
- Editorial Review Package.
- Publication Package.
- Export manifest.
- Package approval and invalidation rules.

## Acceptance evidence

- Every material claim maps to a source or is explicitly marked unsupported/opinion.
- Editorial changes preserve source and human-edit provenance.
- Visual and editorial versions are pinned together.
- Replacing a material visual or factual section invalidates required approvals.
- HTML sanitation rejects executable or unsafe content.
- Markdown remains readable and portable.
- Exports are reproducible from approved artifact versions.
- The package can be reviewed without publication-system access.

## Expansion seams

- Channel adapters consume approved Publication Packages.
- Presentation, newsletter, and additional-language derivatives may reuse package contracts.

## Deferred scope

- Autonomous external posting.
- Broad SEO platform.
- Unreviewed mass content generation.

## Exit trigger

An intended user can approve and export a complete package with demonstrable factual, visual, and operational value.

# Phase 6 — Governed Publishing Connectors

## Product outcome

One approved Publication Package can be sent to one authorized destination with explicit account, payload, approval, idempotency, and published-state evidence.

## Initial strategy

Select one target based on real user need. Prefer:

1. Official API.
2. Approved normalized connector.
3. Authenticated browser provider with dedicated profile.
4. Bounded semantic browser fallback.
5. Stop as unsupported.

## Components

- Publishing Intent contract.
- Publishing Authorization Record.
- Normalized publishing connector interface.
- One platform adapter.
- Preview and dry-run modes.
- Target account verification.
- Payload and content-hash verification.
- Idempotency and duplicate protection.
- Published-state verifier.
- Publication evidence bundle.
- Credential and permission isolation.

## Contracts

- Publishing request/result.
- Target account identity.
- Publishing authorization.
- Published-state evidence.
- Retry, conflict, and rollback behavior.

## Acceptance evidence

- Dry-run produces a reviewable target payload without writing.
- A live test occurs only under explicit authorization.
- The connector confirms target account and package version before execution.
- Duplicate requests do not create duplicate posts.
- Partial or ambiguous success enters verification rather than blind retry.
- Evidence records destination identifiers, account, time, content hash, provider path, and observed result.
- Research credentials cannot authorize publishing.
- Security and platform-policy review pass.

## Expansion seams

- Additional platforms implement the same publishing contract.
- Browser providers remain replaceable.
- Publication metrics can link to the package and publishing evidence.

## Deferred scope

- Multi-platform blast publishing.
- Autonomous engagement.
- Automatic account creation or policy evasion.

## Exit trigger

One destination works safely and repeatedly, and users demonstrate demand for another connector.

# Phase 7 — Measurement and Governed Learning

## Product outcome

Motiflow improves workflow and creative decisions using measured evidence without silently rewriting approved policy or optimizing toward harmful engagement.

## Components

- Workflow and approval metrics.
- Revision and failure analytics.
- Critic calibration datasets.
- Source-quality and factual-accuracy signals.
- Provider cost, latency, and reliability ledger.
- Publication-performance ingestion.
- Learning synthesis engine.
- Approved memory and knowledge updates.
- Experiment and change-impact records.

## Contracts

- Measurement event.
- Outcome record.
- Evaluation dataset version.
- Learning proposal.
- Human-approved knowledge update.

## Acceptance evidence

- Metrics use stable denominators and definitions.
- Learning proposals cite evidence and uncertainty.
- No metric directly changes policy, approval requirements, or canonical contracts.
- Bias, gaming, privacy, and feedback-loop risks are reviewed.
- A human can accept, revise, or reject a learning proposal.
- Accepted updates are versioned and reversible.

## Expansion seams

- Provider routing can consume health/cost evidence.
- Product experiments can compare workflow variants.
- Brand and creative memory can grow from approved outcomes.

## Deferred scope

- Fully autonomous policy changes.
- Unbounded personalization.
- Engagement maximization without business and safety constraints.

## Exit trigger

Measurement improves a declared product outcome and the learning controls prove trustworthy.

# Phase 8 — Platform and Enterprise Expansion

## Product outcome

Proven internal capabilities become a configurable, secure, and extensible enterprise creative-intelligence platform.

## Potential components

- Multi-provider routing and fallback.
- Engine SDK.
- Connector SDK.
- Workflow authoring and version management.
- Enterprise tenancy and isolation.
- Advanced identity, RBAC, and delegated approval.
- Regional data and provider policies.
- Capability signing and compatibility checks.
- Operational dashboards.
- Governed third-party capability ecosystem.

## Activation discipline

Every platform feature must be justified by repeated internal use or customer evidence. Do not generalize one implementation into an SDK before the abstraction has at least two credible consumers.

## Acceptance evidence

- Stable contracts across multiple implementations.
- Tenant and security isolation tests.
- Migration and compatibility evidence.
- Provider and capability health under realistic load.
- Operational support and rollback procedures.
- Clear product packaging and administration outcomes.

## Deferred or rejected behavior

- Unrestricted marketplace installation.
- Silent external code execution.
- Provider or platform policy evasion.
- Autonomous approval of protected decisions.

# Cross-phase dependency rules

1. Schemas and contracts precede dependent runtime components.
2. Creative Kernel owns validation and protected canonical state.
3. Workflow Orchestrator owns scheduling and execution state.
4. Engines and critics never own provider credentials or workflow transitions.
5. Connectors never own product workflow semantics.
6. Publication builds on approved creative artifacts; it does not replace them.
7. Publishing consumes approved Publication Packages; it does not generate factual or creative truth.
8. Measurement observes and proposes; it does not silently change authority or policy.
9. Active workflow runs remain pinned to captured contract, workflow, engine, provider, policy, and knowledge versions.
10. Later phases add contracts or compatible versions rather than editing accepted history in place.

# Phase task template

Every implementation task linked to this roadmap should include:

```yaml
target_phase:
capability_ids:
product_outcome:
current_capability_state:
expected_capability_state:
upstream_artifacts:
downstream_expansion_seam:
in_scope:
out_of_scope:
affected_contracts:
required_adrs:
activation_gate_evidence:
acceptance_criteria:
verification_commands:
independent_review_roles:
rollback_or_safe_stop:
```

# Roadmap maintenance

Update this roadmap when:

- product validation changes the first wedge;
- an ADR changes component ownership or phase order;
- a capability is accepted, rejected, or deferred;
- evidence shows an expansion seam is insufficient;
- a phase completes or is stopped; or
- operational learning changes the recommended sequence.

Do not rewrite completed phase history. Record material changes through dated decisions, tasks, and ADRs.
