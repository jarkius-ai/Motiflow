# Visual Prototype Plan — 2026-08-03

**Status:** Non-authoritative lab spike plan. Not a MEOS task, not tracked by
`MEOS/tasks/`, not subject to Definition of Ready, independent review, or the
Quality Gate.
**Purpose:** Give Jarkius something real to look at and comment on, fast —
before any governed implementation exists.

## Why this file exists

Across this session we found that the current governed sequence
(`MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md`) produces zero visual
output even when complete — it is schemas, fixtures, a validator command, and
CI only, and explicitly excludes UI. Jarkius wants to see and react to real
output (an actual generated image, a real page) to give feedback, the same
way he already works with Gemini → ChatGPT image generation today.

We also surfaced, via a real validation session (see
`docs/01-product/validation/2026-07-25-mvp-validation-report.md`, finding
F-03), that the product's own two-gate approval model (direction approval,
then final approval) felt redundant to him as a solo user — he wants to
approve by looking at output and tuning it, not by approving a text plan
blind before any image exists. That is a real, separate, larger design
question (solo-first vs. team/enterprise scope, whether the two-gate model
survives for solo use) that is **explicitly parked, not decided**, by this
plan. See "Parked design question" below.

## What this plan is

A disposable, throwaway visual prototype:

- Takes a simple text input (a brief, or a short article summary — this is
  intentionally unspecified in detail; the next session should ask Jarkius
  which is more useful to try first).
- Produces one generated image, using whatever is fastest to wire up (a real
  image-generation API call, or a mock/placeholder image if no API key is
  configured yet — either is fine for this spike).
- Lets Jarkius look at the result and say what he'd change.
- Regenerates based on that feedback.

No schema, no contract, no approval record, no database. It exists to let
one person look at output and talk about it. It is explicitly **not** meant
to survive as production code — expect to throw it away or heavily rewrite
it once real design decisions are made.

## Where it lives

Put this work under a new top-level `lab/` or `prototype/` directory (either
name is fine — pick one and stay consistent), **not** under `packages/`,
`docs/`, or `MEOS/`. This keeps it unambiguous that it is not governed
product code. If a `.gitignore` entry or a clear `README.md` inside that
folder stating "throwaway spike, not governed" helps future-you, add one.

## What stays untouched

- `MEOS/tasks/TASK-001_DECISIVE_SLICE_CONTRACT_PROOF.md` remains `BLOCKED`.
  This prototype does not promote it, does not satisfy any of its
  prerequisites, and does not count as evidence toward Definition of Ready.
- `docs/01-product/validation/2026-07-25-mvp-validation-report.md` remains
  as recorded (2 of 5 minimum sessions, F-03 gate-comprehension failure,
  disclosed gate deviation still awaiting product-owner acceptance). This
  prototype does not add to or resolve that report.
- `CONTEXT_INDEX.yaml`'s `readiness_score_current` and `task_001_status` are
  not touched by this work.
- Open governance PRs from this session (#23–#27 at time of writing) are
  independent of this plan and can be reviewed/merged on their own schedule.

## Parked design question (do not decide this inside the prototype)

Whether Motiflow's real product should:

(a) keep the two-gate model as designed, scoped for its stated team/agency
    target customer (`docs/VISION.md`), with solo use being an edge case; or
(b) re-scope the MVP itself as solo-first (Jarkius as the real initial
    customer), collapsing the two-gate model into an iterative
    generate-view-tune loop with implicit approval, deferring team-oriented
    separation-of-duties features to a later phase.

This is a real, hard-to-reverse architecture and product-scope decision
(it would touch `docs/VISION.md`, `docs/PRD.md`,
`docs/02-architecture/RUNTIME_CONTRACTS.md`,
`docs/02-architecture/WORKFLOW_STATE_MACHINE.md`, and ADR-0003). It should go
through a proper brainstorming/design session and likely a new or amending
ADR — not be resolved as a side effect of building a throwaway prototype.

**Recommended next step after this prototype:** run a dedicated brainstorming
session on this exact question, using what the prototype revealed about how
Jarkius actually wants to iterate, before deciding (a) or (b).

## Resume instructions for the next session

1. Read this file first.
2. Ask Jarkius: brief-text input or article-summary input for the first
   prototype pass?
3. Build the smallest possible generate → view → comment → regenerate loop
   under `lab/` (or `prototype/`), using a real image API if a key is
   available, otherwise a placeholder/mock image.
4. Do not touch `MEOS/tasks/`, `CONTEXT_INDEX.yaml` readiness fields, or the
   validation report as part of this work.
5. Once Jarkius has looked at and commented on a few generated results,
   surface the parked design question above as a dedicated brainstorming
   session before writing any ADR or changing the governed architecture.
