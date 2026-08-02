# Motiflow Capability Expansion Roadmap

- **Status:** Accepted expansion sequence; phases require separate activation
- **Owner:** Product Owner, Chief Architect, Delivery
- **Target architecture:** `../02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- **Capability state:** `../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- **Engineering execution:** MEOS
- **Decision:** ADR-0006
- **Responsibility:** Define the ordered journey, phase outcomes, dependencies, activation gates, exit evidence, and expansion seams
- **Does not own:** Product vision, stable architecture, current state, task authorization, exact test commands, or implementation evidence

## 1. Purpose

This roadmap connects the focused creative-direction product to the complete Motiflow platform as independently useful, contract-connected jigsaw pieces.

A phase is not permission to build. It becomes executable only when its product evidence, decisions, contracts, security/data controls, dependencies, ready tasks, reviewers, and verification requirements pass.

## 2. Delivery model

Motiflow is built by completing one useful vertical slice at a time—not by creating a thin fragment of every future subsystem.

Every activated phase must define:

```yaml
phase:
product_outcome:
target_users:
entry_gate:
inputs:
outputs:
components:
contracts:
owned_state:
human_authority:
security_and_data_controls:
verification:
rollback_or_safe_stop:
exit_evidence:
expansion_seams:
deferred_scope:
```

A later phase may extend an accepted seam but must not bypass or reinterpret it.

## 3. Roadmap overview

```text
Phase 0  Align authority, destination, state, and delivery ownership
   ↓
Pre-1    Validate the decisive product and settle blocking contracts
   ↓
Phase 1  Prove the ten-artifact contract foundation
   ↓
Phase 2  Execute creative direction through Gate 1
   ↓
Phase 3  Generate, evaluate, and approve through Gate 2
   ↓
Phase 4  Add grounded read-only knowledge acquisition
   ↓
Phase 5  Assemble governed editorial and Publication Packages
   ↓
Phase 6  Publish through one explicitly authorized connector
   ↓
Phase 7  Measure outcomes and govern learning
   ↓
Phase 8  Expand proven seams into an enterprise platform
```

## 4. Global activation gate

A phase may begin only when all applicable conditions pass:

```yaml
product_outcome_defined: true
target_user_and_need_supported: true
accountable_owner_named: true
scope_and_non_goals_explicit: true
previous_phase_evidence_accepted: true
required_product_evidence_complete: true
contracts_accepted: true
architecture_decisions_accepted: true
security_legal_and_data_policy_resolved: true
dependencies_and_environment_available: true
tasks_ready: true
verification_and_negative_paths_defined: true
rollback_or_safe_stop_defined: true
independent_reviewer_and_qa_assigned: true
protected_human_authority_recorded: true
```

A score cannot compensate for a failed mandatory gate. Accepted direction does not mean an implementation phase is active.

# Phase 0 — Authority and Destination Alignment

## Product outcome

Every contributor and AI agent can distinguish:

- why Motiflow exists;
- what ACDS is;
- what the complete platform may become;
- what exists today;
- how expansion is sequenced;
- how work is authorized and verified;
- which external technologies are deferred or prohibited.

## Deliverables

- Refactored Project Charter.
- Refactored Master Context.
- Destination-only Target Platform Blueprint.
- Active Capability Map.
- This Expansion Roadmap.
- Document Responsibility Model.
- Architecture Change Gate.
- Blueprint Reconciliation Matrix and review.
- Complete 193-file manifest disposition.
- Responsibility Migration Report.
- Accepted ADR-0006.
- Updated `START_HERE.md`, `CONTEXT_INDEX.yaml`, Bootstrap, and Document Index.

## Exit evidence

- One canonical owner exists for each major information class.
- The blueprint contains no current-state, task, CI, or detailed phase ownership.
- The roadmap contains the complete expansion sequence.
- The Capability Map records all state claims.
- MEOS remains the only engineering governance system.
- Agent Reach, browser providers, and proxies are not represented as active.
- Task 001 remains blocked and readiness remains 46/100.
- Independent architecture/documentation review passes.
- Independent QA/link/state verification passes.

## Expansion seams

