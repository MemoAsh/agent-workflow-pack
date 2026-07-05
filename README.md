# Agent Workflow Pack

Audit receipts for AI coding-agent work.

Use this when an agent, MCP server, or review workflow can say "done" while the
evidence is still thin. The receipt makes the run state what was checked, what
was skipped, and where the evidence is incomplete.

Landing page: https://memoash.github.io/agent-workflow-pack/

Free audit fit check: https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml

X / DM: https://x.com/ChenFN01

## What This Is

This is a small service and open example repo for turning one narrow agent
workflow into auditable repo files:

- instructions the agent can reuse
- a task procedure when one is useful
- a receipt schema or template
- verification notes that say what proof is required
- explicit `pass | fail | incomplete` outcomes

Good targets:

- PR review receipts
- MCP or tool-call audit logs
- sensitive-file or safe-edit traces
- release / QA checks
- repeated agent tasks where reviewers need evidence, not confidence

Bad targets:

- vague "make my agent better" requests
- full app builds
- generic prompt packs with no verification
- spam, platform evasion, illegal scraping, account abuse, or credential misuse

## Quick Example

```text
Bad final answer:
No issues found.

Better receipt:
subject: PR #123 checkout changes
files_reviewed:
  - src/payments/checkout.ts
  - tests/checkout.test.ts
checks_run:
  - inspected changed behavior
  - checked error paths
  - checked tests touched by the diff
not_checked:
  - production gateway behavior
  - browser compatibility
verdict: incomplete
reason: tests were inspected but not executed locally
```

For MCP/tool-call audit logs, the same idea becomes:

```text
event: tool_call
outcome: ok | rejected | error
redaction_state: full | sanitized | truncated | omitted
audit_coverage: complete | partial | unobservable
coverage_gap: output_truncated | hook_missing | upstream_not_observed | none
```

## Examples

- Audit receipt article: https://memoash.github.io/agent-workflow-pack/agent-audit-receipts.html
- MCP team audit receipt: https://memoash.github.io/agent-workflow-pack/mcp-team-audit-receipt.html
- Try an audit receipt without local setup: https://memoash.github.io/agent-workflow-pack/try-pr-review.html
- Free SKILL.md checker: https://memoash.github.io/agent-workflow-pack/skill-checker.html
- Completion receipts: [docs/completion-receipts.md](docs/completion-receipts.md)
- PR review workflow: [examples/pr-review-workflow](examples/pr-review-workflow/README.md)
- Safe edit workflow: [examples/safe-edit-workflow](examples/safe-edit-workflow/README.md)
- Safe receipt workflow: [examples/safe-receipt-workflow](examples/safe-receipt-workflow/README.md)
- Audit receipt JSON template: [examples/safe-receipt-workflow/skills/safe-receipt/templates/audit-receipt.json](examples/safe-receipt-workflow/skills/safe-receipt/templates/audit-receipt.json)

## Public Signals So Far

These are technical validation threads, not customer logos:

- ReviewMyMCP maintainer asked to iterate on a machine-readable MCP audit receipt shape: https://github.com/rogue-socket/reviewmymcp/issues/1#issuecomment-4885283874
- Traceary adopted the split between sensitive-path match, access operation, redaction state, and coverage gaps: https://github.com/duck8823/traceary/issues/1257#issuecomment-4886498153
- Forge discussion helped sharpen run-level PR contract report fields: https://github.com/Joncallim/Forge/issues/141#issuecomment-4885081208

## Service

Free fit check:

- send one narrow audit/workflow problem
- I say whether a receipt would help, or whether a normal prompt/checklist is enough

Paid pilot:

- **$99**: one narrow audit workflow pack
- **$299**: one audit workflow pack, setup guidance, and one revision after testing

Typical deliverable:

```text
AGENTS.md or project-instruction patch
skills/<workflow>/SKILL.md when a repeatable procedure is useful
templates/<receipt>.md or .json
verification.md
README.md explaining how to run and judge the workflow
```

Start here: https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml

If it is a bad fit, I will say that before you pay.

## Local Install Examples

Claude Code users can copy a workflow directory into `.claude/skills/`.
Codex users can copy the same workflow into `.codex/skills/`.
Keep repo-wide rules in `AGENTS.md`; keep repeated task procedures in `SKILL.md`.

```bash
# Claude Code
cp examples/pr-review-workflow/AGENTS.md ./AGENTS.md
mkdir -p .claude/skills/pr-review
cp -R skills/pr-review-workflow/* .claude/skills/pr-review/

# Codex
cp examples/pr-review-workflow/AGENTS.md ./AGENTS.md
mkdir -p .codex/skills/pr-review
cp -R skills/pr-review-workflow/* .codex/skills/pr-review/
```

## License

MIT. See [LICENSE](LICENSE).
