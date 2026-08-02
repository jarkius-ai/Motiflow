# Blueprint Reconciliation Review

- **Status:** Review-ready architecture and documentation audit
- **Owner:** Chief Architect and independent reviewer
- **Reviewed source:** External `PROJECT_BLUEPRINT.md` v0.5.0-review
- **Source SHA-256:** `da8e88c5c384ff63c5f4ef76f67cd8ee83ee73e1a778c1b4c7a349f8fd06a366`
- **Source scope:** 32 numbered parts, appendices, 193 fixed-file records, 39 reserved directories, and 5 dynamic path classes
- **Review target:** Draft PR #7, `agent/reconcile-target-blueprint`

## 1. Decision sought

Determine whether the separately authored future-platform blueprint can become a governed Motiflow target architecture without changing the current product identity, bypassing the creative-direction MVP, duplicating MEOS, or authorizing speculative repository generation.

## 2. Review conclusion

The blueprint is strategically compatible with Motiflow **after reconciliation**, but it is not safe to adopt verbatim. Its strongest contribution is the future acquisition, browser, content, publication, measurement, and platform-expansion design. Its weakest fit is the assumption that one monolithic document and a 193-file manifest should bootstrap the repository immediately.

Recommended disposition:

1. Keep the repository authority chain and current ACDS decisive slice.
2. Adopt a repository-native target blueprint as future-state direction.
3. Use the Capability Expansion Roadmap to connect the MVP to the full platform.
4. Preserve the external blueprint as source evidence with a stable hash.
5. Dispose all fixed paths through [`BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`](BLUEPRINT_FILE_MANIFEST_DISPOSITION.md); do not generate them automatically.
6. Keep ADR-0004 `Proposed` until human and independent review decisions are recorded.

## 3. Load-bearing alignment decisions

| Concern | Reconciled decision |
|---|---|
| Product identity | Motiflow remains the product; ACDS remains the product architecture; MEOS remains engineering governance. |
| First product wedge | The ten-artifact, two-gate creative-direction slice remains the initial durable spine. |
| Future platform | Acquisition, Agent Reach, editorial, publication, publishing, measurement, and enterprise functions extend the spine through phases. |
| Blueprint authority | Target-state direction only; it cannot authorize implementation or override higher-authority repository sources. |
| Agent model | MEOS governs delivery roles; runtime engines, critics, and connectors use specific contracts. |
| Repository generation | Incremental, task-owned introduction replaces fixed 193-file generation. |
| Agent Reach | Optional replaceable Phase 4 acquisition/diagnostic provider behind Connector Gateway. |
| Browser execution | Later execution provider, not a core dependency; official APIs and normalized connectors are preferred. |
| Publishing authority | Final creative approval is not external publishing permission; publishing requires a separate authorization record. |
| Current readiness | Unchanged: Task 001 remains blocked and the repository remains pre-implementation. |

## 4. Section-by-section disposition

