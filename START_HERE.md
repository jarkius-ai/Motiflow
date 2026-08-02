# Start Here

This is the canonical entry point for every human contributor and AI agent working on Motiflow.

## One-screen orientation

| Term or document | Responsibility | Implementation authority |
|---|---|---|
| **Motiflow** | Customer-facing product and future platform for governed enterprise creative intelligence | Product identity only |
| **ACDS** | Stable product/runtime architecture | No; contracts, decisions, and ready tasks are required |
| **MEOS** | Engineering readiness, roles, execution, verification, review, and release | Governs work; does not define product scope |
| **ADR** | Durable consequential architecture decision | Only when accepted by authorized humans |
| **Project Charter** | Why Motiflow exists and its durable scope | No |
| **Master Context** | What Motiflow is and its stable architecture | No |
| **Target Platform Blueprint** | Complete future destination and expansion seams | No; target-state direction only |
| **Capability Map** | Evidence-based current state of every capability | No; records state |
| **Expansion Roadmap** | Phase order and activation gates | No; phases still need ready tasks |
| **MEOS task** | Bounded work authorized now | Yes, only after Definition of Ready passes |
| **Evidence** | What actually exists and works | Source of implementation truth |

The documentation responsibility model is defined in [`docs/00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md`](docs/00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md). Architecture-significant changes use [`docs/00-foundation/ARCHITECTURE_CHANGE_GATE.md`](docs/00-foundation/ARCHITECTURE_CHANGE_GATE.md).

## Product direction

The first product is the governed creative-direction MVP defined by [`PROJECT_CHARTER.md`](PROJECT_CHARTER.md). Its canonical artifact spine and stable runtime boundaries are defined by [`MASTER_CONTEXT.md`](MASTER_CONTEXT.md).

Later acquisition, Agent Reach, editorial, publication, browser, publishing, measurement, and enterprise capabilities are governed by the Target Platform Blueprint, Capability Map, and Expansion Roadmap. Their presence in architecture documentation does not mean they are active.

For the evidence-based status of any capability—including Agent Reach, browser providers, and proxy infrastructure—use [`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md).

## Foundation reading order

Read these documents in order:

1. [`PROJECT_CHARTER.md`](PROJECT_CHARTER.md) — product purpose, durable scope, and value.
2. [`MASTER_CONTEXT.md`](MASTER_CONTEXT.md) — stable ACDS architecture, components, and canonical creative spine.
3. [`CONTEXT_INDEX.yaml`](CONTEXT_INDEX.yaml) — machine-readable task and role routing.
4. [`MEOS/20_PROJECT_BOOTSTRAP.md`](MEOS/20_PROJECT_BOOTSTRAP.md) — verified current delivery state and next approved work.
5. Task-specific product, architecture, contract, ADR, implementation, and evidence files selected by `CONTEXT_INDEX.yaml`.

Do not read the entire repository by default. Load the minimum complete context for the assigned role and task.

## Future-platform planning route

Only for target-capability planning, architecture expansion, reconciliation, or phase activation, load the applicable subset of:

- [`docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`](docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md)
- [`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md)
- [`docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`](docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md)
- [`docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`](docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md)
- [`docs/03-delivery/BLUEPRINT_RECONCILIATION_REVIEW.md`](docs/03-delivery/BLUEPRINT_RECONCILIATION_REVIEW.md)
- [`docs/03-delivery/DOCUMENT_RESPONSIBILITY_MIGRATION_REPORT.md`](docs/03-delivery/DOCUMENT_RESPONSIBILITY_MIGRATION_REPORT.md)
- [`docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md)

ADR-0004 records the accepted direction. It does not authorize any roadmap phase or implementation task.

## Current execution order

No implementation task is currently ready. Follow this sequence:

1. Execute the MVP validation protocol with intended users.
2. Record the Product Owner `PROCEED`, `REVISE`, or `STOP` decision.
3. Resolve C-01 through C-06 and accept, revise, or reject ADR-0003.
4. Run Definition of Ready for Task 001.
5. Implement the ten-artifact contract proof only when Task 001 is `READY`.
6. Continue to the executable creative core only after Phase 1 evidence is accepted.

The accepted target direction does not change the current readiness score or blocked Task 001 path. Current values and blockers are owned by [`MEOS/20_PROJECT_BOOTSTRAP.md`](MEOS/20_PROJECT_BOOTSTRAP.md) and the Capability Map.

## For a new AI session

Use this instruction:

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Follow the minimum task- and role-specific route. Identify the canonical owner for every fact you intend to change. Distinguish accepted direction, current state, authorized work, and verified evidence. Load target-platform documents only when the task concerns future capability planning or activation. Stop on conflicts or missing authority and do not invent requirements.

Previous chat memory, a loose blueprint copy, and external planning documents are not repository authority.

## Conflict handling

When documents conflict:

1. Apply [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md).
2. Apply the [`Document Responsibility Model`](docs/00-foundation/DOCUMENT_RESPONSIBILITY_MODEL.md).
3. Prefer accepted ADRs for consequential architecture decisions.
4. Distinguish target direction from current state and implementation truth.
5. Stop and escalate when repository evidence cannot resolve the conflict.
6. Never choose the most convenient interpretation silently.
