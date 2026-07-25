# Success Metrics

**Status:** Supporting product specification
**Owner:** Product
**Scope:** Motiflow outcome measures and success criteria

Motiflow measures success across strategic quality, creative quality, operational performance, trust, and business outcomes.

## North Star

**Percentage of projects that move from a validated brief through approved creative direction to a final approved candidate without restarting the strategy.**

## Product metrics

- Time from submitted brief to approved direction
- First-review approval rate
- Average number of revision cycles
- Direction usefulness score
- Rationale clarity score
- Final candidate acceptance rate
- Candidate revision count
- Percentage of reused knowledge and approved components
- Workflow completion rate
- User adoption by role and workspace

## Quality metrics

- Brief completeness score
- Strategic alignment score
- Narrative coherence score
- Brand compliance score
- Constraint satisfaction rate
- Human-versus-critic agreement rate
- Final asset acceptance rate

## System metrics

- Workflow success and failure rates
- Node latency by engine and provider
- Retry and escalation rates
- Artifact validation failure rate
- Cost per completed workflow
- Provenance completeness
- Mean time to recover from failed jobs

## Trust metrics

- Percentage of consequential decisions with recorded rationale
- Percentage of released assets with complete provenance
- Policy violation and false-positive rates
- Human override frequency
- Access and audit coverage

## Initial MVP targets

Targets must first be baselined through [`MVP_VALIDATION_PLAN.md`](MVP_VALIDATION_PLAN.md), then recalibrated during pilot use. The MVP should demonstrate:

- A complete brief-to-final-approved-candidate workflow with both human gates
- Baseline measurement across 5–10 representative briefs and 2–3 intended users or design partners
- Reliable schema validation between every node
- Selective reruns after feedback
- Separate human direction and final-candidate approval gates
- Full version history and provenance for every approved direction and final candidate
- Measurable improvement in time to approved direction compared with the baseline workflow
- Measurable reduction in avoidable revision cycles compared with an unstructured prompting workflow

## Pre-build baseline measures

- Time from source brief to an approved creative direction using the current manual process
- Number of direction revision cycles before approval
- Intended-user rating of direction usefulness
- Intended-user rating of rationale clarity
- Percentage of briefs that require clarification before direction can be approved
- Number of candidate revisions before final approval
