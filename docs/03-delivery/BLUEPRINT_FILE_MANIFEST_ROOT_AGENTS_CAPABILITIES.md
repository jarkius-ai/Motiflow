# Blueprint Manifest Disposition — Root Agents Capabilities

- **Status:** Review-ready source-manifest reconciliation appendix
- **Owner:** Chief Architect and Documentation

This appendix is part of `BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`. It is a source-reconciliation record, not file-creation authority.

| ID | Original path | Disposition | Repository home or target | Phase | Rule |
|---|---|---|---|---:|---|
| `FILE-ROOT-015` | `.env.example` | Defer | application-specific environment example | 2+ | Only after real configuration keys and secret policy exist. |
| `FILE-ROOT-016` | `.gitignore` | Adopt/adjust | existing .gitignore | 0 | Update only when actual generated/runtime files require it. |
| `FILE-ROOT-008` | `AGENTS.md` | Reject duplicate | START_HERE.md + CONTEXT_INDEX.yaml + MEOS/roles.yaml | — | Would duplicate agent routing and authority. |
| `FILE-ROOT-006` | `CHANGELOG.md` | Defer | release notes / Git history; root CHANGELOG only when release practice requires it | 8 | Do not create solely to satisfy the old manifest. |
| `FILE-ROOT-009` | `CLAUDE.md` | Reject duplicate | START_HERE.md + MEOS/02_AI_CONSTITUTION.md | — | Provider-specific root instructions must not become a competing authority. |
| `FILE-ROOT-004` | `CONTEXT-MAP.md` | Adopt existing | CONTEXT_INDEX.yaml + docs/00-foundation/DOCUMENT_INDEX.md | 0 | Machine routing and human navigation are already separated. |
| `FILE-ROOT-003` | `CONTEXT.md` | Adopt existing | MASTER_CONTEXT.md | 0 | Stable shared architecture context already has a canonical home. |
| `FILE-ROOT-010` | `CONTRIBUTING.md` | Adapt/defer | MEOS Golden Path and contributor guidance; create later only for external contributors | 8 | MEOS already governs internal contribution. |
| `FILE-ROOT-012` | `LICENSE` | Verify/adopt | repository LICENSE if already selected by human owner | 0 | License choice is human/legal authority, never generated from blueprint. |
| `FILE-ROOT-001` | `PROJECT_BLUEPRINT.md` | Adapt | docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md | 0 | Repository-native target state; original remains source input, not root authority. |
| `FILE-ROOT-002` | `PROJECT_STATE.md` | Adopt existing | CONTEXT_INDEX.yaml + MEOS/20_PROJECT_BOOTSTRAP.md | 0 | Current state belongs in routed operational sources, not a duplicate root file. |
| `FILE-ROOT-007` | `README.md` | Adopt existing | README.md | 0 | Keep current product entry and link to canonical navigation. |
| `FILE-ROOT-005` | `ROADMAP.md` | Adapt | docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md + existing roadmap/task artifacts | 0 | Use phased capability activation rather than a competing root roadmap. |
| `FILE-ROOT-011` | `SECURITY.md` | Adapt/defer | security architecture, MEOS controls, future public security policy | 2–8 | Create a root policy only when disclosure/operations require it. |
| `FILE-AGENT-003` | `agents/architect.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-004` | `agents/browser.md` | Adapt/defer | future connector/browser implementation and docs | 6 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-AGENT-014` | `agents/content.md` | Adapt/defer | editorial engine/role contracts | 5 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-AGENT-008` | `agents/documentation.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-012` | `agents/operations.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-001` | `agents/orchestrator.md` | Adapt/defer | Workflow Orchestrator contracts and package | 2 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-AGENT-002` | `agents/planner.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-005` | `agents/platform-adapter.md` | Adapt/defer | future packages/connectors implementation | 6 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-AGENT-011` | `agents/principal-engineer.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-000` | `agents/registry.yaml` | Reject duplicate | MEOS/roles.yaml + CONTEXT_INDEX.yaml; runtime capabilities later in packages | — | Delivery roles and runtime components must remain distinct. |
| `FILE-AGENT-010` | `agents/release.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-013` | `agents/research.md` | Adapt/defer | Motiflow Intelligence engine/role contracts | 4 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-AGENT-006` | `agents/reviewer.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-009` | `agents/security.md` | Adopt existing | MEOS/roles.yaml + applicable MEOS standards | 0 | Engineering role already governed by MEOS; no duplicate agent file. |
| `FILE-AGENT-007` | `agents/verifier.md` | Adapt/defer | MEOS QA/reviewer plus runtime validators/critics | 1–3 | Do not create a second markdown agent constitution; activate as bounded role or runtime capability. |
| `FILE-CAP-005` | `capabilities/approval.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 1–2 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-001` | `capabilities/browser.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 6 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-010` | `capabilities/content-intelligence.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 5 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-009` | `capabilities/data-acquisition.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 4 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-007` | `capabilities/document-generation.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 5 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-004` | `capabilities/evidence.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 1 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-003` | `capabilities/filesystem.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 2 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-008` | `capabilities/knowledge.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 2–4 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-002` | `capabilities/llm.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 3 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-006` | `capabilities/project-state.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 2 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-CAP-000` | `capabilities/registry.yaml` | Adapt/defer | accepted engine/connector/workflow capability contracts under packages/ and docs/02-architecture/ | 2 | Create descriptors only when an accepted contract and ready task activate the capability. |
| `FILE-ROOT-014` | `package.json` | Defer | implementation task-owned TypeScript/application package | 1+ | Create with actual package scope and lockfile. |
| `FILE-ROOT-013` | `pyproject.toml` | Defer | implementation task-owned Python package, if Python remains justified | 4+ | Do not preselect runtime packaging before a ready task. |
| `FILE-RUNTIME-001` | `runs/.gitkeep` | Reject | external/local evidence storage governed by retention policy | — | Do not commit empty mutable run-state directories. |

**Record count:** 43