- Document responsibility model.
- Capability-state vocabulary.
- Phase identifiers and gates.
- Architecture Change Gate.
- Context-routing rules.

## Status

Direction accepted on 2026-08-02 through ADR-0006. PR #7 merged 2026-08-02 with an explicitly accepted residual risk; independent review and QA evidence remain outstanding.

# Pre-Phase 1 — Product Validation and Contract Decision Gate

## Product outcome

The team has evidence that the decisive creative workflow solves a real user problem and has one accepted contract vocabulary before implementation embeds assumptions.

## Required work

- Run 5–10 representative briefs through the prepared manual protocol.
- Conduct sessions with the intended user(s) under the current recorded scope
  (solo per the 2026-07-26 revision in `docs/01-product/MVP_VALIDATION_PLAN.md`;
  2–3-user or design-partner coverage is deferred to the post-build pilot).
- Record baseline and outcome measures.
- Record Product Owner `PROCEED`, `REVISE`, or `STOP`.
- Resolve C-01 through C-06.
- Accept, revise, or reject ADR-0003.
- Accept artifact envelope, parent reference, approval reference, authorship, confidence, provenance, and validation semantics.
- Confirm validator toolchain and independent review/QA expectations.
- Run Definition of Ready for Task 001.

## Exit evidence

- Intended-user evidence exists.
- Product decision is explicit.
- Contract conflicts are closed.
- ADR-0003 is decided.
- Task 001 is `READY` with no implicit exception.

A `REVISE` decision changes product/contracts before implementation. A `STOP` decision stops Phase 1 regardless of the target blueprint.

# Phase 1 — Contract Foundation

## Product outcome

The decisive creative workflow has one executable and independently verifiable contract set before runtime code exists.

## Vertical slice

```text
Ten canonical artifact schemas
+ valid/invalid fixture chains
+ structural and semantic validator
+ one repository command
+ one CI enforcement path
```

## Components

- Shared artifact envelope definitions.
- Ten canonical v1 JSON Schemas.
- Complete valid fixture chain.
- Focused invalid fixtures.
- Semantic lineage and stale-reference checks.
- Approval gate and actor checks.
- Provenance and validation checks.
- One local/CI validation entrypoint.

## Contracts

- Canonical artifact envelope.
- Versioned parent artifact references.
- Approval artifact references and gate cardinality.
- Human/machine authorship.
- Producer metadata.
- Confidence and validation semantics.
- Invalidation and compatibility.

## Exit evidence

- Valid fixtures pass.
- Invalid fixtures fail for expected path/reason.
- Gate bypass and stale references fail.
- Local and CI invoke the same validator.
- No workflow, persistence, API, UI, provider, or publication implementation enters scope.
- MEOS independent review and Quality Gate pass.

## Expansion seams

- Canonical Artifact Envelope.
- Artifact Repository interface requirements.
- Kernel validation boundary.
- Workflow artifact-reference contracts.

# Phase 2 — Executable Creative Core

## Product outcome

A user can submit a brief, receive an explainable Creative Direction Package, and approve, reject, or request revision before generation.

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
- Workflow state, idempotency, cancellation, and safe resume.
- Deterministic mock normalization, fusion, and direction engines.
- Minimal project/brief API.
- Minimal brief and direction-review Studio surfaces.
- Direction approval service.
- Run events, logs, errors, and evidence.

## Contracts

- Kernel validation interface.
- Workflow definition and node execution.
- Specialist Engine contract.
- Artifact Repository contract.
- Direction approval authorization.
- Clarification and error contracts.

## Exit evidence

- Deterministic fixture reaches `AWAITING_DIRECTION_APPROVAL`.
- Valid human decisions resume/revise correctly.
- Stale approval is rejected.
- Revision invalidates only declared downstream artifacts.
- Cancellation and resume preserve last valid state.
- UI/API shows rationale, evidence, alternatives, confidence, and decision history without hidden chain-of-thought.
- Architecture, contract, security, test, documentation, reviewer, and QA gates pass.

## Expansion seams

- Specialist Engine interface.
- Workflow-node registration.
- Approval service.
- Artifact Repository.
- Provider-neutral Connector Gateway port.

## Deferred

Real model calls, candidate generation, external acquisition, editorial authoring, and publishing.

