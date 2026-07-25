# Motiflow Glossary

**Status:** Authoritative vocabulary reference  
**Owner:** Chief Architect

This glossary expands `TERMINOLOGY.md`. When definitions conflict, `TERMINOLOGY.md` and accepted ADRs take precedence.

## Core identity

### Motiflow
The customer-facing product, platform, repository, and ecosystem identity.

### ACDS
**Autonomous Creative Direction System.** The product architecture that powers Motiflow. ACDS is not an alternative product name.

### MEOS
**Motiflow Engineering Operating System.** The governance and delivery system used to specify, build, verify, review, and release Motiflow.

## Runtime components

### Creative Kernel
The integrity and governance boundary that owns canonical schemas, validation, state rules, confidence, provenance, policies, version compatibility, and approval requirements. It does not create visual ideas or schedule work.

### Workflow Orchestrator
The execution coordinator that plans and runs the hybrid DAG, resolves dependencies, schedules parallel and sequential work, applies retries and timeouts, pauses at gates, and passes validated outputs downstream. It does not perform specialist creative reasoning.

### Engine
A bounded reasoning or transformation component with declared inputs, outputs, capability, version, quality thresholds, and failure behavior.

### Agent
An execution actor that may use one or more engines, tools, models, and policies to complete a bounded task. An agent is not automatically an architectural service.

### Connector
A controlled adapter to an external model, knowledge source, storage system, publishing destination, or enterprise service.

### Connector Gateway
The centralized policy and normalization layer through which external providers are accessed. Engines do not call providers directly.

### Critic
A focused evaluator that inspects an artifact against a specific quality dimension and produces structured findings rather than generic praise.

### Review Fusion
The decision stage that combines focused critic results, resolves material disagreement, and determines whether revision or human approval is required.

## Workflow concepts

### Workflow
A versioned definition of nodes, dependencies, gates, policies, inputs, outputs, and completion conditions.

### Run
One execution instance of a workflow against a specific set of inputs and versions.

### DAG
Directed acyclic graph. The dependency structure used to support parallel discovery and design work while preserving sequential creative commitments.

### Synchronization Barrier
A workflow point that waits for all required upstream outputs to complete and validate before downstream fusion begins.

### Human Gate
An explicit state transition requiring authorized human approval, rejection, revision, or override.

### Incremental Re-computation
Re-running only the stages affected by a changed input or decision, plus their downstream dependents.

## Information and artifacts

### Artifact
A structured, versioned output produced or approved during a workflow.

### Package
A typed artifact used as an input/output contract between stages, such as a Narrative Package or Creative Direction Package.

### Creative Package
The canonical aggregate of source, narrative, symbolism, direction, compilation, evaluation, confidence, provenance, and audit information for a creative run.

### Schema
The machine-validatable definition of an artifact or event structure.

### Contract
An agreed interface that defines structure, behavior, compatibility, errors, and ownership across a boundary.

### Provenance
Traceable information about sources, producing engines, models, instructions, knowledge versions, timestamps, and human overrides.

### Evidence Confidence
Confidence in the factual basis supporting a conclusion.

### Reasoning Confidence
Confidence in the interpretation or synthesis derived from evidence.

### Creative Confidence
Confidence that a selected creative decision is suitable for the intended objective. It is not factual certainty.

## Creative reasoning

### Knowledge Fusion
The stage that consolidates independent discovery outputs, removes duplication, surfaces contradictions, preserves uncertainty, and produces one canonical understanding package.

### Dominant Narrative
The single primary idea an artifact should communicate.

### Dominant Metaphor
The main visual mechanism used to translate the narrative into a coherent physical or spatial concept.

### Hero Object
The primary object carrying the visual meaning and hierarchy.

### Visual DNA
A structured profile of the desired editorial, enterprise, industrial, scientific, and stylistic characteristics, including forbidden traits.

### Prompt Compiler
A component that translates an approved provider-neutral design specification into provider-specific syntax without changing meaning.

### Prompt Drift
A compilation failure where provider-specific instructions alter the approved metaphor, hierarchy, mood, constraints, audience, or text policy.

## Governance

### Authoritative Document
A document that controls decisions within a declared scope.

### Supporting Document
A document that explains, illustrates, or operationalizes an authoritative source without superseding it.

### ADR
Architecture Decision Record. The durable record of context, decision, alternatives, consequences, status, and related artifacts for an architecture-significant choice.

### Definition of Ready
The minimum evidence and clarity required before implementation begins.

### Definition of Done
The conditions required to consider work complete, including verification, documentation, review, compatibility, and rollback evidence.

### Quality Gate
A mandatory pass/fail decision based on observable evidence. A score cannot override a failed critical gate.
