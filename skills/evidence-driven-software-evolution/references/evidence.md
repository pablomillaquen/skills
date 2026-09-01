# Evidence Model

How evidence is classified, collected, and used in EDSE. Keep the distinction
between what something *is* and what it *proves* — an observation of type X is
not evidence of a conclusion of type Y (principle P-07).

> **Provenance (inherited).** The E0–E5 scale and its gates below come from
> operational documentation of EDSE v3 and are retained because they remain
> compatible with v5. They are **not** restated in canonical v5.0: v5 §11
> defines the evidence *model* (findings, research questions, traceability)
> but not the E0–E5 scale. Treat the scale and gates as inherited operational
> knowledge, not v5 canon.

## Evidence levels (E0–E5) *(inherited from v3)*

Evidence is classified from least to most reliable:

| Level | Name | Description | Example |
|-------|------|-------------|---------|
| E0 | Opinion | Subjective belief without data | "I think this is slow" |
| E1 | Code inspection | Reading code to understand behavior | "Controller has no validation" |
| E2 | Static analysis | Automated code analysis | PHPStan, ESLint results |
| E3 | Automated test | Test execution proving behavior | PHPUnit, Jest results |
| E4 | Measured metric | Quantified before/after comparison | "Response time: 0.3s → 0.1s" |
| E5 | Production observation | Real-world behavior monitoring | APM logs, error rates |

## Precise rules *(inherited from v3)*

- **Minimum E1 for findings.** A finding must be derived from code inspection
  or better. It cannot rest on assertion.
- **Minimum E3 for code changes.** Any code change must have tests proving it.
- **E4 required for performance claims.** Performance claims require a measured
  before/after metric.
- **E0 never qualifies as evidence for a decision.** Opinion is never sufficient
  evidence to decide.

### On E0 — avoid over-interpretation

E0 is a *classification* in the scale: it labels an unverified opinion as the
lowest level. That is not the same as saying **"you may never hold or state an
opinion."** The rule that matters for decisions is: an E0 opinion is **not
acceptable evidence** upon which to base or justify a decision. You may record
an opinion as context, but you must not treat it as evidence and you must mark
its provenance as opinion/unverified.

## Findings

A finding is an observed fact derived from evidence that identifies a problem
or an opportunity.

Properties:
- Derived from evidence, not opinion.
- Traceable to its data source.
- Classified by category and confidence.

### Finding taxonomy (categories)

Functional · Architecture · Performance · Security · Documentation ·
Compliance · Technical Debt · Regression · Usability

## Research questions

Research questions create clear research objectives with traceability.

Two types:
- **Evaluation research** — discovers Findings and Candidate Decisions.
- **Evolution research** — finds the implementation strategy for accepted
  decisions.

A research question bridges discovery and decision. Every question links to the
uncertainty it resolves.

## Candidate decisions

Candidate decisions are the mechanism by which the product evolves. They are
not a to-do list — they are intervention hypotheses resolved with evidence.

Properties:
- Define the business objective.
- Stay stable during implementation.
- Do not specify the technical solution.
- Can evolve according to research evidence.
- Resolve as IMPLEMENT, RETAIN, or DEFER.

**RETAIN is a valid decision.** When evidence shows the current version is
supported and an update introduces unnecessary risk, RETAIN is correct, not a
failure.

## Traceability

EDSE defines two distinct chains. Keep them separate — they answer different
questions.

### Artifact traceability chain (v5 §3.2)

How the artifacts of a unit of work relate to one another:

```
SPEC → Decision → Implementation → Evidence → Finding → Capability → Pattern → Assessment
```

### Evidence evolution chain (v5 §11.3)

The process a single change follows, from evidence to a new baseline:

```
Evidence → Finding → Candidate Decision → Research → Strategy → Implementation → Validation → Baseline
```

The two are complementary: the artifact chain links *outputs*; the evolution
chain is the *flow* a change traverses. A unit of work must be traceable along
both.

**Provenance rule.** Every claim carries its source: the evidence, its level,
and where it was obtained. If evidence is missing or ambiguous, say so — do not
fill gaps with inference presented as fact.