# Phase 3 — Generation, Evaluation, and Final Approval

## Product outcome

An approved direction produces reviewable candidates through one provider, receives deterministic and critic evaluation, and ends with explicit final human approval and complete provenance.

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
- Generation Specification compiler.
- Candidate normalization and storage.
- Deterministic visual checks.
- One or two focused critics.
- Dimension-preserving review fusion.
- Final review workspace and approval service.
- Provenance closure.

## Exit evidence

- Mock runs are deterministic.
- One real provider works without SDK leakage into engines/workflows.
- Timeout, invalid output, safety failure, and retry exhaustion are tested.
- Candidate artifacts are immutable.
- Critics do not mutate candidates.
- Failed mandatory findings cannot be hidden by aggregate score.
- Final approval references current candidate and critic versions.
- Provenance captures inputs, models/providers, configuration, decisions, and versions.
- One representative brief completes without manual artifact copying.

## Expansion seams

- Model Gateway contract.
- Generation Connector contract.
- Critic contract/registration.
- Approved artifact chain for Publication Package.

## Exit trigger

The first complete creative-direction MVP demonstrates intended-user value and passes product, quality, security, and operational gates.

# Phase 4 — External Knowledge Acquisition

## Product outcome

Motiflow grounds creative and later editorial work in normalized, traceable external sources without coupling workflows to one channel or tool.

## Initial provider classes

- Public web.
- YouTube transcripts/metadata.
- Public GitHub repositories/source material.
- RSS/Atom.

## Components

- Acquisition Request/Result.
- Normalized Source Record.
- Source Bundle and citations.
- Retrieval evidence and hashes.
- Rights, classification, and retention metadata.
- Provider capability descriptors.
- Provider health contract and `motiflow doctor` diagnostics.
- Read-only providers.
- Prompt-injection/untrusted-source controls.
- Optional Agent Reach adapter behind Connector Gateway.

## Agent Reach activation gate

- Dependency/license/install behavior reviewed.
- Supply-chain and credential handling reviewed.
- Motiflow-owned acquisition contracts accepted.
- Wrapper proof of concept compares direct and Agent Reach paths.
- Supported version pinned and tested.
- Disable/replace path proven.
- Ready task and independent review exist.

## Exit evidence

- Controlled fixture and real source succeed for each activated provider.
- Results normalize into one contract.
- Evidence records source, provider, time, URI, hash where applicable, and policy context.
- Prompt-injection fixtures cannot change workflow instructions or expose secrets.
- Provider failure degrades explicitly.
- Fallback does not escalate into authenticated/proxy access.
- Diagnostics are machine-readable and actionable.
- Research credentials remain separate from publishing credentials.

## Deferred

Authenticated social channels, browser-session acquisition, proxy use, comments, engagement, posting, and account modification.

# Phase 5 — Editorial Intelligence and Publication Package

## Product outcome

Approved research, editorial content, and creative artifacts become one factual, visually coherent, reviewable, and reproducible Publication Package.

## Vertical slice

```text
Source Bundle
→ Research Brief
→ Editorial Draft
→ Claim/Citation Map
→ Editorial + Factual + Brand Review
+ Approved Creative Artifact Chain
→ Publication Package
→ Package Approval
→ Markdown/HTML Export
```

## Components

- Research Brief.
- Claim extraction/source mapping.
- Editorial drafting engine.
- Editorial, factual, and brand critics.
- Publication Package schema/composer.
- Markdown and sanitized HTML exporters.
- Selected visual/crop references.
- Derived channel variants.
- Package approval and version pinning.

## Exit evidence

- Material claims map to sources or explicit unsupported/opinion status.
- Editorial and human edits preserve provenance.
- Visual/content versions are pinned.
- Material replacements invalidate required approvals.
- HTML sanitation rejects unsafe content.
- Markdown is portable/readable.
- Exports reproduce from approved versions.
- Package review does not require publication-system access.

## Expansion seams

- Publishing connectors consume only approved packages.
- Presentation, newsletter, language, and channel derivatives reuse package contracts.

# Phase 6 — Governed Publishing Connectors

## Product outcome

