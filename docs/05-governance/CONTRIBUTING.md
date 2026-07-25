# Contributing to Motiflow

## Before changing the system

1. Read `PROJECT_CHARTER.md` and `MASTER_CONTEXT.md`.
2. Locate the relevant product and architecture documents.
3. Check existing ADRs.
4. Define the affected artifact contracts and success criteria.
5. State assumptions and unresolved questions explicitly.

## Change categories

### Documentation-only clarification
May proceed without an ADR when meaning and behavior do not change.

### Product behavior change
Update the PRD, user journey, success metrics, and acceptance criteria.

### Architecture or contract change
Create or update an ADR before implementation.

### Provider integration change
Keep provider-specific behavior behind an adapter and document data handling, retry, timeout, cost, and fallback behavior.

## Pull request expectations

A pull request should explain:

- Problem and intended outcome
- Scope and non-goals
- Documents and contracts affected
- Architecture decision reference
- Testing and evaluation evidence
- Security, cost, and operational implications
- Migration or rollback requirements

## Quality bar

Changes should be understandable by a new engineer without relying on undocumented chat context. Important behavior must be represented in source, schemas, tests, or canonical documentation.
