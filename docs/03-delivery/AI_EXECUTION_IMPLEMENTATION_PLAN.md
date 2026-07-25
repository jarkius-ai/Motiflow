# AI Execution Implementation Plan

**Status:** Implementation planning artifact
**Owner:** Delivery and Chief Architect
**Scope:** Sequenced implementation of the provider-neutral AI execution foundation

## Objective

Implement the provider-neutral execution foundation required to automate the path from crawled Markdown to a review-ready Publication Package.

## Phase 4A — Contracts and testability

Deliver:

- `ModelGateway` interface;
- request, response, error, usage, and trace types;
- capability registry schema;
- mock model adapter;
- JSON Schema output validator;
- semantic validation extension points;
- unit and contract tests.

Exit criteria:

- engines compile without provider SDK dependencies;
- mock workflows produce deterministic artifacts;
- invalid output cannot enter the artifact store;
- every invocation has a trace and usage record.

## Phase 4B — Prompt and configuration control

Deliver:

- versioned prompt registry;
- model routing configuration;
- privacy/provider policies;
- workflow budgets;
- model and prompt provenance in artifact metadata.

Exit criteria:

- prompt changes are versioned and reviewable;
- model names can change without application-code changes;
- workflow execution stops safely when budgets are exceeded.

## Phase 4C — Provider adapters

Deliver adapters in this order:

1. unified TypeScript AI SDK adapter;
2. OpenAI native adapter;
3. Anthropic native adapter;
4. Google native adapter.

Each adapter must pass the same contract suite and expose only declared capabilities.

## Phase 4D — Routing, resilience, and observability

Deliver:

- capability-based routing;
- timeout and retry policy;
- fallback routing;
- rate-limit handling;
- provider health signals;
- cost, token, latency, and validation dashboards;
- retained failure and supersession records.

## Phase 4E — First automated workflow

```text
Crawler Markdown
  -> source hash and duplicate detection
  -> Publication Package creation
  -> metadata and claim extraction
  -> narrative analysis
  -> article and social variants
  -> creative direction and image prompt
  -> visual generation handoff
  -> editorial and visual critique
  -> human review queue
```

The crawler remains independent. It writes Markdown to an inbox or calls an ingestion endpoint. Motiflow owns normalization, processing, retention, review, and export.

## Proposed package layout

```text
packages/
  ai/
    gateway/
    registry/
    routing/
    validation/
    prompts/
    telemetry/
    testing/
  connectors/
    ai/
      unified-sdk/
      openai/
      anthropic/
      google/
      mock/
```

## Security and operational requirements

- API keys are provided through secret management and never stored in publication packages.
- Restricted content is routed only to approved providers.
- Logs must redact source content where policy requires it.
- Publishing remains human-gated initially.
- All external calls are idempotency-aware and traceable.
- Physical deletion requires a separate policy-authorized process.

## Definition of done

Phase 4 is complete when a sample Markdown article can run through the workflow using the mock adapter and at least one real provider, producing a validated, versioned Publication Package with complete provenance and no direct provider dependency inside an engine.
