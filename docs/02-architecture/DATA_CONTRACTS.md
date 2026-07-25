# Data Contracts

**Status:** Architecture contract specification
**Owner:** Chief Architect
**Scope:** Versioned artifact, package, event, and data exchange contracts

Motiflow engines exchange explicit, versioned artifacts. JSON Schema is the initial machine-readable contract format; application types are generated from those schemas where practical.

## Common envelope

Every artifact includes:

```json
{
  "artifact_id": "uuid",
  "artifact_type": "CreativeBrief",
  "schema_version": "1.0.0",
  "project_id": "uuid",
  "workflow_run_id": "uuid",
  "parent_artifact_ids": [],
  "created_at": "ISO-8601",
  "created_by": {"type": "human|engine|system", "id": "string"},
  "confidence": {"level": "low|medium|high", "basis": []},
  "provenance": [],
  "payload": {}
}
```

## Contract rules

- Use semantic versioning for schemas.
- Patch versions clarify without changing meaning.
- Minor versions add backward-compatible fields.
- Major versions may break compatibility and require migration.
- Required fields must be minimal and meaningful.
- Unknown fields should not silently affect decisions.
- Human-authored and machine-authored content must remain distinguishable.
- Claims derived from sources should carry evidence references.
- Validation occurs both before execution and before artifact publication.

## Initial contract sequence

```text
CreativeBrief
→ ResearchPack + AudienceProfile + BrandContext
→ StrategicContext
→ NarrativeStructure + MetaphorCandidateSet
→ CreativeDirectionPackage
→ PromptPackage
→ GeneratedAsset
→ EvaluationReport
→ ApprovalDecision
```

## Invalidation

A new artifact version invalidates only downstream artifacts whose declared dependencies include changed fields or claims. Field-level dependency declarations are preferred where implementation cost is justified.
