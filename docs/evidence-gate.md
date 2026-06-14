# Evidence Gate

An evidence gate is the rule that an agent should not claim completion until it has checked the right thing.

## Common Evidence Types

- Source inspection: useful for small config or copy changes.
- Unit tests: useful for pure functions and contracts.
- Typecheck: useful for TypeScript/API surface changes.
- Build: useful for framework and bundling changes.
- Browser verification: useful for UI and interaction changes.
- API readback: useful for route behavior.
- Database readback: useful for persistence.
- Logs: useful for runtime, jobs, and integrations.

## Choosing Evidence

Use the narrowest evidence that covers the risk.

Examples:

- CSS-only button spacing: browser screenshot or visual check.
- Shared type change: typecheck and focused tests.
- Billing gate: server route check and UI state check.
- Dev server failure: process status, HTTP response, and logs.

## Reporting

Good:

```text
Verified with npm run build and a browser check on /settings. No console errors observed.
```

Good when incomplete:

```text
I updated the route and typecheck passes. I did not run the browser flow because the local server is not starting; the server failure is logged in docs/worklogs.
```

Bad:

```text
It should work.
```
