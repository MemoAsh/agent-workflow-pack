# Completion Receipts

A workflow pack should not end with a vague "done".

A completion receipt is a short, structured end-of-run claim that lets a human reviewer see what the agent actually checked, what it did not check, and what risk remains.

## What It Proves

- The agent accepted a specific scope.
- The agent names the claims it checked.
- The agent cites evidence for those claims.
- The agent names unverified claims.
- The agent reports residual risk before claiming completion.

## What It Does Not Prove

- It does not prove the code is correct.
- It does not replace tests, CI, or human review.
- It does not make an unsafe agent safe by itself.

The point is narrower: make the completion claim inspectable, so "done" cannot hide missing tests, skipped files, or unchecked assumptions.

## Minimal Receipt Fields

```text
Scope:
- Source reviewed:
- Accepted scope:
- Out of scope:

Claims checked:
- Changed behavior/contracts inspected:
- Risk areas inspected:
- Tests considered:
- Negative constraints checked:

Evidence:
- Findings with file/line citations:
- Commands run:
- Commands not run:
- Files or areas not inspected:

Unverified claims:
- Claim:
  Reason it is unverified:
  Follow-up needed:

Verdict:
- Verdict: changes requested / no blocking findings / needs human follow-up
- Residual risk: low / medium / high
- Confidence: high / medium / low
```

## Machine-Readable Receipt Pattern (v1)

For clients that want automation, keep one structured block in the run notes:

```text
{
  "run_id": "run_2026-07-05_001",
  "workflow": "pr-review",
  "agent": "claude-code | codex | other",
  "scope": {
    "in_scope_paths": ["src/", "package.json"],
    "out_of_scope_paths": [".env", "models/"]
  },
  "checks_run": [
    "file_diff_reviewed",
    "restricted_paths_blocked",
    "suspicious_commands_checked"
  ],
  "checks_blocked": [],
  "unverified": [
    "security_threat_model_not_confirmed",
    "runtime_sandbox_not_tested"
  ],
  "evidence": [
    { "type": "file", "path": "src/main.js", "status": "inspected" },
    { "type": "command", "name": "git diff", "status": "executed" }
  ],
  "verdict": "needs_followup | no_blocking_findings | changes_requested",
  "residual_risk": "low | medium | high",
  "next_steps": ["rerun_after_fix", "manual_review_required"]
}
```

This pattern is optional but it makes follow-up easy for teams and auditors.

## Policy-Controlled Receipt (v2)

For narrow safety pilots, include policy controls and the resulting blockers.

```text
{
  "run_id": "run_2026-07-05_002",
  "workflow": "safe-receipt",
  "policy_file": "policy/agent-safety-policy.json",
  "policy_version": "1.0",
  "checks_run": [
    "policy_loaded",
    "restricted_path_check",
    "blocked_action_scan",
    "secret_pattern_scan"
  ],
  "checks_blocked": [
    {
      "rule": "restricted_path",
      "target": "secrets/.env",
      "status": "blocked_by_policy"
    }
  ],
  "unverified": ["runtime_sandbox", "third_party_scan"],
  "evidence": [
    { "type": "file", "path": "src/payments/checkout.js", "status": "inspected" },
    { "type": "command", "name": "npx eslint", "status": "executed" }
  ],
  "verdict": "needs_human_follow_up",
  "residual_risk": "medium"
}
```

Use this in addition to the human-readable section when a buyer asks for audit-ready output.

## Audit Receipt Template

For MCP servers, CI checks, or log-driven audits, keep a tiny JSON artifact that
can be consumed without parsing prose:

```json
{
  "receipt_version": "0.1",
  "subject": {
    "name": "",
    "version_or_hash": "",
    "type": "repo|mcp-server|agent-workflow|other"
  },
  "input_coverage": {
    "mode": "manual|log|synthetic|mixed",
    "sessions": 0,
    "tool_calls_observed": 0,
    "tasks_attempted": []
  },
  "checks": {
    "enabled": [],
    "skipped": [
      {
        "check": "",
        "reason": ""
      }
    ]
  },
  "findings_summary": {
    "critical": 0,
    "high": 0,
    "medium": 0,
    "low": 0
  },
  "telemetry_gaps": [],
  "verdict": "pass|fail|incomplete",
  "generated_at": ""
}
```

The important verdict is `incomplete`. It prevents a run with too little
evidence from looking like a clean pass.

## Why It Belongs In A Workflow Pack

`AGENTS.md` tells the agent the stable repo rules.

`SKILL.md` tells the agent how to run the repeated task.

`verification.md` tells the agent what must be checked before finishing.

`completion-receipt.md` makes the final claim reviewable.
