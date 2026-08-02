# Blueprint Reconciliation Matrix

- **Status:** Review-ready delivery and architecture reconciliation
- **Owner:** Chief Architect and Delivery
- **Source target:** `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- **Current product authority:** `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, accepted ADRs, and accepted product contracts
- **Delivery authority:** MEOS and ready task specifications

## Purpose

This matrix prevents the long-term target blueprint and the current Motiflow repository from becoming competing plans. It identifies how each major target capability relates to existing repository authority, when it may become active, and what decision or evidence is required before implementation.

## Dispositions

- **Adopt** — existing repository direction already provides the preferred model.
- **Adapt** — retain the concept, but fit it into ACDS, MEOS, canonical contracts, or current dependency rules.
- **Defer** — preserve as a future capability and activate only after its trigger.
- **Reject** — do not carry forward because it conflicts with product identity, duplicates authority, or creates premature structure.

A disposition does not mean implementation. Capability state is recorded separately in `TARGET_PLATFORM_CAPABILITY_MAP.md`.

## Reconciliation principles

1. Preserve Motiflow, ACDS, MEOS, Creative Kernel, Workflow Orchestrator, Connector Gateway, and Model Gateway terminology.
2. Preserve the ten-artifact decisive slice and two protected human approval gates.
3. Use MEOS for task readiness, context routing, implementation, independent review, quality gates, and release.
4. Treat the target blueprint as future-state capability direction, not current-state evidence.
5. Introduce directories and implementation artifacts only when an accepted contract or ready task requires them.
6. Connect future capabilities through stable contracts rather than replacing the validated core.

## Matrix

