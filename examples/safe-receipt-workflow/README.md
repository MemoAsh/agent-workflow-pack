# Example: Safe Edit + Receipt Workflow Pack

This sample turns a security-sensitive coding task into a reusable workflow pack.

## Before

The user repeatedly asks:

> Review and apply changes, but block risky commands, never read secrets, and prove what was checked.

## After

The workflow pack forces explicit safety boundaries and a machine-readable completion receipt:

- `AGENTS.md` stores repo-level rules and prohibited actions
- `skills/safe-receipt/SKILL.md` defines the safety workflow
- `policy/agent-safety-policy.json` stores one-file policy inputs
- `skills/safe-receipt/templates/completion-receipt.md` captures what changed, what was checked, and what remains unverified
- `skills/safe-receipt/templates/audit-receipt.json` gives CI and audit tools a small machine-readable receipt shape
- `skills/safe-receipt/templates/profile-exposure-receipt.json` checks whether a workflow requires a tool that is hidden by a restricted profile
- `skills/safe-receipt/templates/large-audit-report-receipt.json` summarizes multi-agent audits with coverage, verifier verdicts, appendix publication state, and drift risk
- `skills/safe-receipt/verification.md` defines mandatory run-end checks

## Files

- [AGENTS.md](AGENTS.md)
- [policy/agent-safety-policy.json](policy/agent-safety-policy.json)
- [skills/safe-receipt/SKILL.md](skills/safe-receipt/SKILL.md)
- [skills/safe-receipt/verification.md](skills/safe-receipt/verification.md)
- [skills/safe-receipt/templates/completion-receipt.md](skills/safe-receipt/templates/completion-receipt.md)
- [skills/safe-receipt/templates/audit-receipt.json](skills/safe-receipt/templates/audit-receipt.json)
- [skills/safe-receipt/templates/profile-exposure-receipt.json](skills/safe-receipt/templates/profile-exposure-receipt.json)
- [skills/safe-receipt/templates/large-audit-report-receipt.json](skills/safe-receipt/templates/large-audit-report-receipt.json)

## Pilot Scope (Recommended)

Use this sample only for one narrow workflow. It is not a full compliance system.
The default intent is to improve auditability for human review and repeatability.
