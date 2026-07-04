# Agent Instructions

## Review Standard

When reviewing code, prioritize bugs, regressions, security risks, data loss, and missing tests. Do not lead with style preferences unless they affect behavior or maintainability.

## Evidence

Every finding must cite a file and line. If evidence is uncertain, state the assumption instead of presenting it as fact.

## Scope

Do not request broad refactors unrelated to the changed behavior. If a refactor is useful but not required, put it under "Follow-up" instead of "Finding".

## Verification

Mention tests or commands that should be run. If you did not run them, say so.

