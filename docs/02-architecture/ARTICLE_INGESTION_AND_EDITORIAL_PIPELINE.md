# Article Ingestion and Editorial Pipeline

Status: Proposed for architecture freeze

## Purpose

Integrate an existing daily article crawler that stores source articles as Markdown files with the Motiflow creative-direction workflow.

The crawler remains an upstream source producer. Motiflow ingests its Markdown outputs, validates and enriches them, generates editorial and visual artifacts, and assembles a review-ready Publication Package.

## Boundary

Motiflow does not need to replace the crawler.

```text
Existing Daily Crawler
        ↓
Markdown Source Files
        ↓
Ingestion Connector
        ↓
Source Normalization + Deduplication
        ↓
Editorial and Creative Workflow
        ↓
Publication Package
        ↓
Side-by-Side Review
        ↓
Markdown / HTML / CMS Export
```

## Ingestion modes

### Watched directory

Motiflow scans a configured directory or object-storage prefix for new Markdown files.

### Manifest handoff

The crawler writes a manifest containing file paths, source URLs, crawl timestamps, and hashes.

### API submission

The crawler submits the Markdown document and metadata through an authenticated ingestion endpoint.

### Repository ingestion

The crawler commits articles to a configured Git repository and Motiflow processes new or changed files.

The MVP should support watched-directory or manifest ingestion first because both preserve the crawler as an independent component.

## Source document contract

```yaml
source_document:
  id:
  source_type: crawled_article
  original_path:
  source_url:
  crawled_at:
  discovered_at:
  title:
  author:
  published_at:
  language:
  markdown:
  content_hash:
  crawler_version:
  metadata: {}
  attachments: []
  ingestion_status:
  duplicate_of:
  warnings: []
```

## Recommended front matter

The crawler may optionally write:

```yaml
---
source_url: https://example.com/article
source_title: Original article title
author: Author name
published_at: 2026-07-25T07:00:00Z
crawled_at: 2026-07-25T08:00:00Z
language: en
content_hash: sha256:...
topics:
  - enterprise-ai
crawler_version: 1.2.0
---
```

Missing metadata may be inferred, but inferred values must be identified as inferred rather than source-confirmed.

## Ingestion validation

The connector must validate:

- readable UTF-8 Markdown;
- non-empty article body;
- stable content hash;
- allowed file size;
- supported language or explicit unsupported-language status;
- safe file path;
- source URL format when supplied;
- duplicate and near-duplicate detection;
- absence of executable attachments;
- crawl timestamp and publication timestamp consistency.

## Deduplication

Use multiple signals:

1. exact content hash;
2. normalized source URL;
3. canonical URL metadata;
4. title and publication-time similarity;
5. semantic near-duplicate score.

A duplicate must not silently start a second full workflow. It should link to the earlier source and record whether the content is identical, updated, or syndicated.

## Editorial processing stages

```text
INGESTED
  ↓
NORMALIZED
  ↓
SOURCE_REVIEWED
  ↓
FACTS_EXTRACTED
  ↓
NARRATIVE_DEFINED
  ↓
ARTICLE_COMPOSED
  ↓
CREATIVE_DIRECTION_DEFINED
  ↓
VISUAL_GENERATED
  ↓
PACKAGE_ASSEMBLED
  ↓
MULTI-DIMENSION_REVIEW
  ↓
FINAL_APPROVAL
```

Independent stages may run in parallel after normalization:

- source and claim extraction;
- audience and business relevance analysis;
- topic classification;
- visual opportunity analysis;
- citation preparation.

Article composition and creative direction should converge through a shared narrative package so the written and visual outputs express the same dominant thesis.

## Editorial outputs

The pipeline should support these configurable content products:

- curated article summary;
- original commentary article;
- executive briefing;
- LinkedIn post;
- newsletter item;
- short social post;
- image caption;
- SEO summary;
- multilingual adaptation.

The system must distinguish source summarization from original commentary and preserve source attribution accordingly.

## Claims and citations

Every material factual claim should record:

```yaml
claim:
  id:
  text:
  source_document_ids: []
  source_spans: []
  evidence_status:
  confidence:
  requires_human_check:
```

The HTML and Markdown outputs should be renderable with citations while retaining a machine-readable citation map.

## Publication Composer

A dedicated Publication Composer assembles:

- approved editorial content;
- selected visual asset;
- captions and alt text;
- citations;
- metadata;
- review findings;
- approvals;
- Markdown and HTML exports.

The Composer is deterministic. It applies approved templates and formatting rules; it does not invent new facts or silently revise approved content.

## Failure handling

Examples:

- invalid Markdown → quarantine and report;
- empty or blocked source → mark ingestion failed;
- duplicate source → link and skip or process as update;
- insufficient evidence → require factual review;
- article and visual narrative conflict → route to narrative reconciliation;
- HTML sanitation failure → block export;
- missing hero image → permit content-only review when workflow policy allows.

## MVP integration

Recommended first implementation:

1. Configure one crawler output directory.
2. Read new `.md` files using a cursor or manifest.
3. Store original source unchanged.
4. Normalize front matter and calculate a content hash.
5. Create a SourceDocument record.
6. Run one editorial-plus-visual workflow.
7. Assemble one Publication Package.
8. Show article and image together for Guided approval.
9. Export `article.md`, `article.html`, `manifest.json`, and image assets.

## Success criteria

- New crawler-produced Markdown files are detected without manual copying.
- The original source remains immutable and traceable.
- Duplicate articles do not create unnecessary workflows.
- Written and visual outputs derive from one approved narrative.
- Reviewers can inspect article, image, sources, and findings together.
- Approved results export cleanly to both Markdown and HTML.
