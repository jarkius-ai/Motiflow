# Validation Case Catalog

**Status:** Case packets prepared; round authorization pending
**Owner:** Product
**Scope:** Synthetic, anonymized input cases for the pre-implementation MVP validation round

This catalog operationalizes the coverage requirements in
[`../MVP_VALIDATION_PLAN.md`](../MVP_VALIDATION_PLAN.md) against the decisive
slice defined in [`../../PRD.md`](../../PRD.md), the role coverage in
[`../PERSONAS.md`](../PERSONAS.md), and the evaluation layers in
[`../../04-ai/EVALUATION_FRAMEWORK.md`](../../04-ai/EVALUATION_FRAMEWORK.md).

All cases are synthetic or anonymized composites. They are `CASE_PREPARED`
inputs only: their content packets are complete, but the validation round is
not ready to start until the dated report records every pre-session control.
They do not record participant outcomes, approvals, or observed performance.

## Coverage Summary

| Coverage requirement | Case IDs |
|---|---|
| Well-formed briefs | `VC-01`, `VC-02` |
| Ambiguous or contradictory briefs | `VC-03`, `VC-04` |
| Brand- or policy-sensitive briefs | `VC-05`, `VC-06` |
| Article-derived brief | `VC-07` |
| Edge case | `VC-08` |

## Case Matrix

| Case | Category | Primary personas | Source type | Channel | Completeness | Ambiguity / contradiction | Brand / policy sensitivity | Expected decision difficulty | Session goal | Representative input |
|---|---|---|---|---|---|---|---|---|---|---|
| `VC-01` | Well-formed brief | Creative Lead, Designer / Content Producer | Structured brief | Paid social static | High | Low | Low | Medium | Confirm the canonical flow works cleanly when the brief is complete and approval-ready. | Launch visuals for a new sparkling water line aimed at health-conscious urban commuters, emphasizing bright citrus energy, premium simplicity, and a clean can packshot with room for offer copy. |
| `VC-02` | Well-formed brief | Brand and Marketing Manager, Creative Strategist | Structured brief | Landing-page hero | High | Low | Medium | Medium | Test whether rationale, metaphor, and composition intent are clear enough for both direction-owner and approver review. | B2B analytics campaign hero for operations leaders, focused on "clarity from complexity," with trust-forward visuals, restrained motion cues, and no consumer-tech tropes. |
| `VC-03` | Ambiguous brief | Creative Lead, Designer / Content Producer | Unstructured brief | Email header | Low | High; missing audience, format, and success criteria | Low | High | Exercise clarification handling without facilitator invention of material requirements. | "Need something premium but warm for next week. Keep it modern. Maybe photography, maybe illustration. It has to feel elevated without feeling exclusive." |
| `VC-04` | Contradictory brief | Brand and Marketing Manager, Creative Strategist | Mixed brief notes | Paid social static | Medium | Contradictory audience, tone, and visual direction | Medium | High | Test whether contradictions are surfaced and frozen before direction approval instead of being smoothed over informally. | Promote an executive finance summit to both CFOs and college students; must feel "minimal and information-dense," "luxury and playful," and use both bold neon contrast and understated grayscale. |
| `VC-05` | Brand-sensitive brief | Brand and Marketing Manager, Reviewer / Approver | Structured brief | Product page hero | High | Low | High brand sensitivity | High | Validate explicit prohibited elements, brand constraints, and approver confidence in the direction package. | Refresh a heritage skincare brand hero using its existing visual codes: muted mineral palette, clinical restraint, no exaggerated beauty retouching, no competitor-like pastel lifestyle styling, and no claims beyond approved copy themes. |
| `VC-06` | Policy-sensitive brief | Reviewer / Approver, Creative Strategist | Structured brief | Paid social static | High | Medium | High policy sensitivity | High | Test whether policy and compliance constraints block unsafe direction before generation planning. | Financial wellness ad for first-time investors highlighting long-term planning; avoid guaranteed-return language, urgency manipulation, or imagery implying instant wealth, while still feeling aspirational and accessible. |
| `VC-07` | Article-derived brief | Creative Strategist, Creative Lead | Source article normalized into brief | Editorial illustration | Medium after normalization | Medium | Low | High | Confirm article-to-brief normalization and whether source-derived direction remains explainable and bounded. | Source article summary: a reported feature on neighborhood cooling strategies, rooftop gardens, reflective materials, and public-health heat mitigation. Output target: one editorial hero image conveying collective urban resilience rather than disaster spectacle. |
| `VC-08` | Edge case | Designer / Content Producer, Reviewer / Approver | Sparse noisy input | Display banner | Low | High; underspecified and attachment-dependent | Medium | High | Reveal failure boundaries when the intake is too thin to proceed without invention. | "Use the deck cover vibe but make it for the campaign banner." No deck attached, no dimensions, no audience, and no approved brand or channel context supplied. |