| Source section | Disposition | Canonical repository home | Required adjustment |
|---|---|---|---|
| Part I — Instructions for Every LLM and Contributor | Adapt | MEOS/02_AI_CONSTITUTION.md, MEOS/03_CONTEXT_STRATEGY.md, START_HERE.md | Keep destination-oriented rules, but remove competing bootstrap authority. |
| Part II — Project Identity and Product Direction | Adopt repository | PROJECT_CHARTER.md and MASTER_CONTEXT.md | Repository product identity and current decisive slice take precedence. |
| Part III — Architecture Evolution | Adapt | TARGET_PLATFORM_BLUEPRINT.md and CAPABILITY_EXPANSION_ROADMAP.md | Retain future-state direction as phases and expansion seams. |
| Part IV — Design Principles | Adopt/adapt | MASTER_CONTEXT.md and MEOS/01_ENGINEERING_CONSTITUTION.md | Consolidate product and engineering principles; avoid duplicate constitutions. |
| Part V — Canonical Domain Language | Adopt repository | docs/00-foundation/TERMINOLOGY.md | Legacy terms require explicit alias mapping; no new synonym set. |
| Part VI — Target System Architecture | Adapt | MASTER_CONTEXT.md, ARCHITECTURE_DEPENDENCY_MAP.md, TARGET_PLATFORM_BLUEPRINT.md | Map control/execution/integration concepts into Creative Kernel, Orchestrator, engines, critics, and Connector Gateway. |
| Part VII — Hybrid Browser Capability | Defer/adapt | Phase 6 connector/browser architecture | Preserve provider abstraction and profile isolation; do not make browser execution an MVP dependency. |
| Part VIII — Reference Repository Analysis and Reuse Plan | Archive/reference | docs/archive or source-analysis record | Useful research input, not architecture authority. |
| Part IX — Protocol and Event Model | Adopt/adapt | RUNTIME_CONTRACTS.md, WORKFLOW_STATE_MACHINE.md, future accepted schemas | Use existing commands/events/artifacts and versioning rules. |
| Part X — Project Intelligence and Parallel Work | Adapt | CONTEXT_INDEX.yaml, MEOS tasks/handoffs, artifact and run state | Separate engineering context/memory from product runtime knowledge. |
| Part XI — Agent Registry and Contracts | Adopt/adapt | MEOS/roles.yaml plus specific runtime engine/connector contracts | Do not treat every engineering role as a runtime agent. |
| Part XII — Capability Registry | Adapt/defer | engine, critic, model, connector, and workflow capability contracts | Create registries only as activated phases require them. |
| Part XIII — Platform Adapters | Defer/adapt | Connector Gateway and Phase 4/6 provider implementations | Keep platform-native types and credentials inside connectors. |
| Part XIV — Security, Privacy, and Compliance | Adopt/adapt | MEOS security rules, architecture docs, phase-specific threat models | Credential and external-write controls remain mandatory. |
| Part XV — Reliability and State Verification | Adopt/adapt | Workflow state machine, runtime contracts, MEOS quality gate | Retain idempotency, verification, fallback, and safe-stop principles. |
| Part XVI — Evidence and Observability | Adopt/adapt | Provenance Record, MEOS evidence, future observability implementation | Evidence must distinguish documentation, execution, and product validation. |
| Part XVII — Testing Strategy | Adopt repository | MEOS/10_QUALITY_GATE.md and task-specific verification | Use risk-based tests and mandatory gates rather than a parallel test constitution. |
| Part XVIII — Repository Structure | Reject immediate generation; adapt ownership | REPOSITORY_STRUCTURE.md | Target boundaries are useful, but directories appear only with governed artifacts. |
| Part XIX — File Generation and Repository Bootstrap | Reject/reframe | MEOS ready tasks and incremental migration | No mass repository bootstrap from a static manifest. |
| Part XX — Documentation-First Development Flow | Adopt/adapt | MEOS Golden Path and documentation rules | Documentation supports decisions but does not substitute for evidence. |
| Part XXI — Quality Gates and Definition of Done | Adopt repository | MEOS/06_DEFINITION_OF_READY.md and MEOS/10_QUALITY_GATE.md | Do not maintain competing readiness or scoring systems. |
| Part XXII — Coding and Review Standards | Adopt repository | MEOS coding/review standards | Use repository standards and independent review. |
| Part XXIII — POC, MVP, and Roadmap | Adapt | CAPABILITY_EXPANSION_ROADMAP.md | Current creative MVP becomes Phase 1–3; acquisition and publishing follow as connected phases. |
| Part XXIV — Initial Work Graph | Adapt | MEOS tasks, dependencies, and CONTEXT_INDEX.yaml | Convert approved phase work into bounded ready tasks rather than a static global graph. |
| Part XXV — ADR Seed List | Adapt/renumber | docs/adr/ and MEOS/14_ADR_PROCESS.md | Legacy ADR numbers collide with existing repository ADRs; concepts must be reviewed and renumbered. |
| Part XXVI — Review Checklist for This Blueprint | Adopt as supporting review | BLUEPRINT_RECONCILIATION_REVIEW.md and MEOS review evidence | Useful checklist, subordinate to repository quality gates. |
| Part XXVII — Bootstrap Prompt for Another LLM | Replace | START_HERE.md and CONTEXT_INDEX.yaml | Repository navigation must replace a standalone prompt. |
| Part XXVIII — Sources and Provenance | Adapt | source inventory, evidence/provenance contracts, archive metadata | Preserve source identity and hashes; do not make appendices authoritative. |
| Part XXIX — Deterministic Generation and Anti-Deviation Contract | Adapt | MEOS task contracts, context routing, schemas, validators, CI | Retain anti-invention discipline without enforcing the rejected fixed-file manifest. |
| Part XXX — Complete File Manifest | Reject as generation authority; preserve as source inventory | BLUEPRINT_FILE_MANIFEST_DISPOSITION.md | All 193 paths require disposition; none are automatically authorized. |
| Part XXXI — Completeness Audit and Review Boundary | Adapt | this review, PR review, independent evidence | Completeness means reconciled decisions, not file-count parity. |
| Part XXXII — External Knowledge Acquisition and Content Intelligence | Adapt/defer | TARGET_PLATFORM_BLUEPRINT.md Phases 4–7 | Preserve acquisition, Agent Reach, content, publishing, and measurement behind phase gates. |
| Appendices A–C | Archive/reference | source inventory and Git history | Retain historical rationale, supersession notes, and source hash; exclude from current authority. |

