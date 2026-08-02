# AI Execution Layer

**Status:** Review-ready target architecture specification
**Owner:** Chief Architect
**Scope:** Provider-neutral model execution, routing, validation, provenance, and usage controls

## Purpose

The AI Execution Layer connects Motiflow engines to external language and multimodal models without coupling the Creative Kernel or Workflow Orchestrator to any provider.

The orchestrator owns workflow state, retries, approvals, budgets, idempotency, and persistence. Models provide bounded cognitive capabilities such as extraction, analysis, writing, creative direction, critique, and learning synthesis.

This document describes the eventual boundary, not the initial delivery sequence. The MVP implements only the gateway interface, deterministic mock, one real provider adapter, validation, and provenance required by the decisive creative workflow. Multi-provider routing, fallback, registries, ledgers, and dashboards remain deferred until that workflow demonstrates value.

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

The complete target layer MUST provide:

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
    projectId: string;
    artifactId?: string;
    stepId: string;
  };
}
```

Engines MUST call this interface or an equivalent Motiflow-owned contract. They MUST NOT import provider SDKs directly.

## Capability routing

The decisive-slice capabilities are (identifiers match the workflow contract
in `docs/02-architecture/RUNTIME_CONTRACTS.md`):

- brief_normalization
- knowledge_fusion
- creative_direction
- generation_specification
- candidate_generation
- deterministic_candidate_review
- critic_evaluation

Potential later capabilities include:

- metadata_extraction
- claim_extraction
- narrative_analysis
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

Valid JSON is not sufficient. Semantic validators MUST detect unknown citations, mismatched artifact references, invalid confidence ranges, and contradictions with the approved Creative Direction Package or Generation Specification.

## Deterministic boundaries

Models MUST NOT control:

- workflow state transitions;
- artifact and project identifiers;
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

## Delivery sequence

1. Manually validate the full two-gate creative workflow with representative briefs and intended users.
2. Freeze the decisive-slice artifact contracts, fixtures, and validation command through human review.
3. Build one executable workflow against a narrow connector port and deterministic fixtures.
4. Add the `ModelGateway` interface and deterministic mock required by that workflow.
5. Add structured and semantic validation plus invocation provenance required by the slice.
6. Add one real provider adapter and prove the generated-candidate path through final approval.
7. Consider registries, ledgers, routing, fallback, and additional adapters only from observed demand.
