# Example: PR Review Workflow Pack

This example converts a repeated PR-review prompt into a reusable AI-agent workflow.

## Before

The user repeatedly pastes:

> Review this PR. Find bugs first. Ignore style-only comments. Cite file and line numbers. Mention tests. Do not suggest unrelated rewrites. Keep the summary short.

## After

The workflow is split into reusable files:

```text
AGENTS.md
skills/pr-review/SKILL.md
skills/pr-review/templates/review-output.md
skills/pr-review/verification.md
```

## Why This Helps

- `AGENTS.md` stores durable review standards.
- `SKILL.md` defines the review procedure.
- `templates/review-output.md` fixes the output shape.
- `verification.md` makes quality auditable.

The next prompt can be shorter:

> Use the PR review workflow on this branch.

## Files

This directory includes the sample files:

- [AGENTS.md](AGENTS.md)
- [skills/pr-review/SKILL.md](skills/pr-review/SKILL.md)
- [skills/pr-review/templates/review-output.md](skills/pr-review/templates/review-output.md)
- [skills/pr-review/verification.md](skills/pr-review/verification.md)

