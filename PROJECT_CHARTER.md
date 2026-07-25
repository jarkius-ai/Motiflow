# Motiflow Project Charter

**Status:** Foundational product authority  
**Product:** Motiflow  
**Product architecture:** Autonomous Creative Direction System (ACDS)  
**Engineering governance:** Motiflow Engineering Operating System (MEOS)

## Purpose

This charter defines Motiflow's enduring product intent: vision, mission, scope, principles, product pillars, and strategic direction. It governs product-level decisions but does not duplicate detailed architecture, delivery controls, contracts, or implementation plans.

## Vision

Build the operating system for enterprise creative intelligence, transforming business intent into governed, explainable creative execution.

## Mission

Enable organizations to move beyond prompt engineering by coordinating specialized intelligence and creative engines through a trustworthy, reviewable workflow.

## North Star

Every material creative decision should be traceable, measurable, reusable, and aligned with business outcomes.

## Product Identity

- **Motiflow** is the customer-facing product, platform, and repository identity.
- **ACDS** is the underlying product architecture.
- **MEOS** is the engineering governance and delivery system used to build, verify, review, and release Motiflow.

These names are related but not interchangeable. Canonical definitions are maintained in [`docs/00-foundation/TERMINOLOGY.md`](docs/00-foundation/TERMINOLOGY.md) and architecture-significant changes require an ADR.

## Guiding Principles

- Understand before generating.
- Reason before rendering.
- Meaning over decorative aesthetics.
- One dominant story and one dominant metaphor per visual concept.
- Human oversight for high-impact, low-confidence, brand-sensitive, or publishing decisions.
- Model-agnostic architecture and replaceable providers.
- Canonical, versioned contracts between components.
- Explainability, provenance, and quality through orchestration.
- Measured outcomes over feature volume.

## Product Pillars

1. **Creative Intelligence** — understand narrative, audience, business meaning, technical context, brand, and evidence.
2. **Workflow Orchestration** — coordinate parallel discovery, sequential creative commitment, review, retry, and approval.
3. **Enterprise Governance** — preserve policy, permissions, provenance, auditability, and human authority.
4. **Knowledge and Memory** — reuse approved context, brand systems, visual language, decisions, and evaluations.
5. **Multi-Model Execution** — compile and route governed creative specifications through replaceable providers.
6. **Quality and Evaluation** — combine focused critics, measurable scorecards, regression checks, and human review.

## Initial Product Boundary

The first release focuses on editorial and enterprise technology visual-direction workflows. Motiflow v1 is not intended to replace general graphic-design suites, digital asset management platforms, presentation authoring systems, project-management tools, or human brand approval.

The MVP must prove one complete path from source material to validated creative direction, provider-specific generation, multi-critic review, and human approval.

## Strategic Goal

Evolve Motiflow from a focused creative application into an extensible platform with governed workflows, SDKs, connectors, evaluation systems, and an ecosystem for enterprise creative operations.

## Success Definition

Motiflow succeeds when teams can reliably:

- turn ambiguous source material into a validated creative direction;
- understand why the direction was recommended;
- generate coherent results across replaceable rendering providers;
- reduce avoidable revision cycles;
- reuse approved knowledge and visual language;
- measure quality, cost, speed, and workflow performance;
- preserve governance, provenance, approval, and change history.

## Documentation Authority

Use [`docs/00-foundation/DOCUMENT_AUTHORITY.md`](docs/00-foundation/DOCUMENT_AUTHORITY.md) to resolve conflicts.

The canonical foundation reading order is:

`START_HERE.md` → `PROJECT_CHARTER.md` → `MASTER_CONTEXT.md` → `CONTEXT_INDEX.yaml` → `MEOS/20_PROJECT_BOOTSTRAP.md` → task-specific documents.

This charter controls product intent. `MASTER_CONTEXT.md` controls stable shared architecture. Accepted ADRs control architecture-significant decisions. MEOS controls engineering governance and delivery execution.
