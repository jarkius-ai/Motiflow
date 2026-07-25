# Documentation Quality Checklist

Use this checklist for authoritative documentation changes.

## Identity and Terminology

- [ ] Motiflow is used as the product and repository identity.
- [ ] ACDS is used only for product architecture.
- [ ] MEOS is used only for engineering governance and delivery.
- [ ] Creative Kernel and Workflow Orchestrator retain their canonical meanings.
- [ ] Any proposed terminology change references an ADR.

## Authority and Navigation

- [ ] The document has the correct authority level.
- [ ] It does not conflict with a higher-authority document.
- [ ] Onboarding links follow the canonical reading order.
- [ ] Superseded documents identify their successor.
- [ ] Historical material is clearly marked.

## Structure and Naming

- [ ] File and folder names follow repository conventions.
- [ ] No empty speculative directory is introduced.
- [ ] Package names represent one clear responsibility.
- [ ] Plural and singular naming are used consistently.
- [ ] Paths match the approved repository structure or are marked transitional.

## Links and References

- [ ] All relative links resolve.
- [ ] Referenced files exist with exact casing.
- [ ] Moved files include updated inbound references.
- [ ] External links are necessary and sufficiently stable.
- [ ] No stale branch-specific URL is presented as canonical.

## Architecture

- [ ] Responsibility boundaries are explicit.
- [ ] Dependency direction is respected.
- [ ] Engines, agents, critics, connectors, schemas, and workflows are not conflated.
- [ ] Human approval and evaluation gates are represented where required.
- [ ] Architecture-significant changes include an ADR.

## Implementation Readiness

- [ ] Requirements are testable.
- [ ] Inputs, outputs, errors, and stopping conditions are defined.
- [ ] Success criteria are measurable.
- [ ] Ownership or intended package location is identified.
- [ ] Open decisions are recorded instead of hidden in prose.

## Review Result

- [ ] Approved
- [ ] Approved with follow-up
- [ ] Changes required
