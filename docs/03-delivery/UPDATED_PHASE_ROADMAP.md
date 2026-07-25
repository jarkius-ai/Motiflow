# Motiflow Delivery Roadmap

**Status:** Review-ready delivery planning artifact
**Owner:** Delivery and Product
**Scope:** Motiflow implementation phases and sequencing after the documentation baseline

This document proposes delivery sequencing. It does not, by itself, change human-accepted product intent, architecture, or ADR decisions.

## Merged documentation stream

- Phase 1 — Repository foundation
- Phase 2 — Documentation normalization
- Phase 2.5 — Proposed runtime contract baseline

## Product and implementation stream

### Phase 3 — Manual validation baseline

Define the manual validation path for the decisive creative-direction slice before broad automation begins.

### Phase 4 — Two-gate workflow review

Review and obtain required human acceptance of the proposed first workflow, which preserves two explicit gates:

- Gate 1: require authorized human approval of the Creative Direction Package before generation proceeds.
- Gate 2: require authorized human final approval after generated candidates and critics complete.

### Phase 5 — Canonical schemas, fixtures, and validation command

Create the canonical contracts, fixtures, and one repository validation command needed to prove the first slice without expanding into broader infrastructure.

### Phase 6 — One executable workflow

Implement one executable workflow that carries a creative brief through direction definition, generation handoff, critique, and approval readiness.

### Phase 7 — Thin Model Gateway

Add only the thinnest model-execution layer required by the first workflow:

- provider-neutral interface;
- deterministic mock implementation;
- one real provider integration.

### Phase 8 — Generated candidates, critics, and final approval

Use the first workflow and thin gateway to produce generated candidates, run critics, and record the final approval decision with full provenance.

## Explicit deferrals

- Multi-provider routing.
- Fallback mesh and resilience breadth beyond the first provider path.
- Cost, token, latency, and validation dashboards.
- CMS and social publishing.
- SDK ecosystem expansion.
- Editorial authoring automation beyond what the first slice requires.

## Retention principle

Nothing is deleted by normal workflow execution. Assets transition through active, published, superseded, archived, and historical states. Physical deletion is reserved for legal, privacy, security, or explicitly authorized maintenance processes.

## Immediate next backlog

Use [`PENDING_WORK_TO_READY.md`](PENDING_WORK_TO_READY.md) as the active
operational path through the blocked pre-implementation state.

1. Authorize validation setup: owner, facilitator, participants, restricted
   evidence controls, and frozen tools/settings.
2. Execute `docs/01-product/MVP_VALIDATION_PLAN.md` with the prepared cases and
   record terminal evidence.
3. Record the accountable product-owner `PROCEED`, `REVISE`, or `STOP`
   decision.
4. Obtain required human review of the two-gate workflow, canonical artifact
   vocabulary, envelope, approval references, schema policy, and validator
   toolchain.
5. Create the governed `evidence/sign-off commit`.
6. Run the MEOS Definition of Ready check and promote Task 001 only when every
   prerequisite passes.
7. Build the canonical schemas, fixtures, and single validation command.
8. Build one executable workflow before broadening platform surface area.
9. Add the thin Model Gateway interface, deterministic mock, and one real
   provider.
10. Run generated candidates through critics and capture final approval
    evidence.
