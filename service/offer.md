# Service Offer

## Pilot

Send me one prompt, checklist, or SOP you keep pasting into a coding agent.
I turn it into repo files your team can reuse.

Price:

- `$99` for one narrow workflow pack
- `$299` for one workflow pack, setup guidance, and one revision after testing

## Deliverables

- `README.md`
- `AGENTS.md` or a project-instruction patch
- `skills/<workflow>/SKILL.md`
- `policy/<workflow>.json` or `policy/agent-safety-policy.json` (safety pilots)
- optional templates
- optional scripts
- `verification.md`
- optional receipt schema block (`checks_run`, `checks_blocked`, `unverified`, `residual_risk`)

## What Counts As Success

You can run the task again without rewriting the original long prompt, and the
agent has to report what it checked, skipped, and could not verify.

## Fit

Good fit:

- repeated PR review prompt
- repeated bugfix or reproduction SOP
- repeated QA/release workflow
- repeated safety rule such as "do not touch generated files or secrets"
- clear expected output
- clear rules the agent should follow

Bad fit:

- one-off task
- vague "make my agent better"
- full app build
- spam, evasion, illegal scraping, account farming, or credential misuse

I do not provide SOC2/ISO/no-risk guarantees and do not claim security
certification. The first pilot is intentionally scoped to verifiable, narrow,
repeatable workflow behavior.

## Payment Timing

For first pilots:

1. Do a free fit check from the issue form.
2. If it fits, confirm the exact scope.
3. Collect payment before delivery, or do one discounted first case study if the buyer agrees the anonymized before/after can be public.

Intake:

- GitHub issue: https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml
- X / DM: https://x.com/ChenFN01
