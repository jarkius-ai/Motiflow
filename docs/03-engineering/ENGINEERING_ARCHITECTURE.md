# Engineering Architecture Baseline

## Initial stack direction

- Backend: Laravel 11+ on PHP 8.3 or later
- Frontend: React with TypeScript and Inertia.js
- Database: PostgreSQL
- Cache and queues: Redis
- Object storage: S3-compatible storage
- Realtime updates: WebSockets or server-sent events
- Deployment: containerized services with environment-specific infrastructure definitions

The stack is a starting direction, not an irreversible constraint. Architecture decisions should be recorded before major deviations.

## Bounded modules

- Identity and Workspaces
- Projects and Briefs
- Creative Kernel
- Workflow Definitions
- Workflow Runtime
- Engine Registry
- Provider Gateway
- Reviews and Approvals
- Assets and Provenance
- Knowledge and Connectors
- Evaluation and Analytics
- Administration and Governance

## Engineering rules

- Domain logic must not depend directly on provider SDKs.
- Long-running work executes through durable queued jobs.
- Every external call has timeout, retry, idempotency, and observability behavior.
- State transitions are explicit and auditable.
- API and event contracts are versioned.
- Secrets never enter prompts or persisted artifacts.
- Tests cover contracts, workflow transitions, invalidation, authorization, and provider failure modes.

## Repository evolution

```text
apps/
  studio/
  api/
packages/
  creative-kernel/
  orchestrator/
  engine-sdk/
  connector-sdk/
  ui/
schemas/
infrastructure/
tests/
```

The first implementation milestone should prove one complete workflow before expanding into a broad engine ecosystem.
