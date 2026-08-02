# Blueprint File Manifest Disposition

- **Status:** Review-ready source-manifest reconciliation
- **Owner:** Chief Architect and Documentation
- **Source:** External `PROJECT_BLUEPRINT.md` v0.5.0-review embedded manifest v1.2.0
- **Source SHA-256:** `da8e88c5c384ff63c5f4ef76f67cd8ee83ee73e1a778c1b4c7a349f8fd06a366`
- **Source declared files:** 193

## Purpose

This document disposes every fixed path declared by the separately authored v0.5.0 blueprint. The detailed 193-record mapping is split into linked appendices for reviewability. These records preserve source intent but do not authorize file creation or mass repository bootstrap.

## Summary

| Disposition | Count |
|---|---:|
| Adapt | 5 |
| Adapt/defer | 70 |
| Adapt/renumber | 8 |
| Adopt existing | 17 |
| Adopt/adapt | 33 |
| Adopt/adjust | 1 |
| Archive/reference | 3 |
| Defer | 26 |
| Defer/adapt | 11 |
| Reject | 1 |
| Reject duplicate | 6 |
| Reject immediate authority | 2 |
| Reject or redesign | 6 |
| Reject/generalize | 2 |
| Reject/reframe | 1 |
| Verify/adopt | 1 |
| **Total** | **193** |

## Detailed appendices

- [`BLUEPRINT_FILE_MANIFEST_ROOT_AGENTS_CAPABILITIES.md`](BLUEPRINT_FILE_MANIFEST_ROOT_AGENTS_CAPABILITIES.md)
- [`BLUEPRINT_FILE_MANIFEST_CHANNELS_PROVIDERS_POLICIES.md`](BLUEPRINT_FILE_MANIFEST_CHANNELS_PROVIDERS_POLICIES.md)
- [`BLUEPRINT_FILE_MANIFEST_CONTRACTS_WORKFLOWS.md`](BLUEPRINT_FILE_MANIFEST_CONTRACTS_WORKFLOWS.md)
- [`BLUEPRINT_FILE_MANIFEST_DOCUMENTS.md`](BLUEPRINT_FILE_MANIFEST_DOCUMENTS.md)
- [`BLUEPRINT_FILE_MANIFEST_PLANNING_SCRIPTS_TEMPLATES.md`](BLUEPRINT_FILE_MANIFEST_PLANNING_SCRIPTS_TEMPLATES.md)

## Decision

The embedded v0.5.0 manifest is historical design inventory only. It is not copied to `planning/FILE_MANIFEST.yaml`, is not a current path allow-list, and does not authorize repository bootstrap. New paths require accepted contracts, MEOS readiness, and exact ready-task ownership.

## Verification

- [x] All 193 source file records have exactly one disposition across the appendices.
- [x] Legacy ADR numbers are not reused.
- [x] Delivery roles are not duplicated as runtime-agent files.
- [x] Phase 4–8 capabilities remain deferred.
- [ ] Independent architecture/documentation review confirms the mappings.
- [ ] Human decision on ADR-0004 confirms or revises the authority model.
