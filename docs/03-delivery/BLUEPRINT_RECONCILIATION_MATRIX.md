# Blueprint Reconciliation Matrix

- **Status:** Accepted direction; implementation dispositions remain phase-gated
- **Owner:** Product Owner, Chief Architect, Delivery
- **Source:** External `PROJECT_BLUEPRINT.md` v0.5.0-review
- **Source SHA-256:** `da8e88c5c384ff63c5f4ef76f67cd8ee83ee73e1a778c1b4c7a349f8fd06a366`
- **Decision:** ADR-0004
- **Responsibility:** Map source-blueprint concepts to their repository owner and disposition
- **Does not own:** Current implementation state, phase authorization, or task instructions

## 1. Dispositions

- **Adopt** — existing repository direction is canonical.
- **Adapt** — retain the concept but fit it into ACDS, MEOS, and canonical contracts.
- **Defer** — retain as a future capability activated only by its roadmap gate.
- **Reject** — exclude because it duplicates authority, conflicts with the product, or creates unsafe/premature structure.
- **Archive/reference** — preserve source intent and traceability without current authority.

Disposition is not implementation state. State is owned by `../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`.

## 2. Responsibility reconciliation

| Source information class | Canonical repository owner | Disposition | Result |
|---|---|---|---|
| Product vision, mission, scope, and value | `PROJECT_CHARTER.md` | Adopt repository | External overlap consolidated; Charter is canonical |
| Stable ACDS identity and component boundaries | `MASTER_CONTEXT.md` and accepted ADRs | Adopt/adapt | Source concepts mapped to Creative Kernel, Orchestrator, Gateways, engines, critics, and Studio |
| Complete future capability destination | `TARGET_PLATFORM_BLUEPRINT.md` | Adopt/adapt | Preserved as provider-neutral destination architecture |
| Current capability state | `TARGET_PLATFORM_CAPABILITY_MAP.md` | Reject from static blueprint | State requires evidence and decisions |
| Phase sequencing and activation | `CAPABILITY_EXPANSION_ROADMAP.md` | Adapt | Phase 0–8 retained outside the blueprint |
| Engineering roles, readiness, QA, and release | MEOS | Adopt repository | Duplicate source governance rejected |
| Bounded implementation work | `MEOS/tasks/` | Reject from blueprint | Work begins only through ready tasks |
| CI, exact tests, command names | Tasks and engineering evidence | Move | Removed from destination architecture |
| Repository file manifest | Manifest disposition records | Reject immediate authority | All 193 paths retained as reviewed inventory, not a path allow-list |
| Provider selection and installation | Capability contract, ADR/security review, ready task | Reject from blueprint | Provider examples remain non-binding |

## 3. Product and architecture concepts

| Source concept | Repository equivalent | Disposition | Target phase or owner | Activation/decision rule |
|---|---|---|---|---|
| Motiflow product identity | Charter and Master Context | Adopt | Foundation | No competing identity |
| ACDS architecture | Master Context and architecture docs | Adopt | Foundation | Material change requires ADR |
| MEOS engineering operating system | `MEOS/` | Adopt | Foundation | Remains sole engineering governance |
| One monolithic blueprint as sole authority | Layered responsibility model | Reject | ADR-0004 | No document owns vision, architecture, state, roadmap, tasks, and evidence together |
| Full up-front 193-file generation | Incremental repository introduction rule | Reject | ADR-0004 | Exact path requires accepted need or ready task |
| Deterministic artifact/contract discipline | Existing contracts and MEOS | Adapt | Phase 1 onward | Apply through schemas, fixtures, tests, and evidence |
| Ten canonical artifacts | Existing decisive-slice authority | Adopt | Phase 1 | ADR-0003 and contract acceptance required |
| Two human creative gates | Existing workflow model | Adopt | Phases 1–3 | Non-bypassable |
| Creative Kernel | Existing ACDS component | Adopt | Phase 2 | Thin implementation after contract proof |
| Workflow Orchestrator | Existing ACDS component | Adopt | Phase 2 | One executable workflow before breadth |
| Model Gateway | Existing provider-neutral boundary | Adapt | Phase 3 | Mock and one provider first |
| Multi-provider mesh | Future platform | Defer | Phase 8 | Proven multiple-provider need |
| Critics and review fusion | Existing evaluation model | Adapt | Phase 3 | Dimension findings cannot be hidden by aggregate score |

## 4. Acquisition and external-provider concepts

