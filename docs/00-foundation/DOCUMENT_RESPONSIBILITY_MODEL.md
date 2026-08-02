# Motiflow Document Responsibility Model

- **Status:** Accepted governance model
- **Owner:** Product Owner, Chief Architect, Documentation
- **Decision:** ADR-0006
- **Purpose:** Assign one canonical owner to each class of project information

## Core rule

Every durable fact, decision, plan, task, and evidence record must have one canonical owner. Other documents may summarize or link to it, but must not maintain a second authoritative copy.

## Responsibility map

| Question | Canonical owner | Content it owns | Content it must not own |
|---|---|---|---|
| Why does Motiflow exist? | `PROJECT_CHARTER.md` | Vision, mission, problem, product principles, durable scope, success | Detailed architecture, phases, tasks, current state |
| What is Motiflow and how is its stable runtime shaped? | `MASTER_CONTEXT.md` | ACDS identity, components, canonical creative spine, ownership, dependency direction, architecture principles | Roadmap, task status, provider installation, evidence |
| What can the complete future platform become? | `docs/02-architecture/TARGET_PLATFORM_BLUEPRINT.md` | Capability domains, component responsibilities, architectural constraints, trust boundaries, expansion seams | Current state, phases, tasks, CI, exact tests, vendor commitment |
| What exists today? | `docs/02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md` | Implemented, validated, contracted, review-ready, planned, deferred, experimental, rejected states | Product vision or implementation instructions |
| How does the product expand? | `docs/03-delivery/CAPABILITY_EXPANSION_ROADMAP.md` | Phase order, outcomes, dependencies, activation and exit gates, expansion seams | Task authorization or implementation evidence |
| How was the external blueprint reconciled? | Reconciliation matrix, review, and manifest disposition records | Adopt/adapt/defer/reject decisions and source traceability | Current implementation claims |
| Why was a consequential architecture choice made? | Accepted ADR | Context, options, decision, consequences, migration, approval | Ongoing task execution details |
| How is work built and verified? | MEOS | Roles, readiness, quality gates, review, release, evidence discipline | Product features and future platform scope |
| What should be built now? | Ready task specification | Objective, scope, acceptance criteria, references, deliverables, verification | Unapproved future work |
| What is actually true? | Code, tests, reports, commits, and other evidence | Observed implementation and verification results | Aspirational or inferred claims |
| Where should a contributor begin? | `START_HERE.md` and `CONTEXT_INDEX.yaml` | Navigation and minimum-complete-context routing | Duplicated product or architecture specifications |
| What is the current delivery position? | `MEOS/20_PROJECT_BOOTSTRAP.md` | Current milestone, blockers, next approved priority, verified status | Future platform design |

## Duplication policy

A non-owner document may include:

- a one-sentence summary;
- a stable identifier;
- a link to the canonical owner;
- consequences relevant to its own responsibility.

It must not copy detailed tables, status, phase logic, acceptance criteria, provider decisions, or task instructions that another document owns.

## Move-not-delete rule

When a document contains content outside its responsibility:

1. Identify the canonical owner.
2. Confirm whether the owner already contains the information.
3. Move or merge unique information into the owner.
4. Preserve source traceability when historically important.
5. Replace the old content with a concise statement and link.
6. Validate that no conflicting authoritative copy remains.

Information is removed only when it is:

- duplicated without additional value;
- contradicted by a newer accepted authority;
- obsolete and preserved in Git history or an explicit archive;
- rejected through a recorded decision.

## Status vocabulary

Use these terms consistently:

- **Accepted** — authorized human decision exists.
- **Implemented** — runtime or repository behavior exists with evidence.
- **Validated** — product or operational evidence supports the outcome.
- **Contracted** — accepted normative contract exists.
- **Review-ready** — coherent proposal exists; required acceptance is pending.
- **Planned** — assigned to a future phase; not activated.
- **Deferred** — intentionally postponed until a trigger occurs.
- **Experimental** — isolated research without production authority.
- **Rejected** — explicitly excluded.
- **Blocked** — a required dependency or decision prevents progress.

`Documented`, `designed`, and `scored` are not substitutes for implementation or validation state.

## AI-agent rule

An AI agent must:

1. Begin at `START_HERE.md`.
2. Load only the minimum complete context routed by `CONTEXT_INDEX.yaml`.
3. Identify the canonical owner for each statement it intends to change.
4. Update the owner and affected references in the same change.
5. Stop when authorities conflict or required acceptance is missing.
6. Never infer implementation from the Charter, Master Context, Blueprint, Roadmap, or a proposal.

## Change control

Changes to this responsibility model require an ADR when they:

- move canonical ownership between major documents;
- add or remove an authority layer;
- change precedence or conflict handling;
- permit a planning document to authorize implementation;
- change how human acceptance is recorded.

## Related documents

- `../../START_HERE.md`
- `../../PROJECT_CHARTER.md`
- `../../MASTER_CONTEXT.md`
- `../../CONTEXT_INDEX.yaml`
- `../02-architecture/TARGET_PLATFORM_BLUEPRINT.md`
- `../02-architecture/TARGET_PLATFORM_CAPABILITY_MAP.md`
- `../03-delivery/CAPABILITY_EXPANSION_ROADMAP.md`
- `../adr/ADR-0006-target-blueprint-and-phased-expansion.md`
- `../../MEOS/20_PROJECT_BOOTSTRAP.md`
