# Artifacts

The documents and records EDSE produces, and where they live. These give the
evidence trail that makes every change accountable.

> **Provenance (inherited).** The decision-recording convention in this file —
> Evidence Level (E1–E5), Confidence (HIGH / MEDIUM / LOW), Type
> (OPERATIONAL / TECHNICAL / ARCHITECTURAL), and the Decision-vs-ADR
> distinction — comes from EDSE v3 operational documentation and is retained
> as compatible with v5. It is not restated in canonical v5.0.

## Findings log

A systematic record of problems and opportunities.

Each finding has:
- SPEC reference (the unit of work that found it)
- Description
- Status (open / mitigated / closed)
- Category, severity, confidence
- Link to the evidence that supports it

## Research questions

Explicit questions created to resolve uncertainty about a finding. Each links
to the finding and the decision it will inform.

## Decision records

Chosen course of action supported by evidence.

Every decision records its Evidence Level and confidence:

```
## D-XXX: [Title]

**Status**: ACCEPTED / DEFERRED / REJECTED
**Type**: OPERATIONAL / TECHNICAL / ARCHITECTURAL
**Confidence**: HIGH / MEDIUM / LOW
**Evidence Level**: E1 / E2 / E3 / E4 / E5
**Date**: [Date]
```

### Decision vs ADR

> Every ADR is a Decision. Not every Decision deserves an ADR.

| Criteria | Decision | ADR |
|----------|----------|-----|
| Scope | Operational or technical | Architectural |
| Impact | Localized | System-wide |
| Duration | May be temporary | Permanent reference |
| Documentation | Decision template | ADR template |

## SPEC / change description

A structured document defining what will be done, why, and how it will be
validated. During implementation it is frozen — unexpected behavior registers
a new finding rather than silently changing scope.

Typical contents: objective, scope, research with justification, validation
scenarios, tasks with status, checklists (quality gates), evidence folder.

## Baseline record

A frozen, validated system state that becomes the foundation for future work.

Components: version (semantic + status tag), regression results, functional
state, performance (if measured), technical debt, ADRs, documentation.

Rules: every baseline has a git tag; every baseline includes regression
results; every baseline lists technical debt; baselines are immutable once
frozen.

## Release / completion report

Officially closes a unit of work and establishes a new baseline.

Required sections: executive summary, objectives, scope, work completed,
metrics, findings, ADRs, technical debt, baseline. Deviations found during
execution are recorded whether or not they were resolved (execution
transparency, P-06).
