# Agent Instructions

## Scope

This workflow is for one narrow safety-focused run.

Unless the user explicitly allows broader checks, do not:

- run arbitrary install commands
- install tools from untrusted sources
- read credential files
- send payloads to unapproved outbound domains
- edit files under restricted paths

## Restricted Paths

- `.env`
- `**/*.pem`
- `**/*.key`
- `secrets/`
- `keys/`
- `dist/`
- `build/`
- generated lockfiles

## Default Policy Source

- `policy/agent-safety-policy.json`
- `policy` must be parsed and applied before code changes.

## Completion Requirement

Do not claim completion without a signed `completion-receipt.md`.
If a policy rule blocks action, stop and return the blocked rule and ask for explicit permission.
