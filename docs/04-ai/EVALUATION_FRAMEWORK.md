# Evaluation Framework

**Status:** AI quality specification
**Owner:** AI Engineering and QA
**Scope:** Deterministic, semantic, critic, and human evaluation layers

Motiflow evaluates both intermediate reasoning artifacts and final creative outputs.

## Evaluation layers

1. **Schema validation** — required fields, types, versions, and references.
2. **Deterministic constraints** — dimensions, prohibited terms, format rules, policy, and brand exclusions.
3. **Specialist critics** — narrative, symbolism, visual quality, brand, business, and production readiness.
4. **Cross-artifact consistency** — alignment between brief, direction, prompt, output, and reviewer decisions.
5. **Human judgment** — approval, correction, ranking, and rationale.
6. **Outcome feedback** — downstream performance and real-world usage where available.

## Evaluation principles

- Do not collapse critical failures into an average score.
- Separate evidence-based findings from subjective preferences.
- Critics must cite the artifact fields or constraints behind findings.
- Confidence and disagreement are visible.
- The system should recommend action, not merely assign scores.
- Evaluation prompts, rubrics, models, and versions are recorded in provenance.

## Report structure

A `Critic Evaluation Package` includes scope, evaluator identities and versions, deterministic findings, critic findings, severity, supporting evidence, confidence, recommended action, blocking status, and links to affected artifact fields.

## Release gate

An artifact may be released only when blocking deterministic checks pass, required critics complete, policy thresholds are met, and the configured human approval is recorded.