| Source concept | Repository boundary | Disposition | Target phase | Rule |
|---|---|---|---:|---|
| Public web acquisition | Knowledge acquisition provider | Defer | 4 | Read-only contract and security controls |
| YouTube transcript acquisition | Knowledge acquisition provider | Defer | 4 | Normalized source and provenance |
| Public GitHub acquisition | Knowledge acquisition provider | Defer | 4 | Read-only and rights-aware |
| RSS/Atom acquisition | Knowledge acquisition provider | Defer | 4 | Normalized feed evidence |
| Channel registry | Connector capability descriptors | Adapt/defer | 4 | Add only activated capabilities |
| Provider health and doctor diagnostics | Connector operability | Adapt/defer | 4 | Machine-readable health contract |
| Agent Reach | Optional acquisition adapter | Adapt/defer | 4 | Not core; security/supply-chain review and wrapper POC required |
| Agent Reach as runtime/state authority | Conflicts with Motiflow ownership | Reject | — | Must remain replaceable behind Connector Gateway |
| Authenticated social acquisition | High-risk provider path | Defer | 4+ | Separate product/legal/security/credential decision |
| Browser-session acquisition | High-risk connector path | Defer | 4+ | Dedicated profile, injection controls, audit, ready task |
| Proxy infrastructure | Not a platform requirement | Reject as default | — | Separate legitimate need and accepted high-risk decision required |

## 5. Editorial, publication, and publishing concepts

| Source concept | Repository boundary | Disposition | Target phase | Rule |
|---|---|---|---:|---|
| Research Agent | Motiflow Intelligence engine or bounded delivery role | Adapt | 4–5 | Runtime engine and MEOS role remain distinct |
| Normalized Content Source | Normalized Source Record/Source Bundle | Adapt | 4 | Must reference canonical provenance |
| Research-to-draft workflow | Editorial workflow | Defer | 5 | Acquisition and editorial validation first |
| Article/editorial authoring | Editorial intelligence | Defer | 5 | Post-creative-MVP product evidence required |
| Claim-to-source mapping | Provenance/factual review | Adapt | 4–5 | Required for approved editorial content |
| Publication Package | Existing post-MVP contract | Adopt/refine | 5 | Wraps approved creative chain; does not replace it |
| Markdown and sanitized HTML | Publication exports | Adopt/defer | 5 | Reproducibility and sanitation evidence |
| Social variants | Derived package outputs | Defer | 5 | Must derive from approved package versions |
| LinkedIn/Viva/CMS connectors | Publishing connector implementations | Defer | 6+ | One authorized target at a time |
| Browser Extension Bridge | Optional browser provider | Adapt/defer | 6 | Official/approved API preferred; security review required |
| Playwright/CDP | Optional browser provider | Defer | 6 | Dedicated profile and action policy |
| Semantic browser | Higher-variance fallback | Defer | 6+ | Bounded action and independent verification |
| Publishing approval | Separate Publishing Authorization Record | Adapt | 6 | Final creative approval is not permission to publish |
| Published-state evidence | Evidence/provenance extension | Adapt | 6 | Verify destination, account, identifier, time, and content hash |

## 6. Measurement and enterprise concepts

| Source concept | Repository boundary | Disposition | Target phase | Rule |
|---|---|---|---:|---|
| Workflow, revision, source, provider, and publication metrics | Measurement events | Defer | 7 | Stable definitions and sufficient data |
| Governed learning | Learning proposals and approved memory updates | Adapt/defer | 7 | Metrics cannot silently change policy/contracts |
| Cost/token/latency ledger | Provider evidence | Defer | 7–8 | Real usage must justify it |
| Brand and creative memory | Approved knowledge | Adapt/defer | 7 | Versioning, policy, and retention required |
| Connector and Engine SDKs | Ecosystem seams | Defer | 8 | Stable internal contracts and demand |
| Enterprise tenancy/RBAC | Enterprise platform | Adapt/defer | 8 | Identity, isolation, and authority model required |
| Capability marketplace | Governed ecosystem | Defer | 8+ | Signing, trust, compatibility, and demand |
| Autonomous engagement optimization | New high-risk product | Reject current roadmap | — | Separate ethics, safety, and product decision required |

## 7. File-level reconciliation

All 193 fixed-file records from the external source are dispositioned in:

- `BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`
- `BLUEPRINT_FILE_MANIFEST_ROOT_AGENTS_CAPABILITIES.md`
- `BLUEPRINT_FILE_MANIFEST_CHANNELS_PROVIDERS_POLICIES.md`
- `BLUEPRINT_FILE_MANIFEST_CONTRACTS_WORKFLOWS.md`
- `BLUEPRINT_FILE_MANIFEST_DOCUMENTS.md`
- `BLUEPRINT_FILE_MANIFEST_PLANNING_SCRIPTS_TEMPLATES.md`

The source also declares 39 reserved directories and 5 dynamic path classes; these remain reviewed target inventory, not immediate repository structure.

## 8. Accepted conclusion

The external blueprint is strategically compatible after reconciliation.

The repository adopts:

- its broader future capability vision;
- provider-neutral acquisition, browser, editorial, publication, publishing, measurement, and enterprise concepts;
- its useful contract and provenance ideas;
- its expansion intent.

The repository rejects:

- monolithic authority;
- duplicate MEOS governance;
- a competing artifact or workflow-state system;
- immediate mass file generation;
- provider or proxy activation from architecture prose;
- broad autonomous publishing or engagement in early phases.

ADR-0004 records the accepted direction. Independent review and QA remain required before PR #7 is ready to merge. No implementation phase is activated by this matrix.
