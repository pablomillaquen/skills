# Agent Skills — pablomillaquen

[![skills.sh](https://skills.sh/b/pablomillaquen/skills)](https://skills.sh/pablomillaquen/skills)

A catalog of publishable Agent Skills. Each skill follows the open
[Agent Skills](https://agentskills.io) standard (a directory with its
`SKILL.md`, `references/`, etc.) and can be installed by any
standards-compatible client.

## Catalog

| Skill | Version | Description |
|-------|---------|-------------|
| [Evidence-Driven Software Evolution](./skills/evidence-driven-software-evolution/) | **EDSE Agent Skill v1.0** | Evolve software systems with evidence, traceability, and architectural control. Investigate → find → decide → change → validate → freeze. |

---

# Evidence-Driven Software Evolution (EDSE)

**EDSE Agent Skill v1.0** — an operational skill for agents that evolve
long-lived software systems with evidence, traceability, and architectural
control.

This repository is the **distribution package**. The canonical methodology
lives in the separate, authoritative repository
[`pablomillaquen/evidence-driven-software-evolution`](https://github.com/pablomillaquen/evidence-driven-software-evolution)
(`v5/EDSE-v5.0.md`). This package is the *agent-facing* presentation of that
methodology and must not be confused with the canon.

## What it is

EDSE structures the way an agent **decides** what to do and how it **proves**
the work was done right:

- Investigate the current system **before** changing it.
- Produce **findings** and **research questions** from verifiable evidence.
- Make **traceable decisions** (operational vs architectural).
- Apply **controlled changes** (no undocumented behavior change).
- **Validate with regression** before freezing a new baseline.

Every change is backed by evidence, every decision is traceable, and every
validated state is frozen as an immutable reference.

## What's in the package

```
evidence-driven-software-evolution/
├── SKILL.md            # Operational interface: when to use, principles, workflow
├── TRACEABILITY.md     # Matrix mapping the skill back to EDSE v5.0 (canonical /
│                       # inherited v3 / adaptation / clarification)
└── references/
    ├── methodology.md  # The 7-stage cycle, two evidence chains, SPEC families,
    │                   # principles, boundary conditions
    ├── evidence.md     # Evidence levels E0–E5, findings, research questions,
    │                   # both evidence chains
    ├── artifacts.md    # Traceability-chain artifacts (findings, decisions,
    │                   # SPECs, baselines, release)
    ├── patterns.md     # 11 frozen patterns + anti-patterns
    └── ADAPTATIONS.md  # Explicit record of every packaging adaptation
```

`TRACEABILITY.md` is included on purpose: it documents *exactly* which parts of
the skill are canonical EDSE v5.0, which are compatible operational conventions
inherited from earlier EDSE versions (v3), and which are pure presentation
adaptations for the Agent Skills format. Nothing is silently changed.

## Versioning

- **EDSE Agent Skill v1.0** is a *packaging* version, **not** an EDSE version.
- It packages **EDSE v5.0** canonical methodology.
- Plus a small set of **compatible operational knowledge inherited from v3**
  (E0–E5 scale and gates, findings taxonomy, Decision/ADR convention), all
  explicitly marked `inherited` so nothing is claimed as v5 canon.
- It does **not** claim to be "EDSE v5.1" and does not make v3 and v5
  equivalent.

## Install / consume

Any tool that understands the open Agent Skills standard. For example, with a
standards-aligned CLI:

```
npx skills add pablomillaquen/skills
```

Then reference the skill as `evidence-driven-software-evolution`. Or clone this
repo and copy the
`skills/evidence-driven-software-evolution/` directory into your agent's
skills directory.

## Traceability to the canonical methodology

See [`skills/evidence-driven-software-evolution/TRACEABILITY.md`](./skills/evidence-driven-software-evolution/TRACEABILITY.md)
for the full matrix. The authoritative source is
[`pablomillaquen/evidence-driven-software-evolution/v5/EDSE-v5.0.md`](https://github.com/pablomillaquen/evidence-driven-software-evolution/blob/main/v5/EDSE-v5.0.md).

## License

MIT — see the `license` field in each `SKILL.md`.
