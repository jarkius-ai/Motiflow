# Blueprint Manifest Disposition — Planning Scripts Templates

This appendix is part of `BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`. It is a source-reconciliation record, not file-creation authority.

| ID | Original path | Disposition | Repository home or target | Phase | Rule |
|---|---|---|---|---:|---|
| `FILE-PLAN-004` | `planning/BACKLOG.md` | Reject duplicate | CAPABILITY_EXPANSION_ROADMAP.md + MEOS tasks + CONTEXT_INDEX.yaml | — | Would create a competing delivery authority. |
| `FILE-PLAN-005` | `planning/DECISION_REGISTER.md` | Adopt existing | docs/adr/ and document index | 0 | ADRs are the decision register. |
| `FILE-PLAN-003` | `planning/FILE_MANIFEST.yaml` | Reject immediate authority | BLUEPRINT_FILE_MANIFEST_DISPOSITION.md + task-owned paths | — | Preserve source inventory, not generation authority. |
| `FILE-PLAN-008` | `planning/GENERATION_REPORT.md` | Adapt | MEOS quality gate/review evidence | 0+ | Use task-specific evidence rather than global generated state. |
| `FILE-PLAN-001` | `planning/MASTER_PLAN.md` | Reject duplicate | CAPABILITY_EXPANSION_ROADMAP.md + MEOS tasks + CONTEXT_INDEX.yaml | — | Would create a competing delivery authority. |
| `FILE-PLAN-007` | `planning/REVIEW_CHECKLIST.md` | Adapt | MEOS quality gate/review evidence | 0+ | Use task-specific evidence rather than global generated state. |
| `FILE-PLAN-006` | `planning/RISK_REGISTER.md` | Adapt | task/ADR risk sections; portfolio risk artifact only if operational need emerges | 0+ | Avoid an unowned static register. |
| `FILE-PLAN-002` | `planning/TASK_GRAPH.yaml` | Reject duplicate | CAPABILITY_EXPANSION_ROADMAP.md + MEOS tasks + CONTEXT_INDEX.yaml | — | Would create a competing delivery authority. |
| `FILE-SCRIPT-001` | `scripts/bootstrap_repo.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-009` | `scripts/channel_doctor.py` | Defer | tools/ or owning package script created by exact ready task | 4 | No script path is authorized until dependencies, tests, and rollback are defined. |
| `FILE-SCRIPT-006` | `scripts/check_document_freshness.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-004` | `scripts/generate_docs.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-005` | `scripts/generate_project_state.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-007` | `scripts/launch_browser_profile.sh` | Defer | tools/ or owning package script created by exact ready task | 6 | No script path is authorized until dependencies, tests, and rollback are defined. |
| `FILE-SCRIPT-008` | `scripts/run_fixture_e2e.sh` | Defer | tools/ or owning package script created by exact ready task | 6 | No script path is authorized until dependencies, tests, and rollback are defined. |
| `FILE-SCRIPT-002` | `scripts/validate_blueprint.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-003` | `scripts/validate_manifest.py` | Reject or redesign | MEOS/repository-specific tooling only if a ready task proves need | task-owned | Old deterministic-bootstrap tooling must not recreate the rejected manifest authority. |
| `FILE-SCRIPT-010` | `scripts/validate_source_bundle.py` | Defer | tools/ or owning package script created by exact ready task | 4 | No script path is authorized until dependencies, tests, and rollback are defined. |
| `FILE-TPL-005` | `templates/adr.md` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |
| `FILE-TPL-003` | `templates/agent.yaml` | Reject/generalize | MEOS roles or specific engine/connector contracts | — | Avoid universal agent template. |
| `FILE-TPL-004` | `templates/capability.yaml` | Defer | owning schema/example directory when capability activates | 2 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-011` | `templates/channel.yaml` | Defer | owning schema/example directory when capability activates | 4 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-015` | `templates/content-draft.md` | Defer | owning schema/example directory when capability activates | 5 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-013` | `templates/content-source.yaml` | Defer | owning schema/example directory when capability activates | 4 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-001` | `templates/document-frontmatter.yaml` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |
| `FILE-TPL-008` | `templates/evidence-manifest.json` | Defer | owning schema/example directory when capability activates | 1 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-007` | `templates/handoff.md` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |
| `FILE-TPL-010` | `templates/knowledge-record.yaml` | Defer | owning schema/example directory when capability activates | 4 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-009` | `templates/milestone.md` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |
| `FILE-TPL-012` | `templates/provider.yaml` | Defer | owning schema/example directory when capability activates | 4 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-014` | `templates/research-brief.md` | Defer | owning schema/example directory when capability activates | 5 | Template must be generated from or validated against an accepted schema. |
| `FILE-TPL-006` | `templates/verification-report.md` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |
| `FILE-TPL-002` | `templates/work-item.yaml` | Adopt/adapt | MEOS standards/templates or current task/ADR structures | 0–1 | Consolidate instead of maintaining parallel templates. |

**Record count:** 33
