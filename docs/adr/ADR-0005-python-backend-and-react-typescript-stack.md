# ADR-0005: Python Backend and React/TypeScript Frontend Stack

- Status: Accepted
- Date: 2026-07-26
- Decision owners: Jarkius (Product owner, Chief Architect, Engineering lead)
- Related task: `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`
- Supersedes: the Laravel/PHP backend direction previously stated in
  `MASTER_CONTEXT.md`, `docs/SYSTEM_DESIGN.md`, and
  `docs/02-architecture/ENGINEERING_ARCHITECTURE.md`
- Superseded by: None

## Context

Foundation documents carried a Laravel (PHP) backend with a React/TypeScript
frontend as the initial stack direction. That direction predated an explicit
product-owner discussion of the technology stack. On 2026-07-26 the accountable
owner reopened the decision before any implementation existed, so no code
migration is required.

Motiflow's core value is automated creative generation: orchestrated
generation pipelines, critic evaluation, provider-neutral model access, and
evaluation instrumentation. The stack decision therefore weighs the AI
ecosystem depth of the backend runtime more heavily than framework
batteries or single-language uniformity.

## Decision Drivers

- Depth and maturity of AI/ML tooling: provider SDKs, evaluation frameworks,
  structured-output tooling, and critic/eval libraries are strongest in Python.
- The decisive slice and roadmap phases 5–8 are generation- and
  evaluation-centric, not CRUD-centric.
- A single builder currently holds all roles; minimizing runtime count until
  the contract proof completes reduces avoidable surface area.
- The frontend direction (React with TypeScript) is unaffected and remains.
- Task 001 requires a JSON Schema 2020-12 validator toolchain consistent with
  the chosen backend runtime.

## Considered Options

### Option A: Keep Laravel/PHP backend

Pros: batteries-included application framework; prior documentation alignment.
Cons: comparatively thin AI/eval ecosystem; provider SDKs and evaluation
tooling lag Python; the previously proposed PHP validator existed only to match
this stack.

### Option B: Full TypeScript (Node backend)

Pros: one language across the stack; shared types generated from schemas;
first-class provider SDKs.
Cons: evaluation and critic tooling thinner than Python; no other decisive
advantage for a generation-centric product.

### Option C: Python backend with React/TypeScript frontend (chosen)

Pros: deepest AI ecosystem for generation, critics, and evaluation; FastAPI
provides a typed, async, OpenAPI-native application layer; JSON Schema 2020-12
validation is first-class through `jsonschema`.
Cons: two languages across the stack; shared contract types must be generated
from the canonical JSON Schemas rather than shared natively.

### Option D: Hybrid Python AI engine behind a TypeScript API

Pros: isolates AI concerns.
Cons: two backend runtimes and an internal service boundary before the first
slice is proven; highest overhead for a solo builder.

## Decision

Motiflow's backend is **Python 3.12+** (FastAPI as the application-layer
direction), with the existing **React + TypeScript** frontend direction
retained. PostgreSQL, Redis, S3-compatible object storage, and containerized
deployment direction are unchanged.

Consequences for Task 001 (C-06): the contract validator toolchain is a plain
**Python 3.12+ CLI** using **`jsonschema` (>=4.21, 2020-12 dialect)** for
structural validation plus a small repository-owned semantic validator, with
dependencies pinned in a committed lockfile. It must not require a network
connection after dependencies are installed and must return non-zero on any
structural or semantic failure. The entrypoint name
`./tools/validate-decisive-slice-contracts` is unchanged.

Cross-stack type safety: TypeScript types for the frontend are generated from
the canonical JSON Schemas; schemas remain the single source of truth per
ADR-0003.

## Migration and Rollback

No implementation exists, so migration is documentation-only:
`MASTER_CONTEXT.md`, `docs/SYSTEM_DESIGN.md`, and
`docs/02-architecture/ENGINEERING_ARCHITECTURE.md` are updated by the change
that lands this ADR. Rollback before implementation is a documentation revert.
After implementation begins, changing the backend runtime requires a
superseding ADR.

## Verification

- No repository document outside historical/archived material continues to
  present Laravel/PHP as the current backend direction.
- Task 001 and the C-06 record name the Python toolchain, dependency range,
  and lockfile policy.
- The docs-check tooling passes after the coordinated updates.

## Approval

| Authority | Name | Decision | Date | Notes |
|---|---|---|---|---|
| Accountable product owner | Jarkius | ACCEPT | 2026-07-26 | Chose AI ecosystem depth as the deciding property |
| Chief architect | Jarkius | ACCEPT | 2026-07-26 | Single backend runtime until the contract proof completes |
| Engineering lead | Jarkius | ACCEPT | 2026-07-26 | Approves Python 3.12+ / `jsonschema` toolchain for Task 001 |

Shared-assignee note: Jarkius holds all three authority roles. This record is
an explicit human decision captured in-session; the separation-of-duties risk
and its independent-review control remain as stated in
`docs/02-architecture/DECISIVE_SLICE_CONTRACT_ACCEPTANCE.md`.
