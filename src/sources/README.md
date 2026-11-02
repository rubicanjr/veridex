# `src/sources/` — Source-Citation Module (PLACEHOLDER)

**Status: empty skeleton. There is no runnable code in this directory yet.**

Intended purpose: implement the provenance/citation layer. Every external data
source Veridex consumes will be wrapped here so that any value entering the
rule engine carries: provider name, dataset identifier, retrieval timestamp,
and access reference. "Uncited input" is treated as invalid by design.

## Planned (not implemented) layout

```
src/sources/
├── README.md              # this file
└── (source adapters)      # TBD — adapter list and format not decided yet
                           # [VERIFY before scaffolding]
```

## Rules for contributors working here later

1. API keys for data providers are read from environment variables only —
   e.g. `[ENV:VERIDEX_DATA_SOURCE_KEY]` (see repo-root `.env.example`).
   Never hardcode, log, or commit real keys.
2. Never store user PII in citation metadata.
3. Cite licensing/terms of the upstream data providers when adapters are
   added; some market-data sources restrict redistribution.
