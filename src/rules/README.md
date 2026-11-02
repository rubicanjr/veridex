# `src/rules/` — Rule Engine Module (PLACEHOLDER)

**Status: empty skeleton. There is no runnable code in this directory yet.**

Intended purpose: house the declarative, versioned rule definitions that the
future Veridex rule engine will evaluate. Each rule, once implemented, is
expected to carry at minimum:

- a stable rule ID
- a human-readable rationale ("why this rule exists")
- the condition expressed in a reviewable form
- source bindings (which data sources the rule reads — see `../sources/`)
- a changelog entry per version

## Planned (not implemented) layout

```
src/rules/
├── README.md          # this file
└── (rule specs)       # TBD — format not chosen yet [VERIFY before scaffolding]
```

## Rules for contributors working here later

1. No rule may reference a secret directly; credentials are accessed via
   environment variables only (`[ENV:VAR_NAME]`).
2. No fabricated results: a rule spec must never claim backtest performance or
   accuracy numbers without a reproducible, cited evaluation. (Currently: no
   public metrics exist.)
3. This is decision-support tooling, **not investment advice**; rule rationales
   must be phrased accordingly.
