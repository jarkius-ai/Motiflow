# Start Here

This is the canonical entry point for every human contributor and AI agent working on Motiflow.

Motiflow is the product and repository identity. The Autonomous Creative Direction System (ACDS) is its product architecture. The Motiflow Engineering Operating System (MEOS) governs how the product is designed, implemented, verified, reviewed, and released.

## Foundation Reading Order

Read these documents in order:

1. [`PROJECT_CHARTER.md`](PROJECT_CHARTER.md) — product vision, mission, scope, principles, and strategic goals
2. [`MASTER_CONTEXT.md`](MASTER_CONTEXT.md) — stable system identity, architecture, boundaries, and shared context
3. [`CONTEXT_INDEX.yaml`](CONTEXT_INDEX.yaml) — machine-readable routing for the current task and role
4. [`MEOS/20_PROJECT_BOOTSTRAP.md`](MEOS/20_PROJECT_BOOTSTRAP.md) — current delivery state, engineering controls, and continuation procedure
5. task-specific product, architecture, engineering, AI, design, contract, ADR, and implementation documents selected by `CONTEXT_INDEX.yaml`

`START_HERE.md` is the navigation authority. It does not replace the governing content of the documents it routes to.

## Foundation Standards

Before changing authoritative documentation or repository structure, review:

- [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md)
- [`docs/00-foundation/TERMINOLOGY.md`](docs/00-foundation/TERMINOLOGY.md)
- [`docs/00-foundation/REPOSITORY_STRUCTURE.md`](docs/00-foundation/REPOSITORY_STRUCTURE.md)
- [`docs/00-foundation/MIGRATION_PLAN.md`](docs/00-foundation/MIGRATION_PLAN.md)
- [`docs/00-foundation/DOCUMENTATION_QUALITY_CHECKLIST.md`](docs/00-foundation/DOCUMENTATION_QUALITY_CHECKLIST.md)

Architecture-significant terminology changes must follow the ADR process and explicitly supersede existing decisions.

## For a New AI Chat or Agent Session

Use this instruction:

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Follow the minimum task- and role-specific route defined in `CONTEXT_INDEX.yaml`. Summarize the verified project state, identify assumptions or conflicts, and continue from the next approved priority without inventing requirements.

Do not treat previous chat memory as the source of truth. Repository artifacts, accepted decisions, current tasks, executable checks, and recorded evidence are authoritative.

## Conflict Handling

When documents conflict:

1. apply [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md);
2. prefer accepted ADRs for architecture-significant decisions;
3. distinguish current state from target state;
4. stop and escalate when the conflict cannot be resolved from authoritative repository evidence;
5. never silently select the most convenient interpretation.
