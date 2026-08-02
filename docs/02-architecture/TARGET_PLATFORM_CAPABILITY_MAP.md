# Motiflow Target Platform Capability Map

- **Status:** Review-ready architecture and portfolio control
- **Owner:** Chief Architect, Product, and Delivery
- **Target architecture:** `TARGET_PLATFORM_BLUEPRINT.md`
- **Delivery sequencing:** `../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- **Current-state authority:** `CONTEXT_INDEX.yaml`, `MEOS/20_PROJECT_BOOTSTRAP.md`, ready tasks, implementation, tests, and evidence

## Purpose

This map connects Motiflow's complete target architecture to the repository's verified current state. It prevents proposed or documented capabilities from being mistaken for implemented product behavior.

The map is a planning and architecture control. Implementation state must be supported by observable repository evidence.

## State vocabulary

| State | Meaning |
|---|---|
| **Implemented** | Runtime behavior exists with required verification evidence. |
| **Validated** | Product or operational evidence demonstrates the intended outcome. |
| **Contracted** | Accepted machine-readable or normative contracts exist; runtime may not. |
| **Review-ready** | A coherent proposal exists but required human acceptance is pending. |
| **Planned** | Approved or proposed for a named future phase; not activated. |
| **Deferred** | Intentionally postponed until an explicit trigger occurs. |
| **Experimental** | Isolated research or POC; no production claim. |
| **Rejected** | Considered and intentionally excluded from the target or current path. |

`Documented` is not an implementation state. A numerical planning score is not implementation evidence.

## Current portfolio summary

At the time of this map:

- The repository has a strong documentation and governance baseline.
- Runtime and application implementation have not started on `main`.
- Product validation and human decisions for the decisive slice remain pending.
- ADR-0003 and the decisive-slice contract acceptance remain pending.
- Task 001 remains blocked.
- The target blueprint and this map do not change that delivery state.

## Capability map

| Domain | Capability | Current state | Target phase | Current evidence or authority | Activation trigger |
|---|---|---|---:|---|---|
| Governance | Product Charter and product identity | Review-ready foundation | 0 | `PROJECT_CHARTER.md` | Human acceptance where still pending |
| Governance | Stable ACDS architecture context | Review-ready foundation | 0 | `MASTER_CONTEXT.md` | Accepted architecture decisions |
| Governance | MEOS engineering governance | Implemented as repository governance | 0 | `MEOS/` authoritative documents | Continued use and enforcement |
| Governance | Canonical onboarding and context routing | Implemented as documentation routing | 0 | `START_HERE.md`, `CONTEXT_INDEX.yaml` | Automated validation may follow later |
| Governance | Independent review and QA separation | Contracted in MEOS | 0 | roles, Review Standard, Quality Gate | Named independent evidence per task |
| Governance | Target-state platform blueprint | Review-ready | 0 | `TARGET_PLATFORM_BLUEPRINT.md` | ADR-0004 decision |
| Governance | Blueprint reconciliation | Review-ready | 0 | reconciliation matrix | ADR-0004 decision and linked routing |
| Product validation | Manual decisive-slice validation protocol | Review-ready | Pre-1 | MVP Validation Plan and instruments | Execute with intended users |
| Product validation | Intended-user evidence | Planned | Pre-1 | Dated validation report placeholder | Complete sessions and evidence |
| Product validation | Product-owner PROCEED/REVISE/STOP decision | Planned | Pre-1 | Named authority, decision pending | Evidence-backed decision |
| Contracts | Ten-artifact decisive-slice vocabulary | Review-ready | 1 | Charter, Master Context, contract docs | Human contract acceptance |
| Contracts | Canonical artifact envelope | Review-ready | 1 | ADR-0003 proposal | ADR-0003 accepted |
| Contracts | Versioned parent references | Review-ready | 1 | ADR-0003 and Task 001 | Contract acceptance and schema proof |
| Contracts | Direction Approval Record contract | Review-ready | 1 | workflow and runtime contracts | Accepted schemas and fixtures |
| Contracts | Final Approval Record contract | Review-ready | 1 | workflow and runtime contracts | Accepted schemas and fixtures |
| Contracts | Provenance Record contract | Review-ready | 1 | decisive-slice contracts | Accepted schemas and fixtures |
| Contracts | Deterministic validation command | Planned | 1 | Task 001 names command | Task 001 READY and implemented |
| Contracts | CI contract enforcement | Planned | 1 | Task 001 | Task 001 READY and implemented |
| Core runtime | Creative Kernel interface | Review-ready target | 2 | Master Context and architecture docs | Phase 1 accepted contract proof |
| Core runtime | Workflow Orchestrator interface | Review-ready target | 2 | Master Context and runtime contracts | Phase 1 accepted contract proof |
| Core runtime | Artifact repository and immutable versions | Planned | 2 | architecture contracts | Storage ADR/task and contract proof |
| Core runtime | Workflow state transitions | Review-ready contract | 2 | Workflow State Machine | Accepted transition contracts |
| Core runtime | Direction approval pause/resume | Review-ready contract | 2 | Workflow State Machine | Executable workflow task READY |
| Core runtime | Deterministic mock engines | Planned | 2 | delivery and AI execution plans | Executable creative-core task READY |
| Core runtime | Run observability and evidence | Review-ready target | 2 | runtime contracts and MEOS | Runtime task with evidence contract |
| Studio | Project and brief workspace | Planned | 2 | PRD and UX direction | Creative-core API/state contract |
| Studio | Direction review workspace | Planned | 2 | PRD and approval model | Direction workflow executable |
| AI execution | Thin Model Gateway | Review-ready target | 3 | AI Execution Layer, ADR-0002 | Creative-core workflow proven |
| AI execution | Deterministic mock model adapter | Planned | 3 | AI execution implementation plan | Model Gateway task READY |
| AI execution | One real model/provider adapter | Planned | 3 | AI execution implementation plan | Mock and contract tests pass |
| Generation | Provider-neutral Generation Specification | Review-ready contract | 3 | canonical artifact chain | Phase 1 schemas accepted |
| Generation | One rendering-provider connector | Planned | 3 | Connector Gateway architecture | Provider and security task READY |
| Generation | Generated Candidate Set | Review-ready contract | 3 | canonical artifact chain | Generation workflow implemented |
| Evaluation | Deterministic candidate checks | Planned | 3 | workflow and evaluation docs | Candidate fixtures and rules accepted |
| Evaluation | Focused critic implementations | Planned | 3 | critic contracts and PRD | Evaluation criteria and fixtures accepted |
| Evaluation | Critic Evaluation Package | Review-ready contract | 3 | canonical artifact chain | Contract proof and critic task |
| Evaluation | Final approval workspace | Planned | 3 | PRD | Candidate and critic workflow works |
| Evaluation | End-to-end provenance closure | Planned | 3 | Provenance Record contract | Full creative MVP evidence |
| Acquisition | Acquisition Request contract | Planned | 4 | target blueprint | Phase 3 MVP accepted; acquisition ADR/task |
| Acquisition | Normalized Source Record | Planned | 4 | target blueprint and provenance direction | Source schema and rights policy accepted |
| Acquisition | Source Bundle and citation mapping | Planned | 4 | target blueprint | Acquisition fixtures and provenance tests |
| Acquisition | Web reader provider | Deferred | 4 | target blueprint | Read-only acquisition phase activated |
| Acquisition | YouTube transcript provider | Deferred | 4 | target blueprint | Read-only acquisition phase activated |
| Acquisition | GitHub source provider | Deferred | 4 | target blueprint | Read-only acquisition phase activated |
| Acquisition | RSS provider | Deferred | 4 | target blueprint | Read-only acquisition phase activated |
| Acquisition | Channel registry | Deferred | 4 | target blueprint | At least two activated channel providers |
| Acquisition | Provider health contract | Deferred | 4 | target blueprint | Acquisition providers selected |
| Acquisition | `motiflow doctor` diagnostics | Deferred | 4 | target blueprint | Machine-readable health contract |
| Acquisition | Agent Reach adapter | Deferred | 4 | target blueprint and reconciliation | Supply-chain/security review; wrapper POC |
| Acquisition | Authenticated X provider | Deferred | 4+ | target blueprint | Separate platform/security/legal approval |
| Acquisition | Authenticated Reddit provider | Deferred | 4+ | target blueprint | Separate platform/security/legal approval |
| Acquisition | LinkedIn research provider | Deferred | 4+ | target blueprint | Public/read path and policy review |
| Acquisition | Browser-session source provider | Deferred | 4+ | browser target architecture | Dedicated profile and credential controls |
| Editorial | Research Brief | Deferred | 5 | target blueprint | Acquisition and editorial validation |
| Editorial | Claim extraction and evidence map | Deferred | 5 | target blueprint | Source and claim contracts accepted |
| Editorial | Article/editorial drafting engine | Deferred | 5 | target blueprint | Product validation and editorial task |
| Editorial | Factual review | Deferred | 5 | Publication Package direction | Evidence and review criteria accepted |
| Editorial | Brand review | Deferred | 5 | brand and review architecture | Brand policy and fixtures accepted |
| Publication | Publication Package | Review-ready post-MVP proposal | 5 | `PUBLICATION_PACKAGE_CONTRACT.md` | Creative MVP accepted; contract refined |
| Publication | Markdown export | Deferred | 5 | Publication Package contract | Package schema and export tests |
| Publication | Sanitized HTML export | Deferred | 5 | Publication Package contract | Sanitizer policy and security tests |
| Publication | Social variants | Deferred | 5 | Publication Package optional outputs | Approved package and channel rules |
| Publication | Selected visual/package pinning | Review-ready proposal | 5 | Publication Package contract | Version and invalidation rules accepted |
| Publishing | Publishing Authorization Record | Planned | 6 | target blueprint | Publishing ADR and authority model |
| Publishing | Normalized publishing connector contract | Planned | 6 | target blueprint | One target selected and validated |
| Publishing | LinkedIn connector | Deferred | 6 | target blueprint | Official/approved execution path and tests |
| Publishing | Viva Engage connector | Deferred | 6+ | target blueprint | First connector proof and demand |
| Publishing | CMS connector | Deferred | 6+ | target blueprint | Publication Package and CMS contract |
| Browser | Extension Bridge provider | Deferred | 6 | target blueprint | Publishing need and security review |
| Browser | CDP/Playwright provider | Deferred | 6 | target blueprint | Dedicated profile and action policy |
| Browser | Semantic browser provider | Deferred | 6+ | target blueprint | Bounded fallback and verification evidence |
| Publishing | Draft and preview mode | Planned | 6 | current draft-first principles | Publishing connector task |
| Publishing | Published-state verification | Planned | 6 | evidence and provenance principles | One live connector and fixture environment |
| Publishing | Research/write credential separation | Contracted as security rule | 4–6 | target blueprint security boundary | Enforced before authenticated/write access |
| Measurement | Workflow duration and approval latency | Deferred | 7 | PRD observability direction | Executable workflow and telemetry |
| Measurement | Revision and critic analytics | Deferred | 7 | target blueprint | Sufficient workflow runs |
| Measurement | Source-quality scoring | Deferred | 7 | target blueprint | Ground truth and calibration dataset |
| Measurement | Publication performance ingestion | Deferred | 7 | target blueprint | Published content and privacy policy |
| Measurement | Provider cost/token/latency ledger | Deferred | 7–8 | AI execution target architecture | Real provider volume justifies it |
| Learning | Approved brand and creative memory | Deferred | 7 | product pillar and target blueprint | Governance, versioning, retention policy |
| Learning | Outcome-driven recommendations | Deferred | 7 | target blueprint | Measured outcomes and evaluation controls |
| Platform | Multi-provider routing | Deferred | 8 | AI execution target architecture | Multiple proven providers and need |
| Platform | Provider fallback mesh | Deferred | 8 | target blueprint | Reliability evidence and risk policy |
| Platform | Engine SDK | Deferred | 8 | target structure | Stable engine contract and multiple engines |
| Platform | Connector SDK | Deferred | 8 | target structure | Stable connector pattern and demand |
| Platform | Enterprise tenancy | Deferred | 8 | security/product target | Pilot identity and isolation decisions |
| Platform | Advanced RBAC and delegated approvals | Deferred | 8 | enterprise target | Tenant and authority model accepted |
| Platform | Capability marketplace | Deferred | 8+ | target blueprint | Signing, trust, compatibility, and governance |
| Platform | Autonomous engagement optimization | Rejected for current roadmap | — | reconciliation matrix | New product, ethics, and safety decision required |

## Phase gates summary

| Phase | Required entry condition | Required exit evidence |
|---:|---|---|
| 0 | Existing authority and target blueprint available | Reconciliation documents linked; ADR-0004 proposed or decided |
| 1 | Product validation, contract acceptance, ADR-0003, toolchain, and DoR pass | Schemas, fixtures, validator, CI, independent review |
| 2 | Phase 1 accepted | Executable creative direction through Gate 1 with evidence |
| 3 | Phase 2 accepted | One-provider candidate path through Gate 2 and provenance |
| 4 | Creative MVP accepted and acquisition outcome validated | Four read-only channels, normalized sources, provenance, diagnostics |
| 5 | Acquisition/editorial outcome validated | Approved reproducible Publication Package |
| 6 | Publication Package accepted and one target authorized | One governed publishing connector with verification evidence |
| 7 | Sufficient workflow and outcome data | Validated measurement and learning controls |
| 8 | Repeated demand and stable internal seams | Enterprise/platform capabilities with independent evidence |

## Update rules

Update this map when:

- a capability receives human acceptance or rejection;
- a contract status changes;
- a task moves between blocked, ready, implemented, or accepted;
- verification changes the evidence state;
- a phase trigger is met or invalidated;
- an ADR changes capability ownership or sequence; or
- repository evidence contradicts the recorded state.

Do not promote a capability based only on prose, a mockup, generated code without verification, a passing score with failed gates, or an unmerged branch.
