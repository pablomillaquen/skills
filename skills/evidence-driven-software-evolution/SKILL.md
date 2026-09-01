---
name: evidence-driven-software-evolution
description: >
  Evolve an existing software system with evidence, traceability, and
  architectural control. Investigate before changing, produce findings and
  research questions from verifiable evidence, make traceable decisions,
  apply controlled changes, and validate with regression before freezing a
  new baseline. Use when modernizing, refactoring, hardening, documenting,
  or otherwise evolving a long-lived software system where correctness and
  accountability matter.
license: MIT
compatibility: Designed for coding agents that can read code, run static
  analysis and tests, record decisions, and inspect version history.
---

# Evidence-Driven Software Evolution (EDSE)

EDSE is a methodology for evolving software systems where every change is
backed by evidence, every decision is traceable, and every validated state is
frozen as an immutable reference. It does not replace engineering judgment —
it structures it. It structures the way you **decide** what to do and how you
**prove** it was done right.

This is **EDSE Agent Skill v1.0** — the operational interface for an agent
applying EDSE. It is based on the canonical **EDSE v5.0** methodology
(`references/methodology.md`) and additionally incorporates a small set of
compatible operational conventions inherited from earlier EDSE versions
(notably v3) that remain consistent with v5. Nothing here is a new EDSE
version and it does not extend the canonical methodology; where a rule is not
canonical v5 it is explicitly marked "inherited". See the traceability table
at the end and `references/ADAPTATIONS.md`.

## When to use

Apply this skill when the task involves evolving an existing software system
and correctness, safety, or accountability matter:

- Legacy modernization or technology migration
- Large refactoring with strict no-behavior-change expectations
- Production hardening or technical debt reduction
- Compliance or certification work (e.g., ISO 27001)
- AI-assisted changes where each modification must be justified and validated
- Long-lived systems where the team must reconstruct *why* things changed

**Do not** force EDSE onto throwaway prototypes, weekend hacks, projects under
one week, or simple CRUD apps with no compliance pressure (see
`references/methodology.md` → Boundary conditions). If the overhead outweighs
the benefit, say so instead of over-applying the process.

## Core principles

These are EDSE's fundamental principles. They govern every decision you make.

1. **Evidence before assumption (P-01).** Every decision is grounded in at
   least one source: user requirements, regulation, standards, technical
   documentation, or test evidence — not intuition.
2. **Product value (P-02).** Justify each unit of work by the value it adds to
   the product. Methodological improvement is a secondary result, never the
   primary goal.
3. **Baseline differential rule (P-03).** When you detect a regression, the
   first mandatory action is comparing the system against the last validated
   baseline before forming new hypotheses.
4. **Acceptance principle for refactoring (P-04).** A successful refactor
   produces no observable behavior change — only internal implementation
   changes.
5. **Evidence requirement for refactoring (P-05).** No refactoring proceeds
   without evidence that the structural problem actually exists.
6. **Execution transparency (P-06).** Record every deviation found during
   execution in the final report, whether or not it was resolved.
7. **Classification (P-07).** An observation of type X is not evidence of a
   conclusion of type Y. Do not overstate what a piece of evidence shows.
8. **Capability over control (P-08).** Evaluate ISO controls through
   capabilities, not individually: Product → Capability → Standard
   (only relevant when certification applies).

## Operating workflow

This is an **operational instantiation of EDSE's 7-stage evolution cycle**
(v5 §3.1) adapted for how an agent works interactively. It introduces no new
methodology: a **precondition** (establishing the baseline) precedes the cycle,
and each of the 7 EDSE stages maps to one agent action.

**Precondition — establish the baseline.** Identify the current validated state
of the system before starting the cycle: version/tag, existing tests, known
deferred work. (This is an operational precondition for executing the cycle,
not an EDSE cycle stage — the cycle has seven stages.)

**EDSE cycle (v5 §3.1, 7 stages):**

1. **Collect evidence (min E1)** — First formulate or confirm the research
   questions that define the uncertainty you need to resolve; then gather
   evidence to answer those questions. Never go looking for evidence without
   knowing which uncertainty it must resolve.
2. **Analyze** — Understand the current state; produce findings: observed
   facts, derived from evidence (not opinion), classified by category and
   confidence.
3. **Decide** — Choose a course of action; record the applicable evidence
   level *(inherited operational convention — see `references/evidence.md`)*
   and separate operational decisions from architectural ones (ADR) using the
   inherited Decision/ADR convention.
4. **Apply controlled change** — Change incrementally with risk control. A
   refactor must not change observable behavior (P-04); if it would, treat it
   as a new candidate decision, not a refactor.
5. **Validate with regression** — Prove existing behavior stays intact and the
   change achieved its intended effect.
