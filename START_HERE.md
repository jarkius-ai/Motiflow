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

## Target Platform Planning

For work about the complete future platform, phased expansion, Agent Reach, acquisition, editorial, publication, publishing, measurement, or enterprise capabilities, let `CONTEXT_INDEX.yaml` route the applicable subset of:

- [`docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md`](docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md) — target-state capability architecture;
- [`docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`](docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md) — explicit current and future capability states;
- [`docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md`](docs/03-delivery/BLUEPRINT_RECONCILIATION_MATRIX.md) — adopt, adapt, defer, and reject mapping;
- [`docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`](docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md) — connected phases and activation gates; and
- [`docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md`](docs/adr/ADR-0004-TARGET-BLUEPRINT-AND-PHASED-EXPANSION.md) — proposed authority and phased-expansion decision.

These files preserve the complete vision but do not replace current product authority or authorize implementation. Work from the repository clone; do not maintain a separate loose blueprint as a competing workspace.

## Current Execution Order

No implementation task is currently ready. Follow this sequence without skipping
the human-evidence and authority gates:

1. review ADR-0004 and the target-platform reconciliation as planning only;
2. execute the prepared MVP validation protocol with intended users;
3. record the accountable product-owner `PROCEED`, `REVISE`, or `STOP` decision;
4. close C-01 through C-06 and accept, revise, or reject ADR-0003;
5. run the Definition of Ready and promote Task 001 only if every prerequisite passes;
6. implement the ten-artifact schema, fixture, validator, and CI contract proof; and
7. only after that proof is accepted, continue toward the creative-direction-first workflow with its two explicit human approval gates.

The product destination remains one end-to-end path from source material through
approved creative direction, one-provider generation, critic review, and final
approval. Publication-platform breadth, editorial authoring expansion,
multi-provider infrastructure, acquisition providers, and publishing connectors
remain parked until their preceding phases and activation gates pass.

If `CONTEXT_INDEX.yaml` or `MEOS/20_PROJECT_BOOTSTRAP.md` route immediate work toward broad infrastructure before the creative-direction proof, treat that as stale routing to reconcile rather than a reason to skip the validated sequence.

Keep detailed contracts, target capabilities, task specs, ADR decisions, and evidence in their authoritative documents rather than duplicating them here.

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

> Read `START_HERE.md`, then `PROJECT_CHARTER.md`, `MASTER_CONTEXT.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md`. Follow the minimum task- and role-specific route defined in `CONTEXT_INDEX.yaml`. Treat validation evidence, product and architecture decisions, and Task 001 readiness as the current ordered path. Load the target-platform blueprint and phase documents only when the task concerns future capability planning or activation. Summarize the verified project state, distinguish current from target state, identify assumptions or conflicts, and continue from the next approved priority without inventing requirements.

Do not treat previous chat memory, a loose blueprint copy, or an external planning document as the source of truth. Repository artifacts, accepted decisions, current tasks, executable checks, and recorded evidence are authoritative.

## Conflict Handling

When documents conflict:

1. apply [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md);
2. prefer accepted ADRs for architecture-significant decisions;
3. distinguish current state from target state;
4. treat the target blueprint as subordinate to accepted product and architecture authority;
5. stop and escalate when the conflict cannot be resolved from authoritative repository evidence; and
6. never silently select the most convenient interpretation.
