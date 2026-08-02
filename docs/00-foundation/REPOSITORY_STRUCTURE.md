# Repository Structure Standard

**Status:** Accepted foundation standard (accepted by Jarkius, 2026-07-26); the tree below remains a target structure  
**Migration mode:** Incremental and non-destructive

## Principles

- Organize by responsibility and artifact type, not by the history of how documents were added.
- Keep product architecture (ACDS), engineering governance (MEOS), and implementation packages distinct.
- Prefer stable plural top-level directories.
- Use lowercase kebab-case for implementation directories and files unless an established framework requires otherwise.
- Keep numbered document sections only where ordered reading is valuable.
- Do not create empty directories without a README or placeholder explaining their intended ownership.

## Canonical target structure

```text
Motiflow/
├── README.md
├── START_HERE.md
├── PROJECT_CHARTER.md
├── MASTER_CONTEXT.md
├── CONTEXT_INDEX.yaml
│
├── MEOS/                         # Engineering governance and delivery system
│
├── docs/
│   ├── 00-foundation/            # Authority, terminology, structure, principles
│   ├── 01-product/               # Vision, PRDs, personas, journeys, roadmap
│   ├── 02-architecture/          # System design, boundaries, contracts, data flows
│   ├── 03-delivery/              # Delivery planning and readiness controls
│   ├── 04-ai/                    # Engines, prompts, evaluations, safety, model strategy
│   ├── 05-governance/            # Engineering-governance guidance (transitional; see note)
│   ├── 05-design/                # UX, UI, design system, creative language (planned, not yet created)
│   ├── 06-operations/            # Deployment, observability, runbooks, security operations (planned, not yet created)
│   ├── adr/                      # Architecture Decision Records
│   └── archive/                  # Superseded, explicitly non-authoritative material
│
├── apps/
│   ├── studio/                   # Human-facing application
│   ├── api/                      # Public and internal API application
│   └── worker/                   # Background execution host, when justified
│
├── packages/
│   ├── creative-kernel/          # Governance and integrity runtime
│   ├── orchestrator/             # Workflow execution runtime
│   ├── engines/                  # Specialist reasoning implementations
│   ├── critics/                  # Quality evaluation implementations
│   ├── connectors/               # Provider and enterprise adapters
│   ├── schemas/                  # Machine-readable canonical contracts
│   ├── workflows/                # Versioned workflow definitions
│   ├── engine-sdk/               # Engine authoring interfaces
│   ├── connector-sdk/            # Connector authoring interfaces
│   └── shared/                   # Truly cross-cutting implementation utilities only
│
├── knowledge/                    # Governed knowledge assets and indexes
├── prompts/                      # Versioned prompt assets, not general documentation
├── evaluations/                  # Datasets, rubrics, fixtures, and benchmark results
├── examples/                     # Reference integrations and workflow examples
├── tools/                        # Repository and developer tooling
├── infrastructure/               # Deployment and environment definitions
└── diagrams/                     # Source diagrams not embedded with owning docs
```

The `docs/` subfolders that exist today are `00-foundation`, `01-product`, `02-architecture`, `03-delivery`, `04-ai`, `05-governance`, `adr`, and `archive`. `docs/05-governance/` holds engineering-governance guidance pending a future consolidation decision; `05-design/` and `06-operations/` are planned targets that have not yet been created.

## Naming conventions

### Directories

- Top-level and implementation directories: lowercase kebab-case.
- Use plural names for collections: `engines`, `connectors`, `workflows`, `schemas`, `evaluations`.
- Product applications may use stable product nouns: `studio`, `api`, `worker`.
- Avoid ambiguous directories such as `core`, `misc`, `new`, `final`, `temp`, or `common` without a narrowly defined contract.

### Markdown documents

- Root controlling documents retain uppercase snake case for visibility and compatibility.
- Ordered governance or specification sets may retain numeric prefixes.
- New standalone documents under `docs/` should use uppercase snake case only when they are controlling standards; otherwise use descriptive kebab-case.
- Never use suffixes such as `_FINAL`, `_LATEST`, `_NEW`, or version copies as authority markers. Use document metadata and Git history.

### Source packages

- Package directory names describe one bounded responsibility.
- Do not create a package for a future capability until an implementation or accepted contract exists.
- `shared` must not become a dumping ground; ownership and dependency direction must remain explicit.

## Dependency direction

```text
apps
  ↓
workflow/orchestration and domain packages
  ↓
SDKs, schemas, and narrowly scoped shared utilities
```

The Creative Kernel must not depend on provider connectors. Connectors must not own product workflows. Engines must exchange validated packages rather than call one another through hidden coupling.

## Transitional rule

Existing paths remain valid until a dedicated migration PR moves them. During transition:

- do not duplicate a document into both old and new locations;
- link to the current authoritative location;
- update references in the same change as each move;
- use redirects or small tombstone documents only when external links require them;
- record every architecture-significant rename in an ADR.
