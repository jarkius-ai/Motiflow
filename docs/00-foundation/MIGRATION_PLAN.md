# Motiflow Repository Migration Plan

**Status:** Proposed  
**Target branch:** `agent/repository-alignment-foundation`

## Purpose

Move Motiflow from an organically expanded repository into a coherent, AI-navigable product and engineering system without breaking active work or obscuring history.

## Governing Identity

- **Motiflow** is the product and repository identity.
- **ACDS (Autonomous Creative Direction System)** is the product architecture.
- **MEOS (Motiflow Engineering Operating System)** is the engineering governance and delivery system.
- **Creative Kernel** remains the canonical kernel name unless superseded by an accepted ADR.
- **Workflow Orchestrator** coordinates workflow execution; it does not absorb kernel, engine, connector, or evaluation responsibilities.

## Migration Principles

1. Establish documentation authority before moving files.
2. Do not delete existing files until references and successors are verified.
3. Perform renames and moves through focused pull requests.
4. Require ADRs for architecture-significant changes.
5. Treat aliases as temporary and identify their canonical successor.
6. Do not create empty speculative folders merely to imply completeness.
7. Leave the default branch understandable and usable after every phase.

## Target Repository Structure

```text
Motiflow/
├── apps/
├── packages/
│   ├── core/
│   ├── orchestrator/
│   ├── engines/
│   ├── agents/
│   ├── evaluation/
│   ├── connectors/
│   ├── sdk/
│   └── shared/
├── schemas/
├── workflows/
├── prompts/
├── knowledge/
├── docs/
├── infrastructure/
├── tools/
├── examples/
└── tests/
```

This is a target state. Directories should be introduced only when they contain implemented or intentionally governed artifacts.

## Phase 1 — Foundation Alignment

Deliverables:

- establish document authority;
- freeze terminology;
- define repository structure;
- align the root reading order;
- add the first terminology ADR;
- document migration sequencing;
- open a draft PR without moving or deleting files.

Canonical reading order:

1. `START_HERE.md`
2. `PROJECT_CHARTER.md`
3. `MASTER_CONTEXT.md`
4. `CONTEXT_INDEX.yaml`
5. `MEOS/20_PROJECT_BOOTSTRAP.md`
6. task-specific architecture, product, workflow, or implementation documents

Exit criteria:

- root documents use the same product, architecture, and governance vocabulary;
- no root document presents a conflicting onboarding sequence;
- all referenced canonical files exist;
- proposed structural changes are documented but not yet executed.

## Phase 2 — Documentation Normalization

Actions:

- classify documents as authoritative, supporting, operational, historical, or generated;
- consolidate overlapping documents;
- repair broken and stale links;
- create a glossary and architecture dependency map;
- move historical content into an explicit archive area;
- add transition notes where paths may be externally referenced.

Exit criteria:

- one canonical document exists for each major concern;
- duplicate documents identify their successor or are archived;
- no orphaned authoritative document remains;
- terminology and link checks pass.

## Phase 3 — Structural Migration

Actions:

- introduce canonical folders only when they contain real files;
- move packages into approved namespaces;
- normalize connector, engine, agent, and evaluation boundaries;
- centralize schemas and workflow definitions;
- update imports, links, scripts, and CI references with each move.

Exit criteria:

- repository layout matches the approved standard;
- dependency direction is preserved;
- builds and tests remain green;
- no obsolete path is referenced by active documentation or automation.

## Phase 4 — Quality Gates

Introduce automated checks for:

- Markdown links;
- YAML validity;
- forbidden or deprecated terminology;
- duplicate authoritative titles;
- orphaned documents;
- ADR numbering and status;
- schema validation;
- architecture dependency violations.

## Phase 5 — Implementation Readiness

Prioritize implementation-ready slices:

1. canonical workflow schema;
2. Creative Kernel validation boundary;
3. Workflow Orchestrator execution contract;
4. engine and connector interfaces;
5. evaluation and verification gates;
6. first end-to-end workflow with human approval.

## Pull-Request Strategy

- **PR 1:** Foundation and terminology.
- **PR 2:** Documentation normalization.
- **PR 3+:** Small structural moves by concern.
- **Later PRs:** Runtime and product implementation.

Avoid combining broad renames, architecture redesign, and implementation in one pull request.

## Rollback

Every migration PR must be independently revertible. Do not remove compatibility notes, aliases, or archived predecessors until the successor has been present on the default branch and all references have been verified.
