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

The number in `MEOS/20_PROJECT_BOOTSTRAP.md` is the document's MEOS topic
identifier, not its position in this onboarding list. Do not read the MEOS
directory numerically from `01` through `20`; use `CONTEXT_INDEX.yaml` to load
the minimum complete context for the task.

`START_HERE.md` is the navigation authority. It does not replace the governing content of the documents it routes to.

The current blocked-path control document is
[`docs/03-delivery/PENDING_WORK_TO_READY.md`](docs/03-delivery/PENDING_WORK_TO_READY.md).
Use it to order the pending validation, sign-off, and Task 001 readiness work.

The reusable agent operating model is
[`docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md`](docs/03-delivery/AUTONOMOUS_AGENT_TEAM_CHARTER.md).
Use it to assign AI work and preserve human decision boundaries.

The current documentation and planning quality result is
[`docs/03-delivery/DOCUMENTATION_AND_PLANNING_QUALITY_REVIEW.md`](docs/03-delivery/DOCUMENTATION_AND_PLANNING_QUALITY_REVIEW.md).
Keep that score separate from product and task implementation readiness.

## Current Execution Order

No implementation task is currently ready. Follow this sequence without skipping
the human-evidence and authority gates:

1. execute the prepared MVP validation protocol with intended users;
2. record the accountable product-owner `PROCEED`, `REVISE`, or `STOP` decision;
3. close C-01 through C-06 and accept, revise, or reject ADR-0003;
4. run the Definition of Ready and promote Task 001 only if every prerequisite passes;
5. implement the ten-artifact schema, fixture, validator, and CI contract proof; and
6. only after that proof is accepted, continue toward the creative-direction-first
   workflow with its two explicit human approval gates.

The product destination remains one end-to-end path from source material through
approved creative direction, one-provider generation, critic review, and final
approval. Publication-platform breadth, editorial authoring expansion,
multi-provider infrastructure, and publishing connectors remain parked until
that MVP proof is accepted.

If `CONTEXT_INDEX.yaml` or `MEOS/20_PROJECT_BOOTSTRAP.md` still route immediate work toward broad Model Gateway-first infrastructure, treat that as stale routing to reconcile rather than a reason to skip the creative-direction-first proof.

Keep the detailed contracts, task specs, and ADR decisions in their authoritative documents rather than duplicating them here.

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

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Follow the minimum task- and role-specific route defined in `CONTEXT_INDEX.yaml`. Treat validation evidence, product and architecture decisions, and Task 001 readiness as the current ordered path; do not jump to the eventual provider-backed workflow. Summarize the verified project state, identify assumptions or conflicts, and continue from the next approved priority without inventing requirements.

Do not treat previous chat memory as the source of truth. Repository artifacts, accepted decisions, current tasks, executable checks, and recorded evidence are authoritative.

## Conflict Handling

When documents conflict:

1. apply [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md);
2. prefer accepted ADRs for architecture-significant decisions;
3. distinguish current state from target state;
4. stop and escalate when the conflict cannot be resolved from authoritative repository evidence;
5. never silently select the most convenient interpretation.
