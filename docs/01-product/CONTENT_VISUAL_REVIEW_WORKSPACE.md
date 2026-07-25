# Content and Visual Review Workspace

**Status:** Proposed post-MVP publication-specialization specification
**Scope:** Future combined editorial and visual publication review; not part of the decisive MVP slice

This document does not govern pre-build MVP validation or the first executable
creative-direction slice. For the MVP, an article may be source material for an
Intake Package, but article authoring, editorial approval, publication packaging,
CMS export, and social adaptation remain out of scope. The controlling MVP flow
is defined in [`../PRD.md`](../PRD.md) and
[`MVP_VALIDATION_PLAN.md`](MVP_VALIDATION_PLAN.md).

## Product outcome

A reviewer must be able to assess the written article and selected visual as one publication unit before approval or export.

## Primary layout

```text
┌──────────────────┬──────────────────────────────┬──────────────────────┐
│ Package / Runs   │ Article + Visual Canvas      │ Review and Decisions │
│                  │                              │                      │
│ Source           │ Title                        │ Overall status       │
│ Versions         │ Article preview              │ Editorial findings   │
│ Workflow         │ Hero image                   │ Visual findings      │
│ Assets           │ Caption + alt text           │ Fact checks          │
│ Exports          │ Citation indicators          │ Brand checks         │
└──────────────────┴──────────────────────────────┴──────────────────────┘
```

## Main review modes

### Publication preview

Shows the article and image as readers will experience them.

Views:

- desktop article;
- mobile article;
- LinkedIn post preview;
- Markdown source;
- sanitized HTML preview.

### Split comparison

Compare:

- source article against proposed article;
- article version against article version;
- image candidate against image candidate;
- complete package version against package version.

### Evidence view

Shows factual claims, supporting sources, confidence, and unresolved verification needs without exposing uncontrolled model chain-of-thought.

### Workflow view

Shows which engine produced each component, its status, cost, duration, versions, and upstream dependencies.

## Required reviewer actions

- approve editorial content;
- approve selected visual;
- approve factual accuracy;
- approve brand compliance;
- request revision for a specific component;
- lock approved title, narrative, image, or metadata;
- edit content with tracked changes;
- replace the selected image;
- compare alternatives;
- inspect source citations;
- export preview files;
- grant final package approval.

## Independent approvals

The interface must not reduce approval to one undifferentiated button.

```yaml
approval_dimensions:
  editorial:
  visual:
  factual:
  brand:
  accessibility:
  final_publication:
```

A project policy determines which dimensions are mandatory.

## Change-impact behavior

The UI must clearly show when an edit invalidates approval.

Examples:

- title typo correction: may preserve factual approval;
- claim revision: invalidates factual and final approval;
- hero-image replacement: invalidates visual and final approval;
- caption change: may invalidate accessibility and final approval;
- source update: marks affected claims and downstream artifacts stale.

## Article editor

The editor should support:

- Markdown-first authoring;
- rich preview without losing Markdown fidelity;
- tracked human changes;
- comments anchored to text ranges;
- citation insertion;
- heading and list validation;
- reusable content templates;
- side-by-side HTML rendering;
- automatic save as a new artifact version.

## Visual review

The visual panel should support:

- selected hero image;
- alternate candidates;
- zoom and crop previews;
- aspect-ratio previews;
- caption and alt-text review;
- prompt and generation-spec inspection;
- critic overlays and findings;
- explicit selection history.

## Review queue

Each package card should display:

- article title;
- source publication;
- crawl date;
- current hero thumbnail;
- workflow stage;
- required reviewer;
- unresolved findings;
- package age;
- publication target.

Recommended queues:

- New sources
- Content review
- Visual review
- Fact check
- Final approval
- Approved for export
- Revision requested
- Failed or blocked

## Export controls

After approval, the user can export:

- Markdown package;
- sanitized HTML package;
- JSON manifest;
- original and optimized image assets;
- LinkedIn-ready content;
- CMS connector payload.

Exports must identify the approved package version and must not silently use newer unapproved components.

## Success criteria

- A reviewer does not need separate applications to compare article and image.
- The relationship between the article thesis and visual metaphor is immediately understandable.
- Sources and factual findings are accessible from the article preview.
- Revision requests target the responsible workflow stage.
- Approval invalidation is visible before a reviewer confirms a change.
- Markdown and HTML exports match the approved preview.
