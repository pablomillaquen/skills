# Methodology — EDSE v5.0 Summary

This is a concise operational summary of EDSE v5.0, the canonical methodology.
The authoritative source is `pablomillaquen/evidence-driven-software-evolution`
(`v5/EDSE-v5.0.md`).

EDSE is a methodology for evolving software systems with evidence,
traceability, and architectural control. It separates discovery, analysis,
decision, and execution into distinct phases, each producing evidence-based
artifacts. EDSE does not replace engineering judgment — it structures it.

EDSE is **generative**: it produces new methodological tools in response to
project needs, not from upfront design. Well-established patterns "freeze"
once validated.

## The 7-stage evolution cycle

Every change to the product follows this cycle:

```
1. Collect evidence   →  what shows the need for change
2. Analyze            →  understand current state, identify problems
3. Decide             →  approach, scope, limits
4. Controlled change  →  apply incrementally with risk control
5. Validate           →  prove no regression (build → tests → device)
6. Freeze baseline    →  confirm validated state as immutable reference
7. Capture knowledge  →  decisions, deviations, EDSE contributions
        └───────────────► next evidence
```

## The two evidence chains

EDSE defines two distinct chains; keep them separate.

**Artifact traceability chain** (v5 §3.2) — how artifacts of a unit of work
relate:

```
SPEC → Decision → Implementation → Evidence → Finding → Capability → Pattern → Assessment
```

**Evidence evolution chain** (v5 §11.3) — the process a single change follows
from evidence to a new baseline:

```
Evidence → Finding → Candidate Decision → Research → Strategy → Implementation → Validation → Baseline
```

Together they provide the structure for preventing unsupported claims,
maintaining traceability from conclusions to sources, and separating
observation from interpretation.

## SPEC families

| Family | Goal | Key rule |
|--------|------|----------|
| Validation | Verify product behavior | Evidence determines state |
| Recovery | Restore functional baseline | Repair before reverting |
| Evolution | Modernize technology | Revert before unresolved regression |
| Refactoring | Improve internal structure | No observable behavior change |
| Functionality | Add new capabilities | New value, new baseline |
| Certification | Prepare evidence for audit | Frozen certification pattern |

## Principles (8)

1. Evidence before assumption (P-01)
2. Product value (P-02)
3. Baseline differential rule (P-03)
4. Acceptance principle for refactoring (P-04)
5. Evidence requirement for refactoring (P-05)
6. Execution transparency (P-06)
7. Classification (P-07) — observation of type X is not evidence of type Y
8. Capability over control (P-08) — Product → Capability → Standard

## Boundary conditions

EDSE is **not** appropriate when:

- Projects under one week (insufficient time to collect evidence)
- Simple CRUD (< ~10 entities): overhead exceeds benefit
- Solo developers: no team-coordination benefit
- No compliance requirements: no certification pressure
- No AI assistance: documentation overhead prohibitive
- Very large systems (> 100 entities, > 50 developers): different approach

If the overhead outweighs the benefit, do not over-apply the process.

## Key facts (v5.0, from 29 SPECs)

- Validated through SIGES project, SPEC-001 through SPEC-029.
- **Generative**: 7 of 10 concepts emerged from need, not design.
- **Knowledge compounding**: each SPEC improves capacity to produce the next.
- **Methodological invisibility**: after ~SPEC-014 it becomes "just how we
  work" (mature methodology needs no conscious effort).
- **11 frozen patterns**, 18/28 reusable without modification (64%).
- **Capability-based assessment**: 45 ISO controls → 13 capabilities.

## Validation evidence

- 29 SPECs analyzed, 32 decisions documented, 45 findings tracked.
- 28 patterns identified (11 frozen), 10 emerging capabilities.
- 75% of improvements attributable primarily to EDSE (single case study;
  generalization requires more evidence).

*Spanish note:* the canonical document is in Spanish. For precise wording of any
rule, consult the canonical `v5/EDSE-v5.0.md`.
