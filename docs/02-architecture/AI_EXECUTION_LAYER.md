# AI Execution Layer

## Purpose

The AI Execution Layer connects Motiflow engines to external language and multimodal models without coupling the Creative Kernel or Workflow Orchestrator to any provider.

The orchestrator owns workflow state, retries, approvals, budgets, idempotency, and persistence. Models provide bounded cognitive capabilities such as extraction, analysis, writing, creative direction, critique, and learning synthesis.

## Core principle

> Models are replaceable capability providers. Motiflow contracts, workflows, knowledge, decisions, and retained evidence are the durable system.

## Architecture

```text
Workflow Orchestrator
        |
        v
Motiflow Model Gateway
        |
        +-- Capability Registry
        +-- Routing and Policy Engine
        +-- Structured Output Validator
        +-- Prompt Registry
        +-- Cost and Usage Ledger
        +-- Invocation Recorder
        |
        +-- Unified SDK Adapter
        +-- OpenAI Adapter
        +-- Anthropic Adapter
        +-- Google Adapter
        +-- Mock Adapter
```

## Responsibilities

The layer MUST provide:

- provider-neutral model invocation contracts;
- capability-based routing rather than hard-coded model selection;
- JSON Schema constrained outputs where supported;
- schema and semantic validation before artifact acceptance;
- retries, timeout handling, fallback routing, and rate-limit handling;
- prompt, schema, model, and adapter version recording;
- token, latency, and cost accounting;
- privacy, residency, and provider allow-list policies;
- deterministic mock execution for tests;
- immutable invocation history for accepted and rejected outputs.

## Model Gateway contract

```ts
export interface ModelGateway {
  execute<TInput, TOutput>(request: ModelRequest<TInput>): Promise<ModelResult<TOutput>>;
}

export interface ModelRequest<TInput> {
  capability: string;
  input: TInput;
  outputSchemaId: string;
  promptId: string;
  policy: {
    privacyTier: "public" | "internal" | "restricted";
    maxCostUsd?: number;
    timeoutMs?: number;
    allowFallback?: boolean;
  };
  trace: {
    workflowRunId: string;
    publicationId?: string;
    stepId: string;
  };
}
```

Engines MUST call this interface or an equivalent Motiflow-owned contract. They MUST NOT import provider SDKs directly.

## Capability routing

Initial capabilities include:

- metadata-extraction
- claim-extraction
- narrative-analysis
- editorial-writing
- editorial-critique
- symbolism-development
- creative-direction
- prompt-compilation
- image-analysis
- visual-critique
- learning-synthesis

Model names remain runtime configuration. Routing considers capability support, quality tier, cost tier, context size, modality, privacy policy, provider health, and workflow budget.

## Validation pipeline

```text
Provider response
      |
      v
Transport validation
      |
      v
JSON parsing
      |
      v
Schema validation
      |
      v
Semantic validation
      |
      +-- accepted artifact
      +-- retryable failure
      +-- terminal failure
      +-- human clarification
```

Valid JSON is not sufficient. Semantic validators MUST detect unknown citations, mismatched publication IDs, unsupported destinations, invalid confidence ranges, and contradictions with approved narrative artifacts.

## Deterministic boundaries

Models MUST NOT control:

- workflow state transitions;
- publication identifiers;
- file paths and retention decisions;
- authentication and secrets;
- database transactions;
- approval requirements;
- retry counters or cost limits;
- HTML sanitization;
- publishing authorization;
- deletion or archival policy.

## Retention and learning

Every invocation produces a retained execution record, including failed, rejected, and superseded results. Nothing is physically deleted except where legal, security, or privacy policy requires it.

The record includes provider, model, adapter, prompt version, schema version, input/output artifact versions, token usage, estimated cost, latency, validation findings, reviewer outcome, and supersession links.

## Initial implementation order

1. ModelGateway interface
2. Model capability registry
3. Mock adapter
4. Structured-output validator
5. Prompt registry
6. Cost and usage ledger
7. Unified SDK adapter
8. Native provider adapters
9. Routing and fallback engine
10. First crawler-to-publication workflow
