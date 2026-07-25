# Data Contracts

**Status:** Review-ready architecture contract specification
**Owner:** Chief Architect
**Scope:** Versioned artifact, package, event, and data exchange contracts

Motiflow engines exchange explicit, versioned artifacts. JSON Schema is the initial machine-readable contract format; application types are generated from those schemas where practical.

## Current common-envelope draft

This example is one input to proposed ADR-0003, not the accepted decisive-slice
schema. Its versionless `parent_artifact_ids` cannot prove stale-parent
invalidation and must not be copied into Task 001 schemas.

Every artifact includes:

```json
{
  "artifact_id": "uuid",
  "artifact_type": "intake_package",
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

## Pending ADR-0003 decisive-slice overlay

The pending proposal replaces versionless parent IDs with
`parent_artifact_refs`. Each entry contains exactly `artifact_id`,
`artifact_type`, and positive integer `artifact_version`:

```json
{
  "parent_artifact_refs": [
    {
      "artifact_id": "uuid",
      "artifact_type": "knowledge_fusion_package",
      "artifact_version": 2
    }
  ],
  "created_by": {"type": "human|engine|system", "id": "string"}
}
```

The proposal remains unaccepted. If accepted, semantic validation must reject a
parent reference whose artifact does not exist, stored type differs, or version
is no longer the current non-invalidated dependency version. `created_by` has
only `type` and `id`; approval role remains under `payload.actor.actor_role`.

## Contract rules

- Use semantic versioning for schemas.
- Patch versions clarify without changing meaning.
- Minor versions add backward-compatible fields.
- Major versions may break compatibility and require migration.
- Required fields must be minimal and meaningful.
- Unknown fields should not silently affect decisions.
- Human-authored and machine-authored content must remain distinguishable.
- Claims derived from sources should carry evidence references.
- Validation occurs both before execution and before approval, export, or publication.

## Canonical decisive-slice vocabulary

The decisive workflow slice uses one canonical artifact vocabulary:

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

Supporting upstream analysis artifacts may still exist internally, but approval gates, runtime contracts, and system documentation should use the canonical names above for the decisive slice.

## Legacy alias mapping

| Legacy term | Canonical term | Notes |
|---|---|---|
| `CreativeBrief` | `Intake Package` | Raw submitted project input |
| `StrategicContext` | `Knowledge Fusion Package` | Use the fused, validated strategic handoff |
| `NarrativeStructure` | `Creative Direction Package` | Narrative structure becomes structured content inside the direction package |
| `MetaphorCandidateSet` | `Creative Direction Package` | Dominant metaphor selection resolves before direction approval |
| `PromptPackage` | `Generation Specification` | Canonical generation handoff; avoid `PromptPackage` in new contracts |
| `GeneratedAsset` | `Generated Candidate Set` | Generation yields a set, even when it contains one candidate |
| `EvaluationReport` | `Critic Evaluation Package` | Deterministic checks and critic findings travel together |
| `ApprovalDecision` | `Direction Approval Record` or `Final Approval Record` | Use the gate-specific canonical record |
| `ApprovedArtifactPackage` | `Generated Candidate Set`, `Final Approval Record`, and `Provenance Record` | Use the explicit gate and lineage artifacts instead of one umbrella term |

## Initial contract sequence

```text
Intake Package
→ Normalized Brief
→ Knowledge Fusion Package
→ Creative Direction Package
→ Direction Approval Record
→ Generation Specification
→ Generated Candidate Set
→ Critic Evaluation Package
→ Final Approval Record
→ Provenance Record
```

## Invalidation

A new artifact version invalidates only downstream artifacts whose declared dependencies include changed fields or claims. Field-level dependency declarations are preferred where implementation cost is justified.

At minimum:

- a new `Creative Direction Package` invalidates the `Direction Approval Record`, `Generation Specification`, `Generated Candidate Set`, `Critic Evaluation Package`, `Final Approval Record`, and `Provenance Record`;
- a new `Generation Specification` invalidates the `Generated Candidate Set`, `Critic Evaluation Package`, `Final Approval Record`, and `Provenance Record`;
- a new `Generated Candidate Set` or `Critic Evaluation Package` invalidates the `Final Approval Record` and `Provenance Record`.
