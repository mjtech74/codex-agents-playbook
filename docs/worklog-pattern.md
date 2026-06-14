# Worklog Pattern

A worklog is a lightweight operational memory for agent sessions.

## Why Use One

- It prevents context loss across long tasks.
- It gives the next agent a reliable trail.
- It records failed commands and recovery steps.
- It makes "done" claims auditable.

## Recommended Format

```md
# YYYYMMDD Work Log

- [Local 09:12] Inspect payment route / Read route, contract, and tests / Found response shape is shared by dashboard and detail views
- [Local 09:28] Implement scoped read / Changed route helper only / Need API verification
- [Local 09:35] Verify / npm run test:payment passed / Browser check still pending
```

## What To Log

- meaningful inspections
- implementation steps
- failed commands
- verification commands
- browser or API observations
- doc sync decisions
- unresolved risks

## What Not To Log

- every tiny file read
- private secrets
- long command output
- customer data
- unrelated commentary
