# Traceability Matrix — SKILL.md → EDSE v5.0

Maps every normative statement in `SKILL.md` and its references to its source
in EDSE v5.0 (`pablomillaquen/evidence-driven-software-evolution`,
`v5/EDSE-v5.0.md`). Adaptations introduced by the Agent Skills format are
listed separately in `references/ADAPTATIONS.md`.

## SKILL.md

| SKILL.md section / rule | EDSE v5.0 source | Type |
|------------------------|------------------|------|
| When to use (list) | §6 Boundary conditions (inverse) | Canonical |
| When NOT to use | §6 Boundary conditions | Canonical |
| Principle 1 evidence before assumption | §1.2 P-01 | Canonical |
| Principle 2 product value | §1.2 P-02 | Canonical |
| Principle 3 baseline differential | §1.2 P-03 | Canonical |
| Principle 4 acceptance (refactor) | §1.2 P-04 | Canonical |
| Principle 5 evidence requirement (refactor) | §1.2 P-05 | Canonical |
| Principle 6 execution transparency | §1.2 P-06 | Canonical |
| Principle 7 classification | §1.2 P-07 | Canonical |
| Principle 8 capability over control | §1.2 P-08 | Canonical |
| Workflow (precondition + 7 stages; RQs in stage 1) | §3.1 7-stage cycle | Adaptation (mapping) |
| Min E1 findings | Inherited v3 §2 | Inherited |
| Min E3 code changes | Inherited v3 §2 | Inherited |
| E4 performance | Inherited v3 §2 | Inherited |
| E0 not evidence for decision | Inherited v3 §2 | Inherited (clarification) |
| Do not assume / provenance | §3.2, P-07 | Clarification |
| Artifact traceability chain | §3.2 Cadena de Evidencia | Canonical |
| Evidence evolution chain | §11.3 Trazabilidad | Canonical |
| Freeze validated baselines | §3.1 stage 6 | Canonical |
| Reference vs change disambiguation | §3.4 Refactoring family | Canonical |
| Required artifacts | §13 How to apply (steps) | Canonical |
| Completion criteria | §3.1, §13 | Canonical |

## references/methodology.md

| Section | EDSE v5.0 source |
|---------|------------------|
| 7-stage cycle | §3.1 |
| Two evidence chains (artifact traceability §3.2, evolution §11.3) | §3.2, §11.3 |
| SPEC families | §3.4 |
| Principles 1–8 | §1.2 |
| Boundary conditions | §6 |
| Key facts (generative, compounding, invisibility) | §2, §5, §9 |
| Validation evidence | §12 |

## references/evidence.md

| Section | EDSE v5.0 source |
|---------|------------------|
| Evidence levels E0–E5 | Inherited v3 §2 (not in v5 §11) |
| E0 precision | Inherited v3 §2 (clarification) |
| Findings taxonomy | Inherited v3 §3 |
| Research questions | §11.2 (v5 canonical) |
| Candidate decisions | §3.3 (v5 canonical) |
| Artifact traceability chain | §3.2 (v5 canonical) |
| Evidence evolution chain | §11.3 (v5 canonical) |
| Provenance rule | §3.2, P-07 |

## references/artifacts.md

| Section | Source | Type |
|---------|--------|------|
| Findings log | v5 §11 | Canonical |
| Research questions | v5 §11.2 | Canonical |
| Candidate decisions | v5 §3.3 | Canonical |
| SPEC / change description | v5 §3 / §13 | Canonical |
| Baseline | v5 §3.1 / §13 | Canonical |
| Release / completion report | v5 §13 | Canonical |
| Evidence Level E1–E5 | v3 §6 | Inherited |
| Confidence (HIGH/MEDIUM/LOW) | v3 §6 | Inherited |
| Decision vs ADR | v3 §6 | Inherited |
| Decision Type (OPERATIONAL/TECHNICAL/ARCHITECTURAL) | v3 §6 | Inherited |

## references/patterns.md

| Section | Source | Type |
|---------|--------|------|
| 11 frozen patterns + evidence | v5 §4 | Canonical |
| Anti-patterns / "Always" lists | v3 §18, compatible with v5 (per-item v5 mapping noted) | Inherited |

## Summary

- **Canonical (v5.0)**: principles P-01–P-08, artifact traceability chain
  (§3.2), evidence evolution chain (§11.3), baseline freeze, SPEC families,
  boundary conditions, research questions, candidate decisions, findings log,
  SPEC/change description, baseline and release/completion-report structures.
- **Inherited (v3, compatible with v5)**: E0–E5 scale, E1/E3/E4/E0 gates,
  findings taxonomy, and from the artifact model — Evidence Level, Confidence,
  Decision-vs-ADR, and Decision Type. These are not restated in v5 and are not
  claimed as v5 canon.
- **Clarifications** (canonical implication made explicit, no new rule):
  E0-for-decisions, do-not-assume/provenance.
- **Adaptations** (pure presentation, no semantic change): English language,
  file split into SKILL.md + references/, 7-stage workflow with precondition
  mapping (research questions kept explicit inside Collect evidence).