6. **Freeze the baseline** — Confirm the validated state as the new immutable
   reference.
7. **Capture knowledge** — Record decisions and deviations (P-06); feed the
   next iteration.

Loop back to stage 1 for each open question. The cycle repeats continuously.

## Mandatory constraints

These are precise, traceable constraints — do not widen or narrow them.

The following are **inherited operational conventions** from earlier EDSE
versions (v3). They are retained because they remain compatible with canonical
v5, but they are not restated in v5.0 itself. Treat them as agent-operational
gates, not v5 canonical rules.

- **Minimum E1 for findings** *(inherited from v3)* — a finding must derive
  from code inspection or better; it cannot rest on assertion.
- **Minimum E3 for code changes** *(inherited from v3)* — any code change must
  have tests proving it.
- **E4 for performance claims** *(inherited from v3)* — performance claims
  require a measured before/after metric.
- **E0 never evidences a decision** *(inherited from v3)* — opinion is never
  sufficient evidence to decide. (E0 labels an unverified opinion; see
  `references/evidence.md` for the E0–E5 scale. E0 ≠ "opinions are banned" — it
  means opinion is not decision evidence.)

**Do not assume.** **Do not treat observations, assumptions, or inferred
states as established facts.** Make uncertainty explicit and preserve
provenance for every claim. This is a core operational rule when working
with agents: never fill gaps with inference and present them as facts.
- **Trace every change through the artifact traceability chain.** Every change
  must be traceable through the chain EDSE calls *Cadena de Evidencia* (v5
  §3.2): **SPEC → Decision → Implementation → Evidence → Finding → Capability →
  Pattern → Assessment**. This is the artifact-traceability chain: what links
  the outputs of a unit of work.
- **Follow the evidence evolution chain.** The per-change trace from evidence
  to the baseline (v5 §11.3) is: **Evidence → Finding → Candidate Decision →
  Research → Strategy → Implementation → Validation → Baseline**. This is the
  evolutionary flow a single change follows. Keep the two distinct: the former
  links artifacts, the latter is the process a change follows.
- **Freeze validated baselines.** A validated state is frozen as an immutable
  reference (v5 §3.1 stage 6). Baselines are immutable once frozen; new work
  starts from the last frozen baseline.
- **Reference vs change disambiguation.** When behavior would change during a
  refactor, do not silently expand the refactor — register it as a candidate
  decision and let evidence determine the path.

## Required artifacts

Keep these artifacts for the evidence trail (see `references/artifacts.md`):

- **Findings log** — observed facts, category, severity, confidence, evidence
  link, status (open/mitigated/closed).
- **Research questions** — explicit questions, each linked to a finding.
- **Decision records** — decision, evidence level, confidence, status; only
  architectural decisions become ADRs.
- **SPEC / change description** — what and why, frozen during implementation.
- **Baseline record** — version/tag, regression results, functional state,
  deferred debt, ADRs.
- **Completion report** — objectives, deviations noted (P-06), evidence,
  metrics, and the new baseline.

## Completion criteria

A unit of work is complete when:

- Every decision is backed by evidence recorded with its provenance.
- Every changed behavior is validated by regression (no new regressions).
- Deviations encountered are documented, resolved or not (P-06).
- A new baseline is frozen or explicitly deferred with justification.
- The evidence chain from finding → decision → change → validation → baseline
  is intact.

## References

Load these on demand:

- `references/methodology.md` — EDSE v5.0 summary, 7-stage cycle, SPEC
  families, boundary conditions.
- `references/evidence.md` — evidence model; E0–E5 scale and gates (inherited
  v3, marked as such).
- `references/artifacts.md` — SPEC, ADR, baseline, release, health report.
- `references/patterns.md` — 11 frozen patterns and known anti-patterns.

Original canonical methodology: `pablomillaquen/evidence-driven-software-evolution`
(`v5/EDSE-v5.0.md`).

## Traceability to EDSE v5.0

| This skill                        | EDSE v5.0 source                                |
|-----------------------------------|-------------------------------------------------|
| Core principles 1–8               | §1.2 Principles P-01…P-08                       |
| Workflow (precondition + 7 stages) | §3.1 7-stage cycle (operational instantiation)  |
| Artifact traceability chain       | §3.2 Cadena de Evidencia (SPEC→…→Assessment)    |
| Evidence evolution chain          | §11.3 Trazabilidad (Evidence→…→Baseline)         |
| E1/E3/E4/E0 gates                 | Inherited v3 (operational convention)           |
| SPEC families (in references)     | §3.4 SPEC families                              |
| Evidence model / findings         | §11 Model of Evidence                           |
| Boundary conditions               | §6 Boundary conditions (references)             |
| Provenance / no-over-interpret    | Adaptation for agents (see references/ADAPTATIONS.md) |
