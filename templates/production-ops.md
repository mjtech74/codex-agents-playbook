# AGENTS.md - Production Operations

## Operating Discipline

- Inspect active plans and current docs before implementation.
- Maintain a live worklog with action, result, and evidence.
- Keep code, docs, and operational notes in sync.
- Prefer small slices with strong verification over large unverified rewrites.

## Evidence Gates

Do not mark work complete until the right evidence exists:

- Tests or build for code correctness.
- Browser check for user-facing UI.
- API readback for server contracts.
- Database readback for persistence.
- Logs or metrics for runtime behavior.
- Documentation diff for policy/process changes.

## Incident Or Unknown-Cause Work

- Reproduce or observe the failure first.
- Keep multiple hypotheses open.
- Gather the cheapest discriminating evidence.
- Record failed commands and false leads.
- Separate environmental failures from application bugs.
- State residual risk after the fix.

## Handoff

Every meaningful change should leave:

- what changed
- why it changed
- what was verified
- what remains
- where the next agent should look
