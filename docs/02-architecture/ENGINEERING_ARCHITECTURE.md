# Engineering Architecture Baseline

**Status:** Supporting engineering specification
**Owner:** Engineering and Chief Architect
**Scope:** Initial implementation stack, bounded modules, and engineering architecture direction

This document sets engineering direction and repository boundaries. Review-ready delivery plans may propose sequencing, but they do not override human-accepted architecture decisions until explicitly approved.

## Initial stack direction

- Backend application: Python 3.12+ with FastAPI as the application-layer
  direction, per
  [`ADR-0005`](../adr/ADR-0005-python-backend-and-react-typescript-stack.md);
  record exact framework and runtime versions at implementation freeze
- Frontend: React with TypeScript
- Database: PostgreSQL
- Cache and queues: Redis
- Object storage: S3-compatible storage
- Realtime updates: WebSockets or server-sent events
- Deployment: containerized services with environment-specific infrastructure definitions

The stack is a starting direction, not an irreversible constraint. Architecture decisions should be recorded before major deviations.

Task 001's contract validator is not the backend application. Its approved
toolchain is a plain Python 3.12+ CLI entrypoint using `jsonschema` (>=4.21,
2020-12 dialect) pinned in a committed lockfile; it must not bootstrap the
application framework or add framework dependencies. See
[`ADR-0005`](../adr/ADR-0005-python-backend-and-react-typescript-stack.md) and
the C-06 record in
[`DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`](DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md).

## Bounded modules

- Identity and Workspaces
- Projects and Briefs
- Creative Kernel
- Workflow Definitions
- Workflow Runtime
- Engine Registry
- Model Gateway
- Reviews and Approvals
- Assets and Provenance
- Knowledge and Connectors
- Critics and Evaluation
- Administration and Governance

## Engineering rules

- Domain logic must not depend directly on provider SDKs.
- Long-running work executes through durable queued jobs.
- Every external call has timeout, retry, idempotency, and observability behavior.
- State transitions are explicit and auditable.
- API and event contracts are versioned.
- Secrets never enter prompts or persisted artifacts.
- Tests cover contracts, workflow transitions, invalidation, authorization, and provider failure modes.
- The first executable slice must preserve two explicit human gates: direction approval before generation and final-candidate approval after critique.

## Repository evolution

The target implementation layout follows [`docs/00-foundation/REPOSITORY_STRUCTURE.md`](../00-foundation/REPOSITORY_STRUCTURE.md). It is a target-state reference, not a statement that every directory already exists today.

```text
apps/
  studio/
  api/
  worker/
packages/
  creative-kernel/
  orchestrator/
  engines/
  critics/
  connectors/
  schemas/
  workflows/
  engine-sdk/
  connector-sdk/
  shared/
knowledge/
prompts/
evaluations/
infrastructure/
tools/
examples/
diagrams/
```

The first implementation milestone should prove one complete creative-direction workflow before expanding into a broad engine ecosystem.

Early implementation must align with the canonical `packages/*` boundaries shown above. Do not create a `packages/ai/` subtree. For the first slice, schemas belong in `packages/schemas/`, workflow definitions in `packages/workflows/`, provider-facing gateway code in `packages/connectors/`, critics in `packages/critics/`, and cross-cutting validation/provenance utilities only where justified in `packages/shared/`.
