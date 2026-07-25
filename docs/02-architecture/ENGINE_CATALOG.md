# Engine Catalog

**Status:** Architecture catalog
**Owner:** Chief Architect
**Scope:** Bounded engine, critic, gateway, and connector responsibilities

Each engine is a replaceable specialist that communicates through Creative Kernel contracts.

## Discovery engines

### Research Engine
Collects, extracts, and synthesizes evidence from approved sources.

### Audience Engine
Builds audience needs, tensions, language, motivations, and risks.

### Brand Engine
Interprets brand identity, tone, visual rules, exclusions, and compliance constraints.

### Business Context Engine
Clarifies objective, offer, channel, market context, and success criteria.

## Reasoning engines

### Knowledge Fusion Engine
Reconciles discovery outputs into a grounded strategic context.

### Narrative Intelligence Engine
Creates narrative structures, tensions, transformations, and message hierarchy.

### Symbol Intelligence Engine
Maps abstract meaning to metaphors, symbols, spatial relationships, and visual language.

### Creative Director Engine
Selects and composes the dominant narrative, metaphor, mood, composition, and art direction.

## Production engines

### Prompt Compiler
Converts provider-neutral creative packages into provider-specific generation requests.

### Model Gateway
Routes provider-neutral requests for image, video, layout, copy, and other model capabilities through the Connector Gateway. Provider-specific SDKs remain inside connector adapters.

### Adaptation Engine
Transforms approved direction across formats, channels, dimensions, and variants.

## Evaluation engines

### Visual Critic
Evaluates composition, hierarchy, clarity, craft, and visual coherence.

### Brand Critic
Evaluates identity, tone, exclusions, and brand-system compliance.

### Business Critic
Evaluates alignment to objective, audience, message, and intended response.

### Constraint Critic
Checks technical, textual, policy, format, and production constraints.

### Synthesis Critic
Combines critic findings into prioritized actions without averaging away important failures.

## Engine specification requirement

Every engine must document mission, non-responsibilities, input and output contracts, confidence model, deterministic validation, failure modes, retry behavior, evaluation fixtures, cost profile, and data-handling boundaries.
