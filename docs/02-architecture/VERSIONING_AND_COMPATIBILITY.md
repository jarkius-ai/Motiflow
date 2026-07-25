# Motiflow Versioning and Compatibility Policy

**Status:** Proposed architecture freeze v0.1
**Owner:** Chief Architect

## Version domains

Version independently:

- artifact schemas;
- workflow definitions;
- engines and critics;
- connector interfaces;
- provider adapters;
- prompts and instructions;
- knowledge packs;
- public APIs;
- events.

Do not use one global product version to imply compatibility across every runtime component.

## Semantic versioning

Use `MAJOR.MINOR.PATCH`.

- **MAJOR:** incompatible contract or behavior change requiring migration.
- **MINOR:** backward-compatible capability or optional field.
- **PATCH:** backward-compatible correction with no contract expansion.

Pre-release versions may use `-alpha.N`, `-beta.N`, or `-rc.N`.

## Compatibility classes

Every contract change is classified as:

- **Compatible:** existing consumers continue without change.
- **Conditionally compatible:** existing consumers work under declared limits or feature negotiation.
- **Migratable breaking:** consumers require a documented migration.
- **Hard breaking:** no safe compatibility path exists and explicit replacement is required.

## Schema rules

Backward-compatible changes may include:

- adding optional fields with safe defaults;
- expanding an enum only when consumers must already handle unknown values;
- adding new artifact types;
- clarifying validation without rejecting previously valid content.

Breaking changes include:

- removing or renaming fields;
- changing field meaning or ownership;
- narrowing accepted values;
- changing requiredness;
- changing identifier semantics;
- changing confidence scale or units;
- altering immutable-history rules.

## API rules

- Public API versions are explicit in routes or media types.
- A deprecated API remains supported for a declared migration window.
- Deprecation includes replacement guidance and removal criteria.
- Error contracts are versioned with the API.
- Provider-native errors are never exposed as stable public contracts.

## Event rules

Events are immutable facts. Existing event meanings do not change.

Compatible evolution uses additive optional fields or a new event type. Breaking payload or semantic changes require a new major event version and parallel consumption during migration.

## Workflow rules

A running workflow remains pinned to the workflow, engine, instruction, schema, policy, and knowledge versions captured when the run starts unless an explicit migration or human override is recorded.

New workflow versions do not silently alter active runs.

## Engine rules

An engine declares accepted input schema ranges and produced output schema versions. The registry rejects an assignment when compatibility cannot be proven.

## Connector rules

Provider adapter upgrades may change internal provider syntax but must preserve the normalized connector contract. A provider change that alters output meaning, safety treatment, data handling, or reproducibility requires review and may require an ADR.

## Migration record

Every breaking change includes:

```yaml
migration:
  id:
  affected_contracts: []
  compatibility_class:
  from_versions: []
  to_version:
  migration_steps: []
  rollback_steps: []
  data_transform:
  validation:
  owners: []
  removal_date: null
```

## Architecture decision trigger

An ADR is required when a version change affects:

- component responsibility;
- dependency direction;
- canonical state ownership;
- security or privacy boundary;
- workflow semantics;
- artifact immutability;
- external publishing authority;
- compatibility policy itself.

## Freeze exit criteria

Runtime implementation may begin when:

- canonical envelopes are accepted;
- state transitions are accepted;
- ownership boundaries are accepted;
- compatibility policy is accepted;
- first workflow and artifact schemas are selected for implementation;
- unresolved changes are recorded rather than hidden in code.
