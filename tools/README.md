# Tools

## check-docs

Documentation-governance checker. Verifies, across all tracked Markdown and
YAML files:

- **LINKS** — every relative Markdown link and image target resolves to an
  existing file or directory, including `#anchor` references to headings
  (GitHub-style slugs). External `http(s)`/`mailto` links and links inside
  fenced code blocks are skipped; anchors that cannot be resolved confidently
  are reported as warnings, not errors.
- **YAML** — `CONTEXT_INDEX.yaml`, `MEOS/roles.yaml`, and any other tracked
  YAML file parse cleanly (requires PyYAML; skipped with a warning if absent).
- **METADATA** — every `.md` file under `docs/01-product/`,
  `docs/02-architecture/`, and `docs/03-delivery/` has a top-level H1 and a
  `**Status:**` line within its first 15 lines.
- **ROUTING** — every path or glob root referenced in `CONTEXT_INDEX.yaml`
  `required:`/`require:` lists and `MEOS/roles.yaml` `reads:` lists exists on
  disk, unless the line carries a `# planned` comment.
- **ADR** — files in `docs/adr/` match `ADR-NNNN-kebab-case.md`, their H1
  starts with `# ADR-NNNN:` matching the filename number, and numbers are
  unique.
- **TASK STATES** — task frontmatter in `MEOS/tasks/*.md` uses only the
  canonical MEOS/19 vocabulary (`PROPOSED`, `READY`, `IN_PROGRESS`, `REVIEW`,
  `LOOP`, `BLOCKED`, `ACCEPTED`, `RELEASED`).

Exit code is 0 only when there are zero errors.

### Run locally

```sh
./tools/check-docs
# or
python3 tools/check-docs
```

Python 3 standard library only; PyYAML is optional (without it, YAML and
routing checks are skipped with a warning). CI runs the same command via
`.github/workflows/docs-check.yml`.

### Freeze exemption

This is documentation-governance tooling, not a product implementation
artifact. Its creation was explicitly approved by the accountable owner
(Jarkius) on 2026-07-26 as exempt from the pre-implementation freeze in
docs/03-delivery/PENDING_WORK_TO_READY.md, which prohibits product
implementation artifacts while Task 001 is blocked. The Task 001 validator
entrypoint `./tools/validate-decisive-slice-contracts` remains a separate,
still-pending deliverable.
