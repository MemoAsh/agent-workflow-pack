# Pilot Process

## Intake

Ask for:

1. AI agent/tool used.
2. The repeated workflow.
3. Current prompt, SOP, checklist, or example output.
4. Always-do rules.
5. Never-do rules.
6. Relevant file paths, commands, or tools.
7. What proves the workflow succeeded.
8. Security risk scope: setup commands, file access, external calls, secret handling.
9. Policy preference: strict mode first, or relaxed mode with explicit exceptions.

## Fit Check

Accept the pilot only if:

- The workflow repeats.
- The expected result can be verified.
- The buyer can test the pack in their own tool.
- The scope fits one narrow workflow.
- The buyer accepts that we only provide a scoped safety/audit pack, not full platform compliance.

Decline or rescope if:

- The request is illegal, spammy, or evasive.
- The buyer wants a full app build.
- The buyer cannot name a repeated workflow.
- The buyer expects guaranteed behavior without verification.
- The buyer expects certification (SOC2, ISO, etc.) in the first pilot.

## Delivery

Deliver:

- `README.md`
- `AGENTS.md` or project-instruction patch
- `skills/<workflow>/SKILL.md`
- optional templates
- optional scripts
- `verification.md`
- optional receipt schema block (`checks_run`, `checks_blocked`, `unverified`, `residual_risk`)
- optional one-file policy for safety pilots: `policy/<workflow>.json`

## Revision

After the buyer tests once, ask:

1. Did the workflow run without rewriting the prompt?
2. Which instruction did the agent miss?
3. Which part saved time?
4. Which risk checks were useful? Which were missing?
5. Which action was blocked by policy and should be explicitly approved next run?
6. Can the before/after be used as an anonymized case study?

## Safety Pilot Add-on (optional, paid)

- Add a one-file policy block for minimal CI-like checks:
  - restricted paths
  - allowed commands
  - blocked secrets patterns
  - blocked outbound actions
- Add a compact, machine-parseable evidence section (`JSON`-style) for follow-up.
