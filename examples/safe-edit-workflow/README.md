# Example: Safe Edit Workflow

This workflow helps an AI coding agent avoid editing restricted files unless the user explicitly approves it.

## Before

The user writes:

> You can edit code, but do not touch generated files, lockfiles, migrations, or billing code unless I explicitly ask.

This can fail because the instruction is passive background context.

## After

The workflow makes the rule active:

1. list planned edits
2. compare against restricted paths
3. ask before editing restricted files
4. report what was checked at the end

## Files

- [AGENTS.md](AGENTS.md)
- [skills/safe-edit/SKILL.md](skills/safe-edit/SKILL.md)
- [skills/safe-edit/verification.md](skills/safe-edit/verification.md)

