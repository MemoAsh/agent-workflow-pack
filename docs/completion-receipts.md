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
- Residual risk:
- Confidence: high / medium / low
```

## Why It Belongs In A Workflow Pack

`AGENTS.md` tells the agent the stable repo rules.

`SKILL.md` tells the agent how to run the repeated task.

`verification.md` tells the agent what must be checked before finishing.

`completion-receipt.md` makes the final claim reviewable.

