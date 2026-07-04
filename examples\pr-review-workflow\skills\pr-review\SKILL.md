---
name: pr-review
description: Use when reviewing a pull request, diff, branch, or code change for bugs, regressions, missing tests, and release risk.
---

# PR Review Skill

## Goal

Find the highest-impact issues in the change. The output is for an engineer deciding whether the PR can merge.

## Process

1. Read the diff and the surrounding code needed to understand behavior.
2. Identify changed contracts, data flow, error handling, user-visible behavior, and tests.
3. List findings first, ordered by severity.
4. Keep summaries brief.

## Finding Rules

- A finding must describe a concrete risk.
- A finding must include file and line evidence.
- Do not include speculative issues without stating the assumption.
- Do not include style-only comments.
- If there are no issues, say that clearly and mention residual test risk.

## Output Format

Use `templates/review-output.md`.

