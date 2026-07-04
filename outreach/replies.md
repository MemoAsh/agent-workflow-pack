# Outreach Replies

Use only in relevant conversations about AI coding agents, Codex, Claude Code, Copilot, `AGENTS.md`, skills, prompt reuse, or workflow reliability.

## Repeated Prompt

If you are pasting the same long prompt more than twice, it is probably ready to become a workflow pack: durable repo rules in `AGENTS.md`, task-specific behavior in a skill, and a tiny verification checklist so the agent knows when it is done.

## Agent Forgets Rules

For rules the agent must never violate, I would make them preflight checks, not just background instructions: list planned files, compare restricted paths, ask before editing, then verify at the end.

## Skill Structure

A useful skill should stay narrow: one trigger, one procedure, one output shape, and a verification checklist. Otherwise it becomes another giant prompt file.

## Soft CTA

I am testing a small service around this: converting repeated AI-agent workflows into `AGENTS.md` + `SKILL.md` packs with verification checklists. If you have a workflow you keep rewriting, I can take a look and tell you whether it is a good fit.

