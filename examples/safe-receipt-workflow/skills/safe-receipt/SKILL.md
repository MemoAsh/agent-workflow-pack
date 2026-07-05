---
name: safe-receipt
description: Use for edits in repos where command risk, secret handling, or outbound actions need audit.
---

# Safe Receipt Workflow

## Goal

Enable high-confidence execution for a narrow workflow while keeping a compact
audit trail of what was allowed, blocked, and unverified.

## Inputs

- target path
- target workflow/task
- expected output target
- security risk scope from `policy/agent-safety-policy.json`

## Process

1. Load `policy/agent-safety-policy.json` and copy risk_scope into working memory.
2. Announce restricted paths and disallowed command patterns before changing files.
3. Preflight planned edits:
   - if a planned edit hits a restricted path, stop and ask for explicit approval.
   - if a planned action is not in `allowed_tools`, stop and ask for approval.
4. Execute only in-scope operations and keep command/use evidence.
5. Run project checks relevant to the request.
6. Validate no secret patterns or restricted paths were touched without permission.
7. Emit `templates/completion-receipt.md` with claims and evidence.
8. If the workflow needs CI, audit, or MCP-style downstream processing, also fill `templates/audit-receipt.json`.

## Stop Conditions

- Any plan includes `rm -rf`, remote credentials, or blocked outbound destinations.
- Planned edits target `.env`, `*.pem`, `*.key`, `secrets/`, `keys/`, `dist/`, `build/`.
- No explicit policy file is available.

## Output

Use `templates/completion-receipt.md` at end. Add `templates/audit-receipt.json` when a machine-readable receipt is useful.

## Verification

Before finishing, check `verification.md`.
