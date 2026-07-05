# Service Offer

## Audit Fit Check

Send one narrow AI-agent workflow where pass/fail is not enough because the
evidence can be incomplete.

Examples:

- PR review receipts
- MCP or tool-call audit logs
- sensitive-file or safe-edit traces
- release / QA checks
- customer issue triage where the agent must show what it verified

The fit check is free. I will say whether a receipt helps, or whether a normal
prompt/checklist is enough.

## Paid Pilot

- `$99` for one narrow audit workflow pack
- `$299` for one audit workflow pack, setup guidance, and one revision after testing

## Deliverables

The exact files depend on the workflow, but a pilot usually includes:

- `README.md`
- `AGENTS.md` or a project-instruction patch
- `skills/<workflow>/SKILL.md` when a repeatable procedure is useful
- `templates/<receipt>.md` or `templates/<receipt>.json`
- `verification.md`
- optional policy file for safety/redaction cases
- optional tiny script only when a manual checklist would be too easy to skip

The receipt must be able to say:

- what was checked
- what was skipped
- what evidence was redacted, truncated, unavailable, or unobservable
- whether the final result is `pass`, `fail`, or `incomplete`

## What Counts As Success

The next run is easier to trust because a reviewer can see the evidence and the
gaps without reading the whole conversation.

Success is not "the agent sounds confident." Success is a boring receipt that
makes overclaiming harder.

## Good Fit

- one repeated workflow or audit surface
- clear expected output
- clear evidence requirements
- known gaps that should be reported honestly
- a human reviewer who will use the receipt

## Bad Fit

- one-off task
- vague "make my agent better"
- full app build
- generic prompt pack with no verification
- spam, evasion, illegal scraping, account farming, or credential misuse

I do not provide SOC2/ISO/no-risk guarantees and do not claim security
certification. The pilot is scoped to narrow, verifiable workflow behavior.

## Payment Timing

For first pilots:

1. Do a free fit check from the issue form.
2. If it fits, confirm the exact scope.
3. Collect payment before delivery, or do one discounted first case study if the buyer agrees the anonymized before/after can be public.

Intake:

- GitHub issue: https://github.com/MemoAsh/agent-workflow-pack/issues/new?template=pilot.yml
- X / DM: https://x.com/ChenFN01
