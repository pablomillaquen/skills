# Agent Skills Adaptations

This file documents every adaptation introduced when packaging EDSE v5.0 as an
Agent Skill. It separates what is canonical EDSE from what is an adaptation
required (or chosen) for the Agent Skills format, so that packaging never
silently changes the methodology.

## 1. Language: English SKILL.md

- **Canonical EDSE v5.0**: Spanish.
- **Adaptation**: `SKILL.md` and `references/` are written in English for
  international discovery and use.
- **Rationale**: Global discoverability on skills.sh.
- **Traceability**: The canonical Spanish document remains the authoritative
  source for exact wording.

## 2. Operational workflow mapping

- **Canonical**: The 7-stage evolution cycle (v5 §3.1).
- **Adaptation**: A **precondition** establishes the current baseline before
  the seven-stage cycle runs. Research questions are handled explicitly at the
  start of Stage 1 (*Collect evidence*) to make the cycle operational for
  agents and prevent "explore first, ask later" behavior.
- **Rationale**: Same semantics as the canonical cycle, adapted to an agent's
  stepwise mode of operation. The precondition is an operational prerequisite
  for executing the cycle, not a cycle stage.
- **Status**: Presentation / operational mapping. It does **not** introduce an
  eighth EDSE stage; the cycle remains seven stages.

## 3. Language of "Mandatory constraints" — precision

- **Source**: The evidence-level gates (min E1 findings, min E3 code changes,
  E4 performance, E0 not evidence) are **inherited operational knowledge from
  v3** (not restated in canonical v5.0).
- **Adaptation**: Their wording in `SKILL.md` is clarified for agent use,
  notably: **E0 is a classification (opinion) but is not acceptable evidence
  for a decision.**
- **Status**: Source is inherited v3; the presentation is clarified to prevent
  misinterpretation. No new or changed methodology.

## 4. Provenance / no-over-interpretation rule

- **Canonical**: Implicit in the evidence model (P-07 classification, evidence
  chain). Not stated verbatim as an operational rule for agents.
- **Adaptation**: Added as an explicit operational principle: *do not treat
  observations, assumptions, or inferred states as established facts; make
  uncertainty explicit and preserve provenance.*
- **Rationale**: Agents have a tendency to fill gaps with inference. This makes
  a canonical implication explicit for agent behavior.
- **Status**: Explicit statement of a canonical implication — no new
  restriction beyond what the evidence model already requires.

## 5. File structure

- **Canonical**: Single large document (`v5/EDSE-v5.0.md`).
- **Adaptation**: Split into `SKILL.md` + `references/` following the Agent
  Skills progressive-disclosure format.
- **Rationale**: The spec recommends keeping `SKILL.md` < 500 lines and moving
  depth to `references/`.

## 6. Versioning policy

This package is **EDSE Agent Skill v1.0** (a packaging version, not an EDSE
version). It represents:

- **EDSE v5.0 canonical methodology**, plus
- **compatible operational knowledge inherited from earlier EDSE versions
  (v3)** — the E0–E5 scale and gates, the findings taxonomy, and the
  decision-recording / Decision-vs-ADR convention, all retained because they
  remain compatible with v5 — plus
- **agent-specific presentation**.

It does **not** claim to be "EDSE v5.1" and it does **not** make v3 and v5
equivalent. Inherited (v3) rules are explicitly marked as `inherited from v3`
wherever they appear; v5 remains the authoritative canonical source. Any rule
not marked inherited and not an explicit agent adaptation is canonical v5.

## Summary of new semantics

No new EDSE semantics were introduced. Adaptations fall into these roles:

- **Presentation** (language, file split, workflow mapping),
- **Clarifications** (making explicit what EDSE already implies):
  do-not-assume/provenance; and for E0-for-decisions, its *source* is
  **inherited from v3** while its *wording* here is clarified for agents, or
- **Inherited operational knowledge from v3**, retained as compatible with v5
  (marked `inherited from v3`).

If any of the above is later judged to have changed EDSE meaning, it must be
revised before publishing. Canonical methodology lives in
`pablomillaquen/evidence-driven-software-evolution` (`v5/EDSE-v5.0.md`).
