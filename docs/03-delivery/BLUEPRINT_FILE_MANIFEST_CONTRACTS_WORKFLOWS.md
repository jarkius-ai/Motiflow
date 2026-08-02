# Blueprint Manifest Disposition — Contracts Workflows

- **Status:** Review-ready source-manifest reconciliation appendix
- **Owner:** Chief Architect and Documentation

This appendix is part of `BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`. It is a source-reconciliation record, not file-creation authority.

| ID | Original path | Disposition | Repository home or target | Phase | Rule |
|---|---|---|---|---:|---|
| `FILE-SCHEMA-017` | `contracts/acquisition-request.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for acquisition-request | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-018` | `contracts/acquisition-result.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for acquisition-result | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-007` | `contracts/agent.schema.json` | Reject/generalize | MEOS role/task contracts or specific runtime capability contracts | — | A universal agent schema would blur delivery roles, engines, and runtime agents. |
| `FILE-SCHEMA-010` | `contracts/approval.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for approval | 1 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-006` | `contracts/capability.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for capability | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-015` | `contracts/channel.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for channel | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-025` | `contracts/claim.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for claim | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-001` | `contracts/command.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for command | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-022` | `contracts/content-draft.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for content-draft | 5 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-019` | `contracts/content-source.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for content-source | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-024` | `contracts/credential-reference.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for credential-reference | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-003` | `contracts/event.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for event | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-004` | `contracts/evidence-manifest.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for evidence-manifest | 1 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-013` | `contracts/file-manifest.schema.json` | Reject immediate authority | MEOS task ownership + repository structure rules + this disposition record | — | Do not restore the 193-file manifest as a generation command. |
| `FILE-SCHEMA-014` | `contracts/knowledge-record.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for knowledge-record | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-009` | `contracts/policy.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for policy | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-011` | `contracts/project-state.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for project-state | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-023` | `contracts/provider-health.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for provider-health | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-016` | `contracts/provider.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for provider | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-027` | `contracts/publication-metric.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for publication-metric | 7 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-021` | `contracts/research-brief.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for research-brief | 5 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-002` | `contracts/result.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for result | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-026` | `contracts/source-bundle.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for source-bundle | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-020` | `contracts/source-citation.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for source-citation | 4 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-012` | `contracts/task-graph.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for task-graph | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-005` | `contracts/work-item.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for work-item | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-SCHEMA-008` | `contracts/workflow.schema.json` | Adapt/defer | packages/schemas/ or owning architecture contract for workflow | 1–2 | Schema is created only with accepted semantics, fixtures, validator, and consumer task. |
| `FILE-WF-001` | `workflows/browser-command-roundtrip.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 6 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-003` | `workflows/channel-doctor.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 4 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-002` | `workflows/fixture-social-draft.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 5 | Retain only as a bounded fixture/example; it is not an MVP product workflow. |
| `FILE-WF-007` | `workflows/post-publication-measurement.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 7 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-000` | `workflows/registry.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 2 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-004` | `workflows/research-to-draft.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 5 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-006` | `workflows/research-to-publish.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 5–6 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |
| `FILE-WF-005` | `workflows/source-verification.yaml` | Adapt/defer | packages/workflows/ or evaluations fixtures under the activated phase | 4–5 | Define as versioned workflow only after prerequisite contracts and product outcome are accepted. |

**Record count:** 35