| Target concept | Repository authority or current equivalent | Disposition | Target phase | Activation or decision requirement |
|---|---|---|---:|---|
| Motiflow product identity | `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, terminology standard | Adopt | 0 | No change without product and ADR authority |
| ACDS architecture | `MASTER_CONTEXT.md`, system design, architecture dependency map | Adopt | 0 | Preserve component boundaries |
| MEOS engineering operating system | `MEOS/` constitutions, roles, gates, Golden Path | Adopt | 0 | Use as delivery authority rather than duplicate it |
| Single canonical onboarding route | `START_HERE.md`, `CONTEXT_INDEX.yaml` | Adopt | 0 | Route minimum complete context |
| One monolithic file as sole authority | Existing layered authority model | Reject | 0 | Blueprint remains subordinate target architecture |
| Full up-front 193-file repository generation | Incremental repository structure standard | Reject | 0 | Create only task-owned or contract-required paths |
| Deterministic generation discipline | MEOS contracts, context routing, task evidence | Adapt | 0–1 | Apply to schemas, tasks, checks, and generated artifacts |
| Capability-first architecture | `MASTER_CONTEXT.md`, Model/Connector Gateway, engine contracts | Adopt | 1–8 | Capabilities use versioned provider-neutral contracts |
| Ten canonical decisive-slice artifacts | Data and runtime contracts; ADR-0003 proposal | Adopt | 1 | Human acceptance and Task 001 readiness required |
| Artifact lineage and invalidation | Data contracts, runtime contracts, workflow state machine | Adopt | 1 | ADR-0003 and C-01–C-06 acceptance |
| Two human creative approval gates | Charter, Master Context, workflow state machine | Adopt | 1–3 | Must remain non-bypassable |
| Creative Kernel | `MASTER_CONTEXT.md`, architecture dependency map | Adopt | 2 | Thin implementation after contract proof |
| Workflow Orchestrator | `MASTER_CONTEXT.md`, runtime and workflow contracts | Adopt | 2 | One executable workflow before breadth |
| Deterministic mock engines | AI execution plan and Model Gateway direction | Adopt | 2–3 | Required for repeatable tests |
| Model Gateway | AI execution layer and ADR-0002 | Adapt | 3 | Thin interface, mock, and one provider first |
| Multi-provider routing mesh | Eventual AI execution architecture | Defer | 8 | Observed demand and one-provider proof |
| Generation provider connectors | Connector Gateway boundary | Adapt | 3 | One approved rendering provider first |
| Critic registry and review fusion | Existing critic contracts and evaluation framework | Adapt | 3 | Start with focused critics; no opaque score override |
| External web acquisition | Knowledge connector capability | Defer | 4 | Creative core MVP accepted and acquisition contracts approved |
| YouTube acquisition | Knowledge connector capability | Defer | 4 | Read-only provider and source provenance proof |
| GitHub acquisition | Knowledge connector capability | Defer | 4 | Read-only provider and source provenance proof |
| RSS acquisition | Knowledge connector capability | Defer | 4 | Read-only provider and source provenance proof |
| Channel registry | Connector capability descriptors | Adapt | 4 | Add only activated channels; no speculative marketplace |
| Provider health and `doctor` diagnostics | Connector operability and provider health | Adapt | 4 | Machine-readable health contract and safe remediation |
| Agent Reach integration | Optional knowledge connector-management provider | Adapt | 4 | Security and supply-chain review; read-only wrapper first |
| Agent Reach as core runtime | Conflicts with Motiflow-owned contracts and state | Reject | — | Keep replaceable behind Connector Gateway |
| Authenticated X/Reddit/social acquisition | Higher-risk knowledge providers | Defer | 4+ | Separate security, legal, credential, and platform review |
| Browser-session acquisition | Connector Gateway and browser capability | Defer | 4+ | Explicit profile, credential, injection, and audit controls |
| Research Agent | Motiflow Intelligence engine or bounded MEOS role | Adapt | 4–5 | Do not confuse delivery agent with runtime engine |
| Normalized Content Source | Supporting source artifact and Knowledge Fusion input | Adapt | 4 | Define versioned source contract and provenance |
| Research-to-draft workflow | Editorial workflow after creative core | Defer | 5 | Acquisition proof and editorial product validation |
| Article and editorial authoring | Publication specialization, explicitly post-MVP | Defer | 5 | Product evidence and accepted editorial contracts |
| Claim-to-source mapping | Provenance and factual-review capability | Adapt | 4–5 | Required before approved editorial package |
| Publication Package | Existing proposed publication contract | Adopt and refine | 5 | Preserve dependency on approved creative artifacts |
| Markdown and sanitized HTML export | Publication Package contract | Adopt | 5 | Reproducible export and sanitation tests |
| Social variants | Publication Package optional output | Defer | 5 | Derived from approved package; not independent truth |
| LinkedIn publishing connector | Post-MVP publishing connector | Defer | 6 | One authorized target, explicit publish approval, evidence |
| Viva Engage publishing connector | Post-MVP publishing connector | Defer | 6+ | Add after first publishing connector proof |
| Browser Bridge provider | Optional execution provider | Adapt and defer | 6 | Official API or approved connector preferred first |
| Playwright/CDP provider | Browser execution implementation | Defer | 6 | Dedicated profile, security controls, verification |
| Semantic browser provider | Higher-variance fallback | Defer | 6+ | Bounded actions and independent verification |
| Research and publishing credential separation | Security boundary | Adopt | 4–6 | Mandatory before authenticated research or write actions |
| Publishing approval gate | Additional external-action authority | Adapt | 6 | Separate from Final Approval Record |
| Published-state evidence | Existing evidence and provenance model | Adapt | 6 | Target verification, identifiers, timestamps, account proof |
| Engagement and performance measurement | Measurement and learning capability | Defer | 7 | Publishing or pilot data plus privacy policy |
| Source-quality scoring | Knowledge and evaluation capability | Defer | 7 | Ground-truth and calibration evidence |
| Cost, token, latency, retry ledger | AI execution architecture | Defer | 7–8 | Add when real provider usage justifies it |
| Reusable brand and creative memory | Knowledge and memory product pillar | Adapt | 7 | Only approved, versioned, policy-compliant knowledge |
| Autonomous engagement optimization | High-risk product behavior | Reject for early phases | — | Requires separate product, ethics, and safety decision |
| Connector SDK | Target platform boundary | Defer | 8 | Stable internal connector patterns and external demand |
| Engine SDK | Target platform boundary | Defer | 8 | Stable engine contract and multiple implementations |
| Capability marketplace | Ecosystem expansion | Defer | 8+ | Governance, trust, signing, compatibility, and demand |
| Enterprise tenancy and RBAC | Product and security architecture | Adapt and defer | 8 | Pilot identity decision first; scale from proven workflow |
| Full multi-channel autonomous platform | Long-term target | Defer | 8+ | Phase-by-phase evidence and human authorization |

## Blueprint section disposition

| Target blueprint area | Disposition | Governing repository home |
|---|---|---|
| Product mission and identity | Adopt repository | Project Charter and Master Context |
| Architecture principles and boundaries | Adopt/adapt | Master Context, architecture docs, ADRs |
| Agent governance and work execution | Adopt repository | MEOS |
| Canonical artifact and workflow contracts | Adopt repository | `docs/02-architecture/` and accepted schemas |
| Browser and publishing architecture | Adapt/defer | Target blueprint, capability map, future ADRs |
| Acquisition and Agent Reach | Adapt/defer | Target blueprint, future connector contracts and ADR |
| Repository file manifest | Reject as immediate generation authority | Repository structure standard and task ownership |
| Future capability inventory | Adopt as target state | Target blueprint and capability map |
| Phase sequencing | Adapt | Capability Expansion Roadmap and ready tasks |
| Current implementation status | Reject from static blueprint | Context Index, Project Bootstrap, tasks, tests, evidence |

## Required follow-through

The reconciliation is complete only when:

- the target blueprint is linked from the document index and context routing;
- the capability map records current states without overstating implementation;
- the expansion roadmap defines phase outcomes and activation gates;
- ADR-0004 records an authorized decision or remains visibly proposed;
- Task 001 remains governed by its existing prerequisites;
- later task specifications reference the relevant phase and expansion seam; and
- superseded standalone blueprint copies are treated as working inputs rather than competing repository authority.

## Review questions

1. Does any row silently change current MVP scope?
2. Does any adapted capability bypass the Creative Kernel, Workflow Orchestrator, Connector Gateway, or approval boundaries?
3. Does any deferred capability appear as implemented or ready?
4. Does the phase preserve a complete useful product outcome?
5. Can later phases connect through explicit contracts without rewriting the decisive core?
6. Is a new ADR, product-validation round, security review, or human decision required?
