# Creative Kernel

**Status:** Architecture specification
**Owner:** Chief Architect
**Scope:** Creative Kernel responsibilities, boundaries, and governed artifact state

The Creative Kernel is Motiflow's domain foundation. It defines the stable language, rules, and lifecycle for creative work independently of any model provider or workflow engine.

## Responsibilities

- Canonical artifact schemas
- Validation and compatibility rules
- Versioning and lineage
- Confidence representation
- Provenance and evidence links
- Policy and governance hooks
- Artifact comparison and invalidation rules
- Domain events

## Canonical decisive-slice artifacts

- `Intake Package`
- `Normalized Brief`
- `Knowledge Fusion Package`
- `Creative Direction Package`
- `Direction Approval Record`
- `Generation Specification`
- `Generated Candidate Set`
- `Critic Evaluation Package`
- `Final Approval Record`
- `Provenance Record`

Audience profiles, research packs, brand context, narrative structures, metaphor candidates, human feedback, and creative memory may exist as supporting records. They do not replace or rename the canonical handoffs above.

## Kernel rules

1. Every artifact has a globally unique identifier, schema version, project identifier, creator, timestamps, and provenance.
2. Artifacts are immutable once emitted; corrections create new versions.
3. Every engine declares accepted input and emitted output contract versions.
4. Confidence is attached to claims and decisions, not treated as a single unexplained number.
5. Downstream artifacts record the exact upstream versions used.
6. Human edits are first-class events and never overwritten by silent regeneration.
7. Validation failures stop propagation until corrected or explicitly overridden by policy.

## Boundary

The Kernel does not schedule jobs, call models, render assets, or own presentation logic. Those responsibilities belong to the Orchestrator, engine adapters, and product applications.
