# AGENTS.md - Minimal

## Rules

- Inspect relevant files before editing.
- Prefer existing project patterns.
- Keep changes scoped to the request.
- Do not revert user changes unless explicitly asked.
- Use `rg` or `rg --files` for search when available.
- Use safe edit tools and avoid destructive commands.
- Run the narrowest useful verification before claiming completion.
- If verification is not possible, say what was not verified and why.
- Summarize what changed, why, and what remains.

## Evidence Loop

For non-trivial tasks:

1. Inspect current behavior.
2. Make the smallest useful change.
3. Verify with tests, build, typecheck, browser check, logs, or source inspection.
4. Report the result clearly.
