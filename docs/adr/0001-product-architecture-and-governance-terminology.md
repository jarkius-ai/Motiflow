# ADR-0001: Product, Architecture, and Governance Terminology

- **Status:** Proposed
- **Date:** 2026-07-25
- **Decision owners:** Motiflow maintainers

## Context

The repository has expanded across product design, architecture, engineering governance, prompts, workflows, and implementation planning. Several documents use Motiflow, ACDS, and MEOS at different abstraction levels. Without a fixed vocabulary, contributors and AI agents can interpret these names as competing products or interchangeable systems.

The repository also uses important component names such as Creative Kernel and Workflow Orchestrator. Casual renaming would create architectural drift and invalidate existing documentation.

## Decision

The repository adopts the following canonical meanings:

- **Motiflow** — the product, platform, and repository identity.
- **Autonomous Creative Direction System (ACDS)** — the product architecture underlying Motiflow.
- **Motiflow Engineering Operating System (MEOS)** — the engineering governance and delivery system used to build and maintain Motiflow.
- **Creative Kernel** — the canonical integrity, validation, provenance, policy, confidence, and versioning boundary.
- **Workflow Orchestrator** — the component responsible for planning and coordinating workflow execution across steps, engines, agents, connectors, evaluation gates, and human approvals.

The names are related as follows:

```text
Motiflow
├── product architecture: ACDS
└── engineering governance and delivery: MEOS
```

ACDS and MEOS are not alternative names for the product.

Architecture-significant terminology changes require a new ADR that explicitly supersedes this decision.

## Consequences

### Positive

- Onboarding becomes consistent.
- Documentation conflicts can be resolved using stable vocabulary.
- AI agents receive clearer role and dependency boundaries.
- Product, architecture, and delivery governance can evolve independently.

### Costs

- Existing documents must be aligned.
- Transitional references may need annotations.
- Contributors must avoid introducing informal substitute names for canonical components.

## Rejected Alternatives

### Use Motiflow, ACDS, and MEOS interchangeably

Rejected because it obscures whether a statement concerns the product, runtime architecture, or engineering process.

### Rename Creative Kernel immediately

Rejected because no demonstrated architectural need currently justifies the migration cost. A future ADR may propose a replacement with impact analysis.

### Put all governance inside MEOS

Rejected because product and architecture authority must remain visible outside the delivery methodology.

## Compliance

New or materially revised authoritative documents must follow this ADR. Deprecated terminology should be corrected or explicitly identified as historical.
