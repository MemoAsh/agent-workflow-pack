# Agent Workflow Pack

Reusable workflow packs for AI coding agents.

Landing page: https://memoash.github.io/agent-workflow-pack/

Free fit check: https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml

Example fit check submission: https://github.com/MemoAsh/agent-workflow-pack/issues/1

Free SKILL.md checker: https://memoash.github.io/agent-workflow-pack/skill-checker.html

Try PR review without local setup: https://memoash.github.io/agent-workflow-pack/try-pr-review.html

Claude Code users can copy a workflow directory into `.claude/skills/`.
Codex users can copy the same workflow into `.codex/skills/`.
Keep repo-wide rules in `AGENTS.md`; keep repeated task procedures in `SKILL.md`.

Quick install examples:

```bash
# Claude Code
cp examples/pr-review-workflow/AGENTS.md ./AGENTS.md
mkdir -p .claude/skills/pr-review
cp -R examples/pr-review-workflow/skills/pr-review/* .claude/skills/pr-review/

# Codex
cp examples/pr-review-workflow/AGENTS.md ./AGENTS.md
mkdir -p .codex/skills/pr-review
cp -R examples/pr-review-workflow/skills/pr-review/* .codex/skills/pr-review/
```

If you keep pasting the same long prompt into Codex, Claude Code, Copilot, Cursor, or another coding agent, that workflow probably belongs in a reusable pack:

- durable repo instructions
- task-specific skill/checklist
- optional output templates
- verification steps

This turns repeated prompt knowledge into something your future self or team can run again.

## The Problem

AI coding agents are powerful, but repeated workflows often stay trapped in chat:

- "Review this PR, but only report real risks."
- "Fix this bug, but reproduce it first."
- "Write release notes in our format."
- "Never edit generated files."
- "Run these checks before saying done."

When those rules live only in a prompt, they drift. People rewrite them, agents forget them, and teams cannot audit what actually happened.

## The Pack

A workflow pack gives the agent a repeatable operating procedure.

Typical layout:

```text
repo/
  AGENTS.md
  skills/
    workflow-name/
      SKILL.md
      verification.md
      templates/
        output-template.md
```

## What Goes Where

| Need | Put It Here |
|---|---|
| Repo-wide conventions | `AGENTS.md` |
| Task procedure | `skills/<workflow>/SKILL.md` |
| Expected output format | `templates/` |
| Success checks | `verification.md` |
| Mechanical repeatable steps | `scripts/` when needed |

## Example

See [examples/pr-review-workflow](examples/pr-review-workflow/README.md) for a small PR-review workflow pack.

More examples:

- [PR review workflow](examples/pr-review-workflow/README.md)
- [Safe edit workflow](examples/safe-edit-workflow/README.md)

## Service

I offer a small paid pilot:

- **$99**: one narrow workflow pack
- **$299**: one workflow pack, setup guidance, and one revision after testing

Good pilot workflows:

- PR review
- bug reproduction and fix
- release notes
- safe edit / restricted path checks
- QA verification
- customer issue triage
- internal handoff for weaker AI models

Not a good fit:

- spam, account abuse, platform evasion, or illegal scraping
- vague "make my agent better" requests
- full app builds disguised as one workflow
- generic prompt packs with no verification

## How A Pilot Works

1. You send one repeated prompt, SOP, checklist, or example output.
2. I separate repo rules, task steps, templates, and verification.
3. I deliver a small workflow pack.
4. You test it once.
5. I make one revision based on what failed.

## Contact

Send one repeated AI-agent workflow you are tired of rewriting.

If it is a bad fit, I will say that before you pay.

Open a [free fit check / pilot issue](https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml) with your repeated workflow.

See [service/offer.md](service/offer.md) for scope and pricing.

## License

MIT. See [LICENSE](LICENSE).
