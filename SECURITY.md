# Security Policy

## Reporting a security issue

If you find a vulnerability in this repository, open a **GitHub issue** to
report it — but follow the redaction rules below. This project is faceless and
asynchronous; expect a written response via the issue thread, not a call.

## Critical rule: NEVER paste real secrets into issues, PRs, or commits

Do **not** include real API keys, tokens, passwords, private keys, or any PII
(personally identifiable information) in public reports, even partially masked.
If a finding involves a credential, describe it only by its **environment
variable name**, using the placeholder convention:

- ✅ Correct: "The service reads `VERIDEX_LLM_KEY` (value omitted, available
  as `[ENV:VERIDEX_LLM_KEY]` in the maintainer environment)."
- ❌ Wrong: pasting `sk-abc123...` or any real value anywhere.

## If you accidentally committed a secret

1. Revoke/rotate the credential immediately at the provider.
2. Open an issue referencing only the variable name (`[ENV:VAR_NAME]`).
3. Maintainers will scrub history and confirm rotation in writing.

## Repository hygiene

- Real credentials live only in local `.env` files, which are git-ignored
  (see `.gitignore`).
- `.env.example` contains key **names only**, never values.
- `secrets.*`, `*.pem`, `*.key`, and similar files are git-ignored by policy.

## Scope note

This repository is an early-stage skeleton with no running services yet. Until
production components exist, "security issues" primarily concern accidental
credential exposure and unsafe contribution practices. No bug bounty program
exists; there are no public metrics on past incidents because none have been
tracked yet.
