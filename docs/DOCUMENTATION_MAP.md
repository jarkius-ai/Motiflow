# Documentation Map

**Status:** Supporting transitional navigation summary

The authoritative navigation index is [`00-foundation/DOCUMENT_INDEX.md`](00-foundation/DOCUMENT_INDEX.md), and conflict resolution is controlled by [`00-foundation/DOCUMENT_AUTHORITY.md`](00-foundation/DOCUMENT_AUTHORITY.md). This map summarizes the current transitional layout only.

## Authority order

1. `PROJECT_CHARTER.md` — enduring human-facing vision, mission, and scope
2. `MASTER_CONTEXT.md` — consolidated operational context
3. `docs/adr/` — architecture decision records (proposed and accepted)
4. Current product, architecture, engineering, AI, and governance specifications
5. `docs/archive/` — historical source material only
6. Chat history and informal notes — non-authoritative inputs

When documents conflict, apply the Document Authority Standard rather than inferring authority from this summary.

## Current transitional structure

```text
docs/
├── 00-foundation/   # manifesto, philosophy, principles
├── 01-product/      # users, journeys, requirements, outcomes
├── 02-architecture/ # kernel, orchestrator, engines, contracts
├── 03-delivery/     # delivery planning, sequencing, readiness, and release controls
├── 04-ai/           # evaluation, memory, prompting, review
├── 05-governance/   # transitional contribution guidance
├── adr/             # architecture decision records
└── archive/         # superseded and imported historical material
```

`docs/VISION.md`, `docs/PRD.md`, `docs/ROADMAP.md`, and `docs/SYSTEM_DESIGN.md` remain active at their current paths until a focused migration updates all inbound links. The proposed target layout is defined in [`00-foundation/REPOSITORY_STRUCTURE.md`](00-foundation/REPOSITORY_STRUCTURE.md).

## Document status

Every substantial specification should identify one of these states:

- `Draft`
- `Proposed`
- `Accepted`
- `Superseded`
- `Archived`

## Change rule

Material changes to architecture, contracts, security boundaries, or product principles require an ADR or an explicit reference to an existing ADR. Documentation should be updated in the same change as the implementation it governs.
