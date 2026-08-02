# Document Responsibility Migration Report

- **Status:** Completed refactor record
- **Date:** 2026-08-02
- **Owner:** Product Owner, Chief Architect, Documentation
- **Decision:** ADR-0004
- **Branch:** `agent/reconcile-target-blueprint`

## Purpose

Record how information from the separately authored v0.5.0 blueprint and overlapping repository documents was assigned to one canonical owner without discarding useful design knowledge.

## Result

The repository now uses this mental model:

```text
Project Charter        = WHY
Master Context         = WHAT and stable architecture
Target Blueprint       = FUTURE DESTINATION
Capability Map         = CURRENT STATE
Expansion Roadmap      = JOURNEY AND PHASES
ADRs                    = CONSEQUENTIAL DECISIONS
MEOS                    = HOW WORK IS BUILT AND VERIFIED
Task                    = WHAT IS AUTHORIZED NOW
Evidence                = WHAT IS ACTUALLY TRUE
```

## Major migrations

| Information class | Previous location or overlap | Canonical owner after refactor | Treatment |
|---|---|---|---|
| Product vision and durable value | Charter, Master Context, external blueprint | `PROJECT_CHARTER.md` | Consolidated and linked |
| Stable ACDS identity and component boundaries | Master Context, system design, external blueprint | `MASTER_CONTEXT.md` and accepted ADRs | Consolidated as stable context |
| Complete future capability domains | External blueprint and target planning | `TARGET_PLATFORM_BLUEPRINT.md` | Preserved as destination architecture |
| Delivery phases and activation gates | External blueprint and roadmap | `CAPABILITY_EXPANSION_ROADMAP.md` | Detailed phase ownership retained in roadmap; removed from blueprint |
| Current implementation and capability status | Blueprint prose, planning, bootstrap | `TARGET_PLATFORM_CAPABILITY_MAP.md`, `MEOS/20_PROJECT_BOOTSTRAP.md`, evidence | Removed from blueprint authority |
| Readiness, quality, reviewer roles, release | External blueprint and MEOS | MEOS | Blueprint references MEOS rather than duplicating it |
| Task-level implementation instructions | External blueprint and delivery plans | `MEOS/tasks/` | Retained only when a ready task owns the work |
| CI, validators, and exact test commands | External blueprint and Task 001 | Task and engineering evidence | Removed from target architecture |
| Repository file manifest | External v0.5.0 manifest | Manifest disposition records | Preserved as historical design inventory, not bootstrap authority |
| Agent Reach | External blueprint | Target Blueprint provider-neutral acquisition seam, Capability Map, Roadmap Phase 4 | Adapted as deferred optional adapter |
| Browser technologies | External blueprint | Target Blueprint provider-neutral browser seam, Capability Map, Roadmap Phase 6 | Deferred; no provider selected |
| Proxy behavior | External blueprint risk/fallback discussion | ADR-0004, Blueprint security constraints, Architecture Change Gate | Not required or authorized; future use requires separate decision |
| Publication Package | Existing publication contract and external blueprint | Architecture contract and Roadmap Phase 5 | Preserved as post-MVP specialization |
| Publishing authorization | External blueprint and publication planning | Target architecture seam and Roadmap Phase 6 | Separated from final creative approval |
| Measurement and learning | External blueprint | Target Blueprint domain and Roadmap Phase 7 | Preserved as governed future capability |

## Content intentionally not duplicated

The following details no longer belong in the Target Platform Blueprint:

- phase numbers and phase exit criteria;
- current blocked or ready status;
- Task 001 instructions;
- validator command names;
- CI implementation details;
- exact test fixture plans;
- repository path allow-lists;
- provider installation steps;
- sprint or milestone commitments;
- release authorization.

These details remain available in the Roadmap, Capability Map, MEOS, tasks, engineering documents, manifest disposition records, and evidence.

## Information retained from the external blueprint

The following source contributions remain represented:

- complete acquisition, browser, content, publication, publishing, measurement, and enterprise capability vision;
- provider and channel registry concepts, adapted to Connector Gateway contracts;
- Agent Reach integration boundary;
- normalized source, citation, rights, provenance, and health concepts;
- research-to-content and publication-package relationships;
- security separation between research and publishing credentials;
- browser and authenticated-access risk boundaries;
- future connector, engine, and capability extensibility;
- all 193 fixed manifest path dispositions;
- all 39 reserved directory and 5 dynamic path-class reviews.

## Canonical documents updated or added

### Updated

- `PROJECT_CHARTER.md`
- `MASTER_CONTEXT.md`
- `START_HERE.md`
- `CONTEXT_INDEX.yaml`
- `MEOS/20_PROJECT_BOOTSTRAP.md`
- `docs/00-foundation/DOCUMENT_INDEX.md`
- `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- `docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- `docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`
- `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- `docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`

### Added

- `docs/00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md`
- `docs/00-foundation/ARCHITECTURE_CHANGE_GATE.md`
- `docs/03-delivery/BLUEPRINT_RECONCILIATION_REVIEW.md`
- `docs/03-delivery/BLUEPRINT_RECONCILIATION_VALIDATION.md`
- `docs/03-delivery/BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`
- five manifest disposition appendices;
- this migration report.

## Acceptance record

Jarkius accepted the product-to-platform direction and documentation responsibility model on 2026-08-02.

ADR-0004 is accepted for direction. Independent Reviewer and QA evidence remain required before PR #7 should be marked ready to merge under current MEOS controls.

## Unchanged blockers

This refactor does not change:

- product validation requirements;
- ADR-0003 status;
- decisive-slice contract acceptance;
- Task 001 readiness;
- runtime implementation status;
- Agent Reach, browser, publishing, or proxy activation status.

## Validation checklist

- [x] One canonical owner assigned to each major information class.
- [x] Target Blueprint reduced to destination architecture.
- [x] Phase details retained in the Expansion Roadmap.
- [x] Current-state truth retained in Capability Map, Bootstrap, and evidence.
- [x] MEOS remains the only engineering governance system.
- [x] External provider examples remain non-binding.
- [x] Original blueprint manifest retained through explicit dispositions.
- [x] Human `ACCEPT DIRECTION` recorded in ADR-0004.
- [ ] Independent architecture review completed.
- [ ] Independent QA/link verification completed.
