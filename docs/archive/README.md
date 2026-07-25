# Documentation Archive

This directory preserves earlier generated documents, discussion exports, and superseded specifications.

## Archive rule

Preserve useful historical material, but do not treat it as current product or architecture truth.

Every imported document should begin with:

```text
Status: Archived
Canonical replacements: <paths>
Source date: <date if known>
Purpose: Historical reference and source material
```

## Consolidation workflow

1. Import the original without silently rewriting its meaning.
2. Compare it against current canonical documents.
3. Move enduring concepts into the proper current specification.
4. Convert material decisions into ADRs.
5. Record contradictions or unresolved questions.
6. Link the archive file to its canonical replacements.

## Pending imports

The earlier ACDS master-context and blueprint documents should be added here when their exact original contents are available. They should then be reviewed against `MASTER_CONTEXT.md`, `PROJECT_CHARTER.md`, and the current architecture specifications.
