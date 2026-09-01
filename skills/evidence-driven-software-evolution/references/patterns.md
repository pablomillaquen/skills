# Patterns

Validated patterns you can reuse, and anti-patterns to avoid. Patterns in EDSE
emerge from repeated need and are frozen once validated through repeated use.
Do not invent new patterns when existing ones work.

> **On the freeze threshold.** Canonical v5 states a general "3+ SPECs"
> threshold, but its own record (below) shows per-pattern evidence varies
> (5+/4+/6+/3+/3+/5/4+/4+/2+). Reproduce the canonical evidence per pattern
> rather than imposing a uniform threshold.

## 11 frozen patterns (validated, v5.0)

The "Canonical evidence" column reproduces the *Evidencia* column of v5.0 §4
(verified field-by-field against `v5/EDSE-v5.0.md` §4).

| # | Pattern | Frozen | Reusability | Canonical evidence (v5 §4) |
|---|---------|--------|-------------|----------------------------|
| 1 | Standardized SPEC structure | SPEC-010 | High | 5+ SPECs |
| 2 | Given/When/Then scenarios | SPEC-005 | High | 4+ SPECs |
| 3 | Evidence-based decision flow | SPEC-020 | High | 6+ SPECs |
| 4 | Baseline freeze pattern | SPEC-013 | High | 4+ SPECs |
| 5 | Product value principle | SPEC-014 | High | 4+ SPECs |
| 6 | Classification principle | SPEC-018 | High | 3+ SPECs |
| 7 | Phased execution model | SPEC-019 | High | 3+ SPECs |
| 8 | ISO certification pattern | SPEC-026 | Medium | 5 SPECs |
| 9 | Traceability matrix | SPEC-010 | High | 4+ SPECs |
| 10 | Capability-based assessment | SPEC-021 | High | 4+ SPECs |
| 11 | Capability health tracking | SPEC-023 | High | 2+ SPECs |

Reuse these before designing new ones. Being frozen means they have stopped
changing because evidence showed they work.

## Anti-patterns — never

*Inherited operational list from v3 §18, retained as compatible with v5 (each
item's violated principle is noted where it maps to a v5 principle).*

- ❌ Optimize without measuring (violates Measure First; v5 P-01 evidence)
- ❌ Refactor without evidence of need (violates Evidence Over Intuition; v5 P-05)
- ❌ Skip regression testing (violates Regression First; v5 §3.1 stage 5)
- ❌ Make decisions on E0 evidence (violates Evidence Levels; *inherited v3*)
- ❌ Create new patterns when existing ones work (violates Guardrails; v5 "Do
  not invent new patterns" / frozen-pattern practice)
- ❌ Forget to document why something was NOT done (violates Traceability; v5 P-06)
- ❌ Allow technical debt without a finding (violates Debt Model; *inherited v3*)
- ❌ Treat reports as "Completed" without documenting deviations (violates
  Execution Transparency, P-06)
- ❌ Reintroduce a regression by changing behavior during a refactor
  (violates Acceptance Principle, P-04)

## Always

*Inherited operational list from v3 §18, compatible with v5.*

- ✅ Measure before and after (E4 required for performance; *E4 gate inherited v3*)
- ✅ Document findings with evidence (min E1; *E1 gate inherited v3*)
- ✅ Run regression after every change (v5 §3.1 stage 5 Validate)
- ✅ Justify decisions with data (v5 P-01)
- ✅ Prefer existing architecture (v5 P-04 / refactor no-behavior-change)
- ✅ Record deferred work with rationale (v5 P-06 transparency)
- ✅ Link every artifact in the traceability chain (v5 §3.2)
