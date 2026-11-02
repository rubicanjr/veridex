# Veridex

**No black boxes. Just rules + sources.**

> **Status: early / active development.** This repository is a public skeleton,
> not a finished product. Nothing here should be treated as production-ready.

## What this is

Veridex is a **decision-support infrastructure** for individual investors. It is
rule-based, source-cited, and explainable by design: every output is meant to be
traceable back to an explicit rule and a named data source.

This open-source repository contains the intended skeleton for the K1/K2 layers
of the Veridex model:

- **K1** — a free weekly Transparency Report (planned)
- **K2** — a SaaS dashboard (planned)
- **K3** — an asynchronous custom ruleframe service (not part of this repo)

## What this is NOT

- **NOT investment advice.** Veridex does not recommend buying, selling, or
  holding any security. It is a decision-*support* tool only. Nothing produced
  by this project constitutes a recommendation, solicitation, or financial,
  legal, or tax advice. Users are responsible for their own decisions.
- **NOT a working product yet.** Modules under `src/` are placeholders. No
  engine currently executes.
- **NOT a performance claim.** There are no public metrics yet — no accuracy
  figures, no backtests, no user counts, no benchmarks. Any such numbers would
  be published separately with sources if they ever exist.

## The "no black boxes" philosophy

Most AI finance tools hide their reasoning inside opaque models. Veridex takes
the opposite stance: every signal must come from a human-readable rule, and
every rule must cite the data source it was evaluated against. If a conclusion
cannot be traced to a rule and a source, it does not ship. Explainability is a
hard architectural constraint, not a feature.

## Repository layout

```
.
├── .kiro/               # Kiro agentic configuration placeholder [VERIFY: Kiro docs]
├── docs/                # High-level documentation
│   └── ARCHITECTURE.md
├── src/                 # Skeleton modules (placeholders, no runnable code)
│   ├── rules/
│   └── sources/
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── LICENSE              # MIT
├── .env.example         # Key NAMES only, values intentionally empty
└── README.md
```

## Setup (placeholder)

Setup is **not finalized**. The intended flow, once code exists:

```bash
# 1. Clone
git clone https://github.com/<org>/veridex.git
cd veridex

# 2. Copy the example environment file and fill in YOUR OWN values.
#    Never commit real credentials. Values marked below are placeholders.
cp .env.example .env

# 3. Required environment variables (names only — see .env.example):
#    VERIDEX_LLM_KEY=[ENV:VERIDEX_LLM_KEY]
#    VERIDEX_DATA_SOURCE_KEY=[ENV:VERIDEX_DATA_SOURCE_KEY]

# 4. Install / run commands: TBD — no build system is wired up yet.
#    [VERIFY before use; nothing in src/ is executable at this stage.]
```

## License

Released under the [MIT License](LICENSE).

---

*Faceless, AI-native, asynchronous project. All contributions are written and
PR-based — see [CONTRIBUTING.md](CONTRIBUTING.md).*