## Executable Case Packets

### `VC-01` Well-Formed Brief Packet

| Field | Packet content |
|---|---|
| Objective | Launch a premium-feeling paid social visual for a new sparkling water line entering urban grocery and convenience channels. |
| Audience | Health-conscious urban commuters aged 25-40 who want a refreshing but low-sugar beverage option. |
| Channel / deliverable | One paid social static image for Instagram and mobile feed placements. |
| Required message | Bright citrus refreshment with premium simplicity; the product should feel clean, energetic, and easy to notice in a crowded feed. |
| Constraints / prohibited elements | Keep space for short offer copy; include a clean can packshot; avoid cluttered lifestyle scenes, heavy text overlays, or indulgent soda cues. |
| Available references | Synthetic product name: `Current Citrus`; package format: slim 330 ml can; approved product descriptors: citrus, crisp, low sugar, commuter-friendly. |
| Success signal | The participant can approve or revise direction using only the packet information without adding missing business or channel context. |

### `VC-02` Well-Formed Brief Packet

| Field | Packet content |
|---|---|
| Objective | Create a landing-page hero direction for a B2B analytics campaign aimed at operations leaders evaluating workflow visibility tools. |
| Audience | Operations directors and VP-level operations leaders at mid-market companies. |
| Channel / deliverable | One desktop-first landing-page hero concept with responsive intent noted for smaller screens. |
| Required message | "Clarity from complexity" for operational decision-makers who need trust, control, and visibility rather than hype. |
| Constraints / prohibited elements | Avoid consumer-tech clichés, neon dashboards, and startup-playful tone; preserve a trust-forward, restrained visual language. |
| Available references | Synthetic product framing: workflow analytics platform; approved value themes: visibility, bottleneck detection, calmer decision-making; no testimonials or metrics required in the hero. |
| Success signal | The participant can judge whether the rationale, metaphor, and composition intent are understandable for both direction-owner and approver review. |

### `VC-03` Ambiguous Brief Packet

| Field | Packet content |
|---|---|
| Verbatim input | "Need something premium but warm for next week. Keep it modern. Maybe photography, maybe illustration. It has to feel elevated without feeling exclusive." |
| Facilitator-known metadata | Source type: unstructured brief; intended deliverable label: email header; case tag: intentionally incomplete and clarification-heavy. |
| Preserved omissions | No audience provided. No business objective provided. No dimensions provided. No channel-specific success metric provided. |
| Preserved uncertainty | "Premium but warm," "modern," and "elevated without feeling exclusive" are intentionally undefined. |
| Available references | None beyond the verbatim input. |
| Session handling note | Do not add missing context unless the participant requests clarification and explicitly states what is missing. Capture the missing-field discussion as evidence. |

### `VC-04` Contradictory Brief Packet

| Field | Packet content |
|---|---|
| Verbatim input | Promote an executive finance summit to both CFOs and college students; must feel "minimal and information-dense," "luxury and playful," and use both bold neon contrast and understated grayscale. |
| Facilitator-known metadata | Source type: mixed brief notes; intended deliverable label: paid social static; case tag: contradiction-preservation and handoff-risk exercise. |
| Preserved conflicts | Audience conflict: CFOs and college students. Tone conflict: luxury and playful. Visual conflict: bold neon contrast and understated grayscale. Information-density conflict: minimal and information-dense. |
| Available references | None beyond the verbatim notes. |
| Session handling note | Do not reconcile the conflicts for the participant. The session tests whether contradictions are surfaced and frozen before direction approval. |

### `VC-05` Brand-Sensitive Brief Packet

| Field | Packet content |
|---|---|
| Objective | Refresh a heritage skincare brand product-page hero while preserving existing brand trust cues and avoiding off-brand beauty styling. |
| Audience | Existing and prospective skincare buyers seeking evidence of efficacy, restraint, and quality. |
| Channel / deliverable | One product page hero image direction. |
| Required message | Clinical restraint, ingredient credibility, and premium care without exaggerated transformation cues. |
| Constraints / prohibited elements | No exaggerated beauty retouching; no competitor-like pastel lifestyle styling; no unapproved efficacy claims; no medical-before/after framing; preserve muted mineral palette and calm studio discipline. |
| Available references | Synthetic brand guardrails: muted mineral palette, clinical restraint, ingredient-led trust, heritage positioning; no external moodboard required. |
| Success signal | The participant can evaluate brand alignment and prohibited elements directly from the packet without needing undocumented facilitator interpretation. |

### `VC-06` Policy-Sensitive Brief Packet