One approved Publication Package is sent to one authorized destination with account, payload, approval, idempotency, and published-state evidence.

## Preferred provider order

1. Official API.
2. Approved normalized connector.
3. Authenticated browser provider with dedicated profile.
4. Bounded semantic browser fallback.
5. Stop as unsupported.

## Components

- Publishing Intent.
- Publishing Authorization Record.
- Publishing connector interface.
- One target adapter.
- Preview and dry-run modes.
- Target account and package-version verification.
- Idempotency/duplicate protection.
- Published-state verifier and evidence bundle.
- Credential and permission isolation.

## Browser activation gate

- Demonstrated need not satisfied by official/approved API.
- Legal/platform policy review.
- Dedicated profile and least-privilege credentials.
- Selector/action policy and bounded scope.
- Ambiguous-success verification.
- Disable/replace plan.
- Ready task, security review, reviewer, and QA.

## Proxy rule

Proxy infrastructure is not a roadmap requirement. Any future legitimate use requires a new accepted high-risk decision and cannot be introduced as silent provider fallback.

## Exit evidence

- Dry-run creates a reviewable payload without writing.
- Live test occurs only with explicit authorization.
- Target account and approved package version are confirmed.
- Duplicate requests do not duplicate publications.
- Ambiguous success enters verification rather than blind retry.
- Evidence records destination ID, account, time, content hash, provider path, and result.
- Research credentials cannot authorize publishing.

# Phase 7 — Measurement and Governed Learning

## Product outcome

Motiflow improves decisions from measured evidence without silently rewriting approved policy, contracts, or human authority.

## Components

- Workflow/approval metrics.
- Revision/failure analytics.
- Critic calibration datasets.
- Source-quality/factual-accuracy signals.
- Provider cost, latency, reliability evidence.
- Publication performance ingestion.
- Learning synthesis.
- Human-approved memory/knowledge updates.
- Experiment and change-impact records.

## Exit evidence

- Metrics have stable definitions and denominators.
- Learning proposals cite evidence and uncertainty.
- Metrics cannot directly change policy, approval requirements, or contracts.
- Bias, gaming, privacy, and feedback-loop risks are reviewed.
- Knowledge updates are versioned, attributable, reversible, and human-approved.

## Rejected early behavior

Autonomous engagement optimization, unreviewed policy adaptation, and metric-driven publication without human authority.

# Phase 8 — Enterprise and Ecosystem Expansion

## Product outcome

Proven internal seams support broader enterprise deployment and governed extensibility.

## Candidate capabilities

- Multiple model/generation providers.
- Evidence-based routing and fallback.
- Engine SDK.
- Connector SDK.
- Multi-tenant/project isolation.
- Enterprise identity and delegated approvals.
- Regional/provider data controls.
- Operational resilience and scale.
- Governed capability marketplace after trust/demand are proven.

## Activation evidence

- Repeated user demand.
- Stable internal interfaces with multiple implementations.
- Operational load justifies added complexity.
- Tenant/security/authority model accepted.
- Compatibility, signing, trust, deprecation, and support policies exist.
- Enterprise capabilities do not weaken creative gates or provenance.

# Roadmap governance

## Update this roadmap when

- a product decision changes the phase outcome;
- an ADR changes sequencing or ownership;
- a phase entry or exit condition changes;
- evidence activates, revises, pauses, or stops a phase;
- a new expansion seam is accepted;
- a deferred capability is promoted or rejected.

## Do not update this roadmap merely because

- a provider or library is interesting;
- a prototype exists;
- a planning score increased;
- documentation was generated;
- an LLM suggested a feature;
- a future capability appears in the blueprint.

## Related authorities

- Product purpose: `../../PROJECT_CHARTER.md`
- Stable architecture: `../../MASTER_CONTEXT.md`
- Future destination: `../02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- Current state: `../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- Responsibility model: `../00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md`
- Change gate: `../00-foundation/ARCHITECTURE_CHANGE_GATE.md`
- Accepted direction: `../adr/ADR-0006-target-blueprint-and-phased-expansion.md`
- Current delivery state: `../../MEOS/20_PROJECT_BOOTSTRAP.md`
- Task execution and evidence: MEOS and task-specific artifacts
