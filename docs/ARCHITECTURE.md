# Veridex Architecture (High-Level Overview)

> Status: conceptual documentation for a skeleton repository. **No component
> described here is implemented yet.** This file describes intent, not current
> behavior. There are no public performance metrics yet.

## Design principle: no black boxes

Every output produced by Veridex must be traceable to (a) an explicit,
human-readable **rule** and (b) one or more named data **sources**. If a
statement cannot cite both, it is not allowed to leave the system. This is an
architectural constraint, enforced conceptually at every layer below.

## The three-tier model

### K1 — Free weekly Transparency Report
A scheduled, push-style artifact: once per week, users receive a report that
shows *which rules ran*, *against which sources*, and *what each rule
evaluated to* — with citations. The report is deliberately readable without
any dashboard: the goal is to make the reasoning chain itself the product at
this tier. (Planned; not implemented.)

### K2 — SaaS dashboard
An interactive surface over the same rule evaluations: filtering, history,
per-rule drill-down, and source provenance views. K2 adds convenience, not new
authority — every number in the dashboard must resolve back to the same
rule+source trace exposed in K1. (Planned; not implemented.)

### K3 — Asynchronous custom ruleframe service
A higher-touch tier where users commission bespoke ruleframes (collections of
rules with their own source bindings and evaluation policies). Interaction is
asynchronous and written — issue/spec-based, no live sessions required. K3 is
a service offering and is **out of scope for this open-source repository**.

## Core concepts

### Rule engine
The intended heart of the system: a deterministic evaluator that applies
declarative, versioned rules to incoming data. Rules are plain, reviewable
definitions (in the future: likely declarative specs under `src/rules/`), each
with an identifier, a human-readable rationale, and a changelog. Determinism
matters: given the same inputs and rule version, the engine must produce the
same output, so any conclusion can be reproduced and audited later.

### Source citation
Every datum entering the engine carries provenance: provider, dataset,
timestamp, and retrieval reference. Outputs embed these citations so a reader
can independently verify the input behind each conclusion. The citation layer
(intended home: `src/sources/`) treats "uncited input" as invalid input.

### Explanation layer (future)
Natural-language summaries may be generated to aid readability, but they are
constrained to *restate rule outcomes and citations* — never to introduce new
judgment. Any generated text must link back to rule IDs and source references.

## Data flow (conceptual)

```
external data providers  ->  source-citation layer  ->  rule engine
        (keys via [ENV:...])      (provenance tags)     (deterministic eval)
                                                             |
                                     transparency report (K1)|  dashboard (K2)
                                             (rule + source trace everywhere)
```

## What is NOT here

- No investment-advice logic by design: the system supports decisions, it does
  not make them.
- No hidden scoring: if a mechanism influences output, it must appear as a
  citable rule.
- No implemented code yet: `src/` contains placeholders only.
