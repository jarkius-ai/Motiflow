# Documentation Map

This file explains where Motiflow knowledge belongs and which documents are authoritative.

## Authority order

1. `PROJECT_CHARTER.md` — enduring human-facing vision, mission, and scope
2. `MASTER_CONTEXT.md` — consolidated operational context
3. `docs/adr/` — approved architectural decisions
4. Current product, architecture, engineering, AI, and governance specifications
5. `docs/archive/` — historical source material only
6. Chat history and informal notes — non-authoritative inputs

When documents conflict, the higher authority wins unless a newer ADR explicitly changes the decision.

## Structure

```text
docs/
├── 00-foundation/   # manifesto, philosophy, principles
├── 01-product/      # users, journeys, requirements, outcomes
├── 02-architecture/ # kernel, orchestrator, engines, contracts
├── 03-engineering/  # implementation architecture and standards
├── 04-ai/           # evaluation, memory, prompting, review
├── 05-governance/   # contribution, security, decisions, releases
├── adr/             # architecture decision records
└── archive/         # superseded and imported historical material
```

## Document status

Every substantial specification should identify one of these states:

- `Draft`
- `Proposed`
- `Accepted`
- `Superseded`
- `Archived`

## Change rule

Material changes to architecture, contracts, security boundaries, or product principles require an ADR or an explicit reference to an existing ADR. Documentation should be updated in the same change as the implementation it governs.
