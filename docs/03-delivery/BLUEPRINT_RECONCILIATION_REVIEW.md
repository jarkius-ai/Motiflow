# Blueprint Reconciliation and Responsibility Review

- **Status:** Direction accepted; independent review pending
- **Owner:** Product Owner and Chief Architect
- **Reviewed source:** External `PROJECT_BLUEPRINT.md` v0.5.0-review
- **Source SHA-256:** `da8e88c5c384ff63c5f4ef76f67cd8ee83ee73e1a778c1b4c7a349f8fd06a366`
- **Source scope:** 32 parts, 193 fixed files, 39 reserved directories, 5 dynamic path classes
- **Review target:** Draft PR #7
- **Decision:** ADR-0004 accepted on 2026-08-02

## 1. Review question

Can the separately authored future-platform blueprint become part of Motiflow without:

- redefining the product;
- bypassing the creative-direction MVP;
- duplicating MEOS;
- creating competing artifact, approval, provenance, or workflow systems;
- authorizing Agent Reach, browser automation, proxies, or publishing prematurely;
- triggering speculative repository generation?

## 2. Conclusion

**Yes, after responsibility refactoring and phased reconciliation.**

The external blueprint contributes a strong future vision for acquisition, browser providers, editorial intelligence, Publication Packages, publishing, measurement, learning, and enterprise expansion.

It is not safe as a monolithic implementation authority. Its product, architecture, state, phase, engineering, task, CI, test, and file-manifest concerns must be assigned to separate canonical owners.

That refactor has now been applied on PR #7.

## 3. Accepted responsibility model

```text
PROJECT_CHARTER.md
  WHY Motiflow exists

MASTER_CONTEXT.md
  WHAT Motiflow is and its stable ACDS architecture

TARGET_PLATFORM_BLUEPRINT.md
  WHERE the complete platform may go

TARGET_PLATFORM_CAPABILITY_MAP.md
  WHAT exists or is deferred today

CAPABILITY_EXPANSION_ROADMAP.md
  HOW the platform expands through phases

ADRs
  WHY consequential architecture choices were made

MEOS
  HOW work is made ready, built, reviewed, verified, and released

Ready Task
  WHAT is authorized now

Evidence
  WHAT is actually true
```

## 4. Product outcome after reconciliation

The first product remains the governed creative-direction MVP:

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

The mature platform may later add:

```text
Knowledge Acquisition
→ Editorial Intelligence
→ Publication Package
→ Publishing Authorization
→ Channel Execution
→ Measurement
→ Governed Learning
→ Enterprise and Ecosystem Capabilities
```

The future platform extends the creative spine through versioned seams. It does not replace it.

## 5. Architecture mapping

| Source concept | Motiflow owner after reconciliation |
|---|---|
| Kernel/policy/validation core | Creative Kernel |
| Workflow and retry coordination | Workflow Orchestrator |
| AI/runtime worker roles | Specialist Engines, Critics, or bounded runtime agents |
| Engineering/development agents | MEOS roles |
| Provider/model registry concepts | Connector Gateway and Model Gateway capability contracts |
| Research/acquisition | Knowledge Acquisition capability behind Connector Gateway |
| Agent Reach | Optional Phase 4 acquisition adapter |
| Browser automation | Optional Phase 6 provider behind browser/execution connector seam |
| Content authoring | Editorial Intelligence, Phase 5 |
| Publication assembly | Publication Package, Phase 5 |
| External posting | Publishing Connector plus Publishing Authorization, Phase 6 |
| Analytics/learning | Measurement Events and governed Learning Proposals, Phase 7 |
| Multi-provider/SDK/tenancy | Enterprise platform, Phase 8 |

## 6. Provider decisions

### Agent Reach

- Retained as a useful future option.
- Deferred to Phase 4.
- Not installed or integrated.
- Not part of the core architecture.
- Must remain replaceable behind Motiflow acquisition contracts.
- Requires supply-chain/security review, wrapper proof, ready task, and independent evidence.

### Browser providers

- Extension Bridge, Playwright/CDP, and semantic browser systems remain possible implementations.
- None is selected or active.
- Official or approved API paths are preferred when suitable.
- Browser activation requires explicit need, security/legal review, dedicated profile, bounded action policy, and verification.

### Proxy infrastructure

- Not a Motiflow requirement.
- Not approved or implemented.
- Cannot be silent fallback or an evasion mechanism.
- Any legitimate future need requires a separate accepted high-risk decision and task.

## 7. Source manifest review

All 193 fixed paths have one explicit disposition across the manifest records.

The source manifest is retained as historical design inventory only. It is not:

- copied into a current `FILE_MANIFEST.yaml`;
- a repository allow-list;
- permission to create files or directories;
- evidence that capabilities exist.

The 39 reserved directories and 5 dynamic path classes are also treated as deferred inventory subject to accepted need and task ownership.

## 8. Content migration result

No useful category was simply thrown away:

- product intent moved to the Charter;
- stable architecture moved to Master Context;
- target capabilities stayed in the Blueprint;
- phases stayed in the Roadmap;
- current state stayed in the Capability Map and Bootstrap;
- engineering/readiness stayed in MEOS;
- task details stayed in tasks;
- source file intent stayed in disposition records;
- provider detail stayed as deferred options and risk controls;
- superseded wording remains in Git history.

The migration is recorded in `DOCUMENT_RESPONSIBILITY_MIGRATION_REPORT.md`.

## 9. LLM-confusion review

The main confusion risks were:

1. Treating the blueprint as implementation authority.
2. Confusing ACDS and MEOS.
3. Assuming an ADR is accepted merely because it exists.
4. Treating a roadmap phase as a ready task.
5. Treating a provider named in architecture as selected or installed.
6. Treating documentation score as implementation readiness.

Controls now include:

- one-screen orientation in `START_HERE.md`;
- canonical owner routing in `CONTEXT_INDEX.yaml`;
- Document Responsibility Model;
- Architecture Change Gate;
- accepted ADR-0004;
- evidence-based Capability Map;
- explicit current-state Bootstrap;
- provider-specific high-risk routing;
- `stop_and_escalate` rules for conflict.

## 10. Current status

| Item | Status |
|---|---|
| Product-to-platform direction | Accepted |
| Documentation responsibility model | Accepted and applied |
| Blueprint destination architecture | Refactored |
| Phase 0–8 roadmap | Retained and aligned |
| Capability Map | Active and aligned |
| 193-file dispositions | Complete |
| Structural/semantic self-validation | Pass |
| Independent architecture/documentation review | Pending |
| Independent QA/link/state verification | Pending |
| Runtime implementation | Not started |
| Task 001 | Blocked at 40/100 readiness |

## 11. Merge recommendation

Keep PR #7 in draft until independent Reviewer and QA checks are recorded and any findings are corrected.

After those review controls pass, PR #7 may be marked ready to merge as an accepted architecture/governance reconciliation. Merging it still does not activate Phase 1 or change Task 001 readiness.

## 12. Implementation recommendation

After PR #7 review is complete, return to the existing decisive-slice path:

1. Intended-user validation.
2. Product Owner `PROCEED`, `REVISE`, or `STOP`.
3. Contract acceptance and ADR-0003.
4. Task 001 Definition of Ready.
5. Phase 1 contract proof only.
