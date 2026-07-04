---
name: safe-edit
description: Use before editing files in a repository with restricted paths, generated files, or sensitive areas.
---

# Safe Edit Skill

## Goal

Prevent accidental edits to restricted files while still allowing useful code changes.

## Process

1. Identify the files likely to be edited.
2. Compare planned edits against restricted paths and file types.
3. If any planned edit touches a restricted file, stop and ask for explicit approval.
4. Make only approved edits.
5. Report the edited files and restricted-path check in the final response.

## Restricted Examples

- generated files
- lockfiles
- migrations
- billing or payment code
- authentication code
- secrets or credential files

## Stop Conditions

Stop and ask before editing if:

- the user did not explicitly request the restricted file change
- the restricted file is required to complete the task
- the file appears generated but is not clearly marked

## Verification

Before finishing, check `verification.md`.

