# Publication Package Contract

**Status:** Proposed post-MVP specialization
Applies to: Motiflow / ACDS runtime

## Purpose

The Publication Package is a post-MVP specialization that assembles already-approved MVP artifacts for publishing systems, editorial workflows, or channel-specific exports.

It is not the canonical MVP workflow output. The decisive MVP slice ends with the governed artifact chain through `Final Approval Record` and `Provenance Record`; the Publication Package wraps those records only after final approval.

## Core principle

> The Publication Package is an optional container built on top of approved canonical artifacts, not a replacement for them.

## Canonical MVP dependency chain

Every Publication Package must reference these canonical artifacts:

- Intake Package
- Normalized Brief
- Knowledge Fusion Package
- Creative Direction Package
- Direction Approval Record
- Generation Specification
- Generated Candidate Set
- Critic Evaluation Package
- Final Approval Record
- Provenance Record

## Specialized container shape

```yaml
publication_package:
  id:
  project_id:
  workflow_run_id:
  version:
  status:

  canonical_refs:
    intake_package_ref:
    normalized_brief_ref:
    knowledge_fusion_package_ref:
    creative_direction_package_ref:
    direction_approval_record_ref:
    generation_specification_ref:
    generated_candidate_set_ref:
    critic_evaluation_package_ref:
    final_approval_record_ref:
    provenance_record_ref:

  source:
    source_document_ids: []
    source_urls: []
    crawl_timestamp:
    source_hashes: []
    citations: []

  editorial:
    title:
    subtitle:
    summary:
    article_markdown:
    article_html:
    social_variants:
      linkedin:
      short_post:
      newsletter_intro:
    key_points: []
    call_to_action:
    hashtags: []

  visual:
    hero_asset_id:
    alternate_asset_ids: []
    creative_direction_id:
    generation_specification_id:
    caption:
    alt_text:
    credit_line:
    aspect_ratio:
    text_policy:

  metadata:
    slug:
    language:
    locale:
    topics: []
    audience: []
    publication_targets: []
    seo_title:
    seo_description:
    canonical_url:

  review:
    editorial_status:
    visual_status:
    factual_status:
    brand_status:
    overall_status:
    findings: []
    approvals: []

  provenance:
    source_versions: []
    engine_versions: []
    model_versions: []
    generation_spec_versions: []
    knowledge_versions: []
    human_edits: []

  exports:
    markdown_uri:
    html_uri:
    json_uri:
    image_uris: []
    manifest_uri:
```

## Required outputs

Every Publication Package must include:

1. A final title and article body.
2. Both Markdown and sanitized HTML representations.
3. A selected hero image or explicit `visual_pending` status.
4. Image caption and accessibility alt text.
5. Source provenance and citation references.
6. Editorial, visual, factual, and brand review status.
7. A machine-readable manifest.
8. Version and approval history.
9. References to the full canonical MVP artifact chain.

## Optional outputs

Depending on workflow configuration:

- LinkedIn-ready post;
- newsletter introduction;
- short executive summary;
- multiple language variants;
- SEO fields;
- social image crops;
- presentation-ready excerpt;
- CMS-specific payloads;
- scheduled publishing instructions.

## Content ownership

- Content engines may propose and revise editorial sections assigned to them.
- Creative engines may not rewrite factual article content.
- Visual critics may not mutate editorial content.
- Editorial critics may not replace the approved visual direction.
- The Publication Composer assembles validated components but must not silently change their meaning.
- Human edits create a new package version and are preserved in provenance.

## Markdown requirements

The Markdown export must:

- use UTF-8;
- preserve headings, lists, emphasis, links, and citations;
- use repository-approved front matter when configured;
- refer to images using stable asset identifiers or export-relative paths;
- avoid provider-specific temporary URLs;
- remain readable without the HTML version.

Example:

```markdown
---
title: "Example title"
slug: "example-title"
status: "review"
hero_image: "assets/hero-16x9.webp"
---

# Example title

Article body...

![Accessible visual description](assets/hero-16x9.webp)

*Caption explaining the relationship between the image and article.*
```

## HTML requirements

The HTML export must:

- be sanitized before storage or rendering;
- preserve semantic headings;
- include accessible image markup;
- exclude executable scripts;
- use configurable templates rather than model-generated page shells;
- support review rendering without requiring publication-system access;
- retain stable links between claims and citations.

## Review status model

```text
DRAFT
CONTENT_REVIEW_REQUIRED
VISUAL_REVIEW_REQUIRED
FACT_CHECK_REQUIRED
BRAND_REVIEW_REQUIRED
REVISION_REQUIRED
AWAITING_FINAL_APPROVAL
APPROVED
EXPORTED
PUBLISHED
```

Overall approval requires all configured mandatory review dimensions to pass.

## Packaging rules

- The package may be assembled only after a valid Final Approval Record exists.
- Article and image versions are pinned together at approval.
- Replacing the hero image after approval invalidates visual and final approval.
- Material editorial changes invalidate factual and final approval.
- Metadata-only corrections may use a configurable lightweight approval path.
- Exports must be reproducible from the approved canonical artifact versions.
- Publishing connectors may consume only an approved Publication Package unless an explicit preview mode is used.

## Recommended export directory

```text
publication-package/
├── article.md
├── article.html
├── manifest.json
├── citations.json
├── assets/
│   ├── hero-16x9.webp
│   ├── hero-linkedin.webp
│   └── thumbnail.webp
└── review/
    ├── findings.json
    └── approvals.json
```

## Acceptance criteria

The contract is satisfied when a user can:

- review the article and selected image in one workspace;
- compare article and image revisions;
- see which sources support the content;
- approve content and visual dimensions separately;
- export Markdown and HTML without copying from a chat response;
- reproduce the approved package from stored versions;
- send an approved package to a publishing connector without reformatting it manually.
