# Verification Checklist

A valid safe-receipt run must:

- parse `policy/agent-safety-policy.json` before edits
- validate any planned edits against restricted paths and blocked tools/actions
- state whether policy checks were passed or explicitly blocked
- run relevant project checks (tests/build/lint) or state clearly why not run
- list files inspected, files not inspected, and why skips happened
- produce a machine-checkable evidence section in the receipt
- report any unverified claims before marking the run complete
