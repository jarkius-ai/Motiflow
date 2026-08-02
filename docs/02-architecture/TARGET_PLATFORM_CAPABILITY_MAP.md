# Motiflow Target Platform Capability Map

- **Status:** Active portfolio-state control
- **Owner:** Product Owner, Chief Architect, Delivery
- **Target architecture:** `TARGET_PLATFORM_BLUEPRINT.md`
- **Delivery sequencing:** `../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- **Engineering execution:** MEOS
- **Responsibility:** Record the evidence-based current state of every current and future capability
- **Does not own:** Product vision, architecture design, delivery authorization, or implementation instructions

## 1. Purpose

This map prevents target architecture, planning, prototypes, and documentation from being mistaken for implemented product behavior.

A capability state changes only from repository evidence and the applicable human decisions. The blueprint cannot promote state. The roadmap cannot promote state. A task cannot promote state until its acceptance evidence exists.

## 2. State vocabulary

| State | Meaning |
|---|---|
| **Accepted foundation** | Human-authorized product, architecture, or governance direction exists. |
| **Implemented governance** | Repository governance or routing behavior exists and is in active use. |
| **Implemented runtime** | Runtime behavior exists with required verification evidence. |
| **Validated** | Product or operational evidence demonstrates the intended outcome. |
| **Contracted** | Accepted normative contracts exist; runtime may not. |
| **Review-ready** | A coherent proposal exists but required acceptance or independent review is pending. |
| **Planned** | Assigned to a future phase but not activated. |
| **Deferred** | Intentionally postponed until an explicit trigger occurs. |
| **Experimental** | Isolated research or proof of concept; no production claim. |
| **Rejected** | Considered and intentionally excluded. |
| **Blocked** | A required dependency, decision, evidence set, or environment prevents progress. |

`Documented`, `designed`, `generated`, and `scored` are not implementation states.

## 3. Current portfolio summary

- Product and future-platform direction are accepted.
- The documentation responsibility model and context routing are implemented as repository governance.
- Runtime and application implementation have not started on `main`.
- Intended-user MVP validation remains pending.
- ADR-0003 and decisive-slice contract acceptance remain pending.
- Task 001 remains blocked with readiness score 40/100.
- Agent Reach is deferred and not installed.
- No browser provider is selected or implemented.
- Proxy infrastructure is not required, approved, or implemented.
- ADR-0006 acceptance does not activate any implementation phase.

## 4. Governance and authority

| Capability | Current state | Evidence or authority | Next trigger |
|---|---|---|---|
| Motiflow product identity and durable scope | Accepted foundation | `PROJECT_CHARTER.md` | Change only through product authority and applicable ADR |
| Stable ACDS architecture | Accepted foundation | `MASTER_CONTEXT.md` | Change only through accepted ADR |
| MEOS engineering governance | Implemented governance | `MEOS/` | Continue task-by-task enforcement |
| Canonical onboarding | Implemented governance | `START_HERE.md` | Keep routing current |
| Machine-readable context routing | Implemented governance | `CONTEXT_INDEX.yaml` | Validate and update with authority changes |
| Document Responsibility Model | Implemented governance | `docs/00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md`, ADR-0006 | Independent review and continued enforcement |
| Architecture Change Gate | Implemented governance | `docs/00-foundation/ARCHITECTURE_CHANGE_GATE.md` | Apply to consequential changes |
| Independent reviewer and QA separation | Contracted | MEOS Review Standard and Quality Gate | Assign independent evidence per task/PR |
| Target Platform Blueprint | Accepted foundation | ADR-0006, `TARGET_PLATFORM_BLUEPRINT.md` | Update through architecture review and ADR when material |
| Blueprint reconciliation | Accepted direction; structural review complete | reconciliation matrix, review, validation, manifest dispositions | Independent review and QA before PR readiness |
| External v0.5.0 file manifest | Rejected as immediate authority; retained as reference | manifest disposition records | Individual paths introduced only by accepted need and ready task |

## 5. Product validation and decisive-slice readiness

| Capability or decision | Current state | Evidence | Next trigger |
|---|---|---|---|
| Manual MVP validation protocol | Review-ready | validation plan and instruments | Execute with intended users |
| Intended-user evidence | Planned | dated validation report placeholder | Complete sessions and record evidence |
| Product Owner PROCEED/REVISE/STOP decision | Planned | named authority | Evidence-backed decision |
| Ten-artifact decisive-slice vocabulary | Review-ready | Charter, Master Context, contract docs | Human contract acceptance |
| Canonical artifact envelope | Review-ready | ADR-0003 | Accept/revise/reject ADR-0003 |
| Versioned parent references | Review-ready | ADR-0003 and Task 001 | Contract acceptance and schema proof |
| Direction Approval Record contract | Review-ready | workflow/runtime contracts | Accepted schemas and fixtures |
| Final Approval Record contract | Review-ready | workflow/runtime contracts | Accepted schemas and fixtures |
| Provenance Record contract | Review-ready | decisive-slice contracts | Accepted schemas and fixtures |
| Task 001 | Blocked | task spec and readiness review | All prerequisites and Definition of Ready pass |
| Deterministic contract validator | Planned | Task 001 | Task 001 ready and implemented |
| CI contract enforcement | Planned | Task 001 | Validator exists and Task 001 implemented |

## 6. Core creative runtime

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Creative Kernel interface | Review-ready architecture | 2 | Accepted Phase 1 contract proof |
| Workflow Orchestrator interface | Review-ready architecture | 2 | Accepted Phase 1 contract proof |
| Artifact repository and immutable versions | Planned | 2 | Storage decision and ready task |
| Workflow state transitions | Review-ready contract | 2 | Accepted transition contracts |
| Direction approval pause/resume | Review-ready contract | 2 | Executable workflow task ready |
| Deterministic normalization/fusion/direction engines | Planned | 2 | Phase 2 task ready |
| Project and brief workspace | Planned | 2 | Creative-core API/state contract |
| Direction review workspace | Planned | 2 | Direction workflow executable |
| Runtime observability and evidence | Review-ready architecture | 2 | Runtime task with accepted evidence contract |

## 7. Generation, evaluation, and final approval

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Thin Model Gateway | Review-ready architecture | 3 | Creative core proven |
| Deterministic mock model adapter | Planned | 3 | Model Gateway task ready |
| One real model/provider adapter | Planned | 3 | Mock and contract tests pass |
| Provider-neutral Generation Specification | Review-ready contract | 3 | Phase 1 schemas accepted |
| One rendering-provider connector | Planned | 3 | Provider/security task ready |
| Generated Candidate Set | Review-ready contract | 3 | Generation workflow implemented |
| Deterministic candidate checks | Planned | 3 | Candidate fixtures and rules accepted |
| Focused critic implementations | Planned | 3 | Evaluation criteria and fixtures accepted |
| Critic Evaluation Package | Review-ready contract | 3 | Contract proof and critic task |
| Final approval workspace | Planned | 3 | Candidate and critic workflow works |
| End-to-end provenance closure | Planned | 3 | Full creative MVP evidence |

## 8. Knowledge acquisition

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Acquisition Request/Result contracts | Planned | 4 | Phase 3 MVP accepted and acquisition decision/task |
| Normalized Source Record | Planned | 4 | Source schema, rights, and data policy accepted |
| Source Bundle and citation mapping | Planned | 4 | Acquisition fixtures and provenance tests |
| Public web provider | Deferred | 4 | Read-only acquisition phase activated |
| YouTube transcript provider | Deferred | 4 | Read-only acquisition phase activated |
| Public GitHub source provider | Deferred | 4 | Read-only acquisition phase activated |
| RSS/Atom provider | Deferred | 4 | Read-only acquisition phase activated |
| Channel capability descriptors | Deferred | 4 | Activated provider set requires them |
| Provider health contract | Deferred | 4 | Providers selected for proof |
| `motiflow doctor` diagnostics | Deferred | 4 | Machine-readable health contract |
| Agent Reach adapter | Deferred; not installed | 4 | Security/supply-chain review, accepted contracts, wrapper POC, ready task |
| Authenticated X/Reddit/social acquisition | Deferred high-risk | 4+ | Separate product, legal, security, credential, and platform review |
| LinkedIn research provider | Deferred high-risk | 4+ | Public/read path and policy review |
| Browser-session source provider | Deferred high-risk | 4+ | Dedicated profile, credential controls, accepted decision, ready task |

## 9. Editorial and Publication Package

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Research Brief | Deferred | 5 | Acquisition and editorial validation |
| Claim extraction and evidence map | Deferred | 5 | Source and claim contracts accepted |
| Editorial drafting engine | Deferred | 5 | Product validation and editorial task |
| Factual review | Deferred | 5 | Evidence model and review criteria accepted |
| Brand review | Deferred | 5 | Brand policy and fixtures accepted |
| Publication Package | Review-ready post-MVP contract | 5 | Creative MVP accepted and contract refined |
| Markdown export | Deferred | 5 | Package schema and export tests |
| Sanitized HTML export | Deferred | 5 | Sanitizer policy and security tests |
| Social/channel variants | Deferred | 5 | Approved package and channel rules |
| Visual/content version pinning | Review-ready proposal | 5 | Invalidation and approval rules accepted |

## 10. Publishing and browser execution

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Publishing Authorization Record | Planned | 6 | Publishing ADR and authority model |
| Normalized publishing connector | Planned | 6 | One target selected and validated |
| LinkedIn connector | Deferred | 6 | Official/approved path and tests |
| Viva Engage connector | Deferred | 6+ | First connector proof and demand |
| CMS connector | Deferred | 6+ | Publication Package and CMS contract |
| Extension Bridge provider | Deferred; not selected | 6 | Demonstrated need and security review |
| CDP/Playwright provider | Deferred; not selected | 6 | Dedicated profile, action policy, ready task |
| Semantic browser provider | Deferred; not selected | 6+ | Bounded fallback and verification evidence |
| Draft and preview mode | Planned | 6 | Publishing connector task |
| Published-state verification | Planned | 6 | One live connector and controlled environment |
| Research/write credential separation | Contracted security rule | 4–6 | Enforce before authenticated or write access |
| Proxy infrastructure | Rejected as default requirement; not approved | — | New legitimate need, legal/security review, accepted decision, policy, and ready task |
| Autonomous engagement optimization | Rejected for current roadmap | — | New product, ethics, safety, and authority decision |

## 11. Measurement, learning, and platform expansion

| Capability | Current state | Target phase | Activation trigger |
|---|---|---:|---|
| Workflow duration and approval latency | Deferred | 7 | Executable workflow and telemetry |
| Revision and critic analytics | Deferred | 7 | Sufficient workflow runs |
| Source-quality scoring | Deferred | 7 | Ground truth and calibration data |
| Publication performance ingestion | Deferred | 7 | Published content and privacy policy |
| Provider cost/token/latency ledger | Deferred | 7–8 | Real provider volume justifies it |
| Approved brand and creative memory | Deferred | 7 | Governance, versioning, retention policy |
| Outcome-driven recommendations | Deferred | 7 | Measured outcomes and evaluation controls |
| Multi-provider routing | Deferred | 8 | Multiple proven providers and demonstrated need |
| Provider fallback mesh | Deferred | 8 | Reliability evidence and risk policy |
| Engine SDK | Deferred | 8 | Stable engine contract and multiple implementations |
| Connector SDK | Deferred | 8 | Stable connector pattern and demand |
| Enterprise tenancy | Deferred | 8 | Pilot identity and isolation decisions |
| Advanced RBAC/delegated approval | Deferred | 8 | Tenant and authority model accepted |
| Capability marketplace | Deferred | 8+ | Signing, trust, compatibility, governance, and demand |

## 12. Phase gates summary

| Phase | Entry condition | Exit evidence |
|---:|---|---|
| 0 | Repository authority and external blueprint available | Responsibility model, reconciliation, accepted ADR-0006, independent review/QA |
| Pre-1 | Validation protocol and decision instruments ready | Intended-user evidence, Product Owner decision, contract acceptance, ADR-0003, Task 001 DoR |
| 1 | Pre-1 mandatory gates pass | Schemas, fixtures, validator, CI, independent review |
| 2 | Phase 1 accepted | Executable creative direction through Gate 1 |
| 3 | Phase 2 accepted | One-provider candidate path through Gate 2 and provenance |
| 4 | Creative MVP accepted and acquisition outcome justified | Read-only providers, normalized sources, provenance, diagnostics |
| 5 | Acquisition/editorial outcome validated | Approved reproducible Publication Package |
| 6 | Publication Package accepted and one target authorized | One governed publishing connector with evidence |
| 7 | Sufficient workflow/outcome data | Validated measurement and governed learning |
| 8 | Repeated demand and stable seams | Enterprise/platform capabilities with independent evidence |

## 13. Update rules

Update this map when:

- an authorized human accepts, revises, or rejects a capability or decision;
- a contract status changes;
- a task changes state;
- implementation or verification evidence changes reality;
- a phase trigger is met or invalidated;
- an ADR changes ownership, sequence, security, or provider direction;
- repository evidence contradicts the map.

Never promote state from prose, an unmerged branch, a mockup, generated code without verification, a provider response, or a score with failed mandatory gates.
