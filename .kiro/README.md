# `.kiro/` — Kiro agentic configuration (PLACEHOLDER)

This directory exists so the repository is compatible with the **Kiroween
hackathon** requirement of a root-level `/.kiro` folder.

> ⚠️ **[VERIFY: Kiro docs]** — The exact required subdirectory schema and file
> formats for `.kiro/` (e.g., steering files, specs, hooks) have NOT been
> verified against official Kiro documentation. What follows is a minimal,
> deliberately conservative placeholder layout. **Do not assume these filenames
> or structures are correct until you confirm them in the Kiro docs.**

## Current contents

- `steering/` — empty template directory. [VERIFY: Kiro docs] may expect
  specific steering/spec markdown files here.
- `empty-template.md` — a blank template file, intentionally containing no
  invented configuration.

## Rules for this directory

1. **No secrets here.** If a Kiro config ever needs a credential, reference it
   as `[ENV:VAR_NAME]` only (see `.env.example` at repo root).
2. **No fabricated features.** Do not describe Kiro agents, specs, or hooks that
   do not exist yet.
3. When the real schema is confirmed, replace this README's `[VERIFY]` notes
   with links to the authoritative documentation.

## TODO (for whoever validates this repo)

- [ ] Confirm the canonical `.kiro/` subdirectory layout from Kiro docs.
- [ ] Add real steering/spec files per that schema.
- [ ] Remove the `[VERIFY: Kiro docs]` markers once validated.