## 5. Manifest and repository-structure findings

The embedded manifest is internally deterministic, but its lifecycle model conflicts with the repository’s evidence-driven incremental structure. It declares most architecture, policy, agent, channel, provider, schema, workflow, template, and planning files for `phase-0-bootstrap`, before the corresponding product outcomes or contracts are accepted.

Required correction:

- Keep the 193 records as a source inventory only.
- Do not generate `planning/FILE_MANIFEST.yaml`.
- Do not reserve `src/motiflow/**`, channel/provider directories, browser packages, or test trees before a ready task owns them.
- Map implementation to the repository’s chosen stack and package boundaries rather than the source blueprint’s Python-first `src/motiflow` layout.
- Introduce schemas, workflows, policies, connectors, tests, and tooling with the exact phase and task that consumes them.

The complete per-file mapping is maintained in [`BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`](BLUEPRINT_FILE_MANIFEST_DISPOSITION.md).

## 6. Reserved-directory and dynamic-path decision

| Source class | Decision |
|---|---|
| `channels/`, `providers/` | Defer to Phase 4 and place under approved connector/config ownership. |
| `packages/browser-bridge-extension`, `packages/fixture-web`, `packages/local-console` | Defer to an exact product or integration task; no reservation now. |
| `planning/milestones`, `planning/work-items` | Reject duplicate; use MEOS tasks, roadmap, and repository evidence. |
| `src/motiflow/**` | Reject as predetermined implementation topology; use accepted Laravel/TypeScript/package architecture or a future ADR. |
| `tests/**` | Adopt the testing intent, but create task-owned test locations with implementation. |
| Dynamic milestone/work-item files | Route to MEOS tasks and approved delivery artifacts. |
| Dynamic runtime evidence | Keep outside source control unless an accepted retention contract defines a safe repository artifact. |
| Dynamic implementation files | Allowed only through exact ready-task ownership and repository structure rules. |
| Generation staging | Local/CI temporary state only; never a canonical source-of-truth path. |

## 7. Contract integration that must be completed before each later phase

```text
Normalized external source records
        ↓
Source bundle and claim/citation records
        ↓
Intake Package / Knowledge Fusion Package
        ↓
Existing creative-direction artifact chain
        ↓
Final Approval Record + Provenance Record
        ↓
Publication Package
        ↓
Publishing Authorization Record
        ↓
Published-state evidence and measurement events
```

No later contract may create a second artifact envelope, approval model, provenance system, or workflow-state owner.

## 8. Gaps remaining after this review

- The full external blueprint text is not yet committed to the repository; the target blueprint and disposition records preserve its decisions and hash, but the source file remains an external review input.
- ADR-0004 still needs explicit human disposition and independent Reviewer/QA evidence.
- Product validation and ADR-0003 remain the blockers for Task 001.
- Phase 4 source schemas, Phase 5 editorial contracts, Phase 6 publishing contracts, and Phase 7 measurement events remain intentionally undefined until their activation work begins.
- Technology choices for later acquisition/browser services must be decided through ready tasks or ADRs rather than inherited from the Python-first source layout.

## 9. Required PR #7 adjustments

- [x] Add a repository-native target blueprint.
- [x] Add capability state and expansion-phase documents.
- [x] Add a high-level reconciliation matrix.
- [x] Route navigation through `START_HERE.md` and `CONTEXT_INDEX.yaml`.
- [x] Add this section-level review.
- [x] Add the 193-file disposition record.
- [x] Link the detailed review artifacts from the document index and PR description.
- [ ] Perform independent architecture/documentation review.
- [ ] Record human decision on ADR-0004.

## 10. Merge recommendation

Keep PR #7 in draft until the detailed review artifacts are independently checked. After that, the documentation package may be merged as **review-ready target direction** without changing Task 001 readiness. ADR-0004 acceptance remains a separate explicit human decision; merging the PR must not imply acceptance unless the ADR approval table is updated by authorized humans.