| Field | Packet content |
|---|---|
| Objective | Create a paid social direction for a financial wellness campaign aimed at first-time investors while staying inside conservative policy limits. |
| Audience | Adults early in their investing journey who want reassurance and clarity, not speculation cues. |
| Channel / deliverable | One paid social static image. |
| Required message | Long-term planning, steady confidence, and accessible financial learning. |
| Constraints / prohibited elements | No guaranteed-return language; no urgency manipulation; no luxury windfall imagery; no implied instant wealth; no claims that investing is risk-free. |
| Available references | Synthetic campaign theme: "Start steady"; approved framing themes: consistency, learning, horizon, calm progress. |
| Success signal | The participant can determine whether policy and compliance constraints are strong enough to block unsafe direction before generation planning. |

### `VC-07` Article-Derived Packet

| Field | Packet content |
|---|---|
| Synthetic article-source synopsis | A reported city feature describes how several neighborhoods are responding to intensifying heat waves. It covers apartment residents tending rooftop planters, a school installing reflective shade structures, small businesses repainting roofs with heat-reducing coatings, and a public-health worker explaining that cooling infrastructure works best when communities maintain it together. The article contrasts practical, collective adaptation with sensational disaster imagery and explicitly avoids framing heat resilience as a luxury available only to affluent districts. |
| Bounded output target | Normalize the article into a brief for one editorial hero illustration that conveys collective urban resilience and shared cooling strategies. The output target is a single publication-style hero image direction, not article writing, not infographics, and not multiple derivative assets. |
| Audience | Readers of a general-interest feature on climate adaptation and civic design. |
| Channel / deliverable | One editorial illustration hero for a digital article header. |
| Required message | Neighborhood-scale heat mitigation is practical, collaborative, and materially visible in the built environment. |
| Constraints / prohibited elements | Avoid disaster spectacle, apocalyptic smoke, or lone-hero framing; do not drift into technical diagramming or policy explainer graphics. |
| Available references | The synopsis above is the only source material for the session; no full article body is supplied. |
| Success signal | The participant can judge whether article normalization produces an explainable direction that stays bounded to the supplied source synopsis. |

### `VC-08` Edge Case Packet

| Field | Packet content |
|---|---|
| Verbatim input | "Use the deck cover vibe but make it for the campaign banner." |
| Facilitator-known metadata | Source type: sparse noisy input; intended deliverable label: display banner; case tag: missing-attachment and stop-condition risk. |
| Intentionally missing dependency | The referenced deck is not provided. No banner dimensions are provided. No audience is provided. No approved brand context is provided. |
| Available references | None. The missing deck is intentional and must remain unavailable during the session. |
| Session handling note | Do not substitute a deck, invent a target size, or infer brand rules. This case is ready specifically because the missing dependency is part of the test. |

## Case-Preparation Notes

| Case | Required tags | Case-prepared condition | Status |
|---|---|---|---|
| `VC-01` | `well-formed`, `structured`, `low-ambiguity` | This catalog now contains the objective, audience, deliverable, message, constraints, references, and success signal. | `CASE_PREPARED` |
| `VC-02` | `well-formed`, `structured`, `brand-aware` | This catalog now contains the business objective, audience, landing-page context, constraints, references, and success signal. | `CASE_PREPARED` |
| `VC-03` | `ambiguous`, `incomplete`, `clarification-heavy` | This catalog preserves the omissions and uncertain terms verbatim, with no hidden solution added. | `CASE_PREPARED` |
| `VC-04` | `contradictory`, `mixed-source`, `high-decision-difficulty` | This catalog preserves the conflicts verbatim and states that the facilitator must not reconcile them. | `CASE_PREPARED` |
| `VC-05` | `brand-sensitive`, `prohibited-elements`, `approver-critical` | This catalog now contains explicit brand guardrails, prohibited elements, and success criteria. | `CASE_PREPARED` |
| `VC-06` | `policy-sensitive`, `regulated-language`, `blocking-risk` | This catalog now contains explicit policy exclusions, approved framing themes, and success criteria. | `CASE_PREPARED` |
| `VC-07` | `article-derived`, `normalization`, `editorial` | This catalog now contains a bounded synthetic source synopsis and a single-output target. | `CASE_PREPARED` |
| `VC-08` | `edge-case`, `missing-attachment`, `stop-condition-risk` | This catalog accurately declares that the missing deck and missing context are intentional and must remain unavailable. | `CASE_PREPARED` |

## Use Rules

- Do not add participant names, raw source documents, or confidential material to
  this file.
- Do not rewrite ambiguous or contradictory language before the session starts.
- Do not treat any case as approved, rejected, or successful before a recorded
  session outcome exists in the dated validation report.
- If a future round changes case scope materially, create a new dated catalog or
  append a revision note rather than overwriting the validation history.
