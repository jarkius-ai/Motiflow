# Motiflow Documentation Normalization Report

**Status:** Phase 2 baseline complete
**Owner:** Documentation and Chief Architect
**Review date:** 2026-07-25

## Scope

This report records the first repository-wide documentation normalization pass following the foundation alignment. It classifies document responsibilities, identifies overlap, and defines safe follow-up actions. It does not delete, archive, or move existing artifacts.

## Result

The repository now has one canonical bootstrap route, explicit document authority, stable terminology, a document index, a glossary, a repository migration plan, and an architecture dependency map.

The largest source of confusion was not contradictory architecture. It was duplicated navigation and authority claims across root and MEOS documents. PR #1 resolves that issue by making `START_HERE.md` the sole onboarding router while preserving MEOS as engineering governance.

## Classification

### Authoritative root documents

| Document | Authority |
|---|---|
| `START_HERE.md` | Onboarding and navigation |
| `PROJECT_CHARTER.md` | Product vision, mission, scope, principles, and pillars |
| `MASTER_CONTEXT.md` | Stable product and architecture context |
| `CONTEXT_INDEX.yaml` | Machine-readable role and task routing |
| `MEOS/20_PROJECT_BOOTSTRAP.md` | Current engineering state and continuation |

### Foundation documents

The `docs/00-foundation/` collection controls documentation authority, vocabulary, target repository structure, migration sequencing, quality review, navigation, glossary, and normalization findings.

### Product documents

Documents under `docs/01-product/` elaborate product requirements, personas, journeys, scope, and success criteria. They are subordinate to the Project Charter and must align with the Master Context.

### Architecture documents

Documents under `docs/02-architecture/` elaborate runtime components, contracts, data flows, security boundaries, deployment boundaries, and dependency direction. Architecture-significant changes require ADR review.

### Engineering governance

Documents under `MEOS/` define how work is prepared, executed, verified, reviewed, and released. MEOS is authoritative for delivery governance but subordinate to accepted product and architecture authority.

### AI and design documents

Documents under `docs/04-ai/` and `docs/05-design/` define bounded AI-engine behavior, evaluation, design language, and UX/design contracts. They must use canonical package and architecture boundaries.

## Overlap findings

### Onboarding overlap — resolved

Previously, `README.md`, `START_HERE.md`, `CONTEXT_INDEX.yaml`, and `MEOS/20_PROJECT_BOOTSTRAP.md` presented different starting sequences. The canonical route is now:

1. `START_HERE.md`
2. `PROJECT_CHARTER.md`
3. `MASTER_CONTEXT.md`
4. `CONTEXT_INDEX.yaml`
5. `MEOS/20_PROJECT_BOOTSTRAP.md`
6. task-specific documents

### Product identity overlap — resolved

Motiflow is the product, ACDS is the product architecture, and MEOS is the engineering operating system. ADR-0001 records this relationship.

### Repository structure overlap — controlled

Several documents describe repository structures at different stages. `REPOSITORY_STRUCTURE.md` is now the canonical target-state reference. Other trees must be labelled current, transitional, or historical.

### Architecture summary duplication — controlled with boundaries

`MASTER_CONTEXT.md`, product specifications, and detailed architecture documents may each summarize the architecture for different audiences. Summaries are acceptable when they link to the canonical source and do not redefine component responsibilities.

### MEOS duplication — review during later cleanup

MEOS documents intentionally repeat some non-negotiable rules for operational safety. Duplication should only be removed where it creates conflicting authority or maintenance risk. Safety-critical repetition is not automatically a defect.

## Link review

The foundation changes use repository-relative links and exact known paths. A complete automated Markdown-link check is still pending because no CI validator currently exists.

Until automation is introduced, every documentation PR must apply `DOCUMENTATION_QUALITY_CHECKLIST.md` and verify changed links manually.

## Archive candidates

No file is archived in this phase. A document becomes an archive candidate only when:

- a canonical successor exists;
- all active inbound references are identified;
- the document has no unique operational or historical value that belongs in active navigation;
- a transition note names the successor;
- the move is performed in a focused, revertible PR.

## Duplicate-handling policy

When two documents overlap:

1. identify their authority and audience;
2. select one canonical home for each decision;
3. replace duplicate normative prose with a concise summary and link;
4. preserve useful examples as supporting content;
5. archive rather than delete when historical traceability matters;
6. update machine-readable routing and inbound references in the same change.

## Phase 2 completion criteria

- [x] Canonical bootstrap established.
- [x] Document authority defined.
- [x] Foundation identity terminology normalized; decisive-slice artifact vocabulary remains review-ready pending human acceptance.
- [x] Document index created.
- [x] Glossary created.
- [x] Architecture dependency map created.
- [x] Duplication and archive policy recorded.
- [x] Existing files preserved; no destructive cleanup mixed into normalization.
- [ ] Automated link and metadata validation implemented in CI.
- [ ] Every supporting document has explicit metadata.
- [ ] Archive candidates confirmed through a separate review.

The unchecked items require implementation work and should be handled by the repository validator phase rather than by manually rewriting every document in one large PR.

## Recommended next change

Create a separate architecture-contract branch from this normalization branch and add:

1. canonical package envelope schema;
2. workflow definition schema;
3. engine interface specification;
4. connector interface specification;
5. event envelope and event catalog;
6. workflow state-machine specification;
7. error taxonomy and retry classification;
8. compatibility and versioning policy.

That change should freeze interfaces before runtime implementation begins.
