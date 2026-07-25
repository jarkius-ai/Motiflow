# ADR-0002: Provider-Neutral AI Model Gateway

- Status: Proposed
- Date: 2026-07-25
- Decision owners: Motiflow architecture

## Context

Motiflow requires language and multimodal models for extraction, reasoning, writing, creative direction, critique, and learning. Provider capabilities, pricing, availability, and model names change frequently. Direct SDK imports inside engines would create lock-in, inconsistent observability, fragmented policy enforcement, and difficult testing.

## Decision

Motiflow will own a provider-neutral `ModelGateway` contract. All engines invoke model capabilities through this gateway. Provider SDKs are isolated behind adapters.

Routing is capability-based and policy-aware. Model identifiers are runtime configuration, not application logic.

The gateway must support:

- unified and native provider adapters;
- schema-constrained output where available;
- semantic validation;
- cost, latency, and token accounting;
- retries and fallback routing;
- provider health and privacy policies;
- complete invocation provenance;
- a deterministic mock adapter.

## Consequences

### Positive

- Providers and models can be replaced without rewriting engines.
- Security, budgets, validation, and telemetry are enforced consistently.
- Tests can run without external API calls.
- Model comparisons and controlled experiments become possible.
- Historical outputs remain reproducible and explainable.

### Negative

- The gateway adds an abstraction and maintenance cost.
- Provider-specific features may require escape hatches.
- Lowest-common-denominator abstractions must be avoided.

## Guardrails

Provider-specific features may be exposed through typed capability extensions, but engines may not import provider SDKs directly. Any escape hatch must still pass through gateway policy, telemetry, and retention controls.

## Alternatives rejected

1. **Single provider throughout the application** — rejected due to lock-in and operational risk.
2. **Direct SDK calls in each engine** — rejected due to duplicated policy and poor observability.
3. **Let the LLM orchestrate the entire workflow** — rejected because workflow state, approvals, budgets, and persistence must remain deterministic.
