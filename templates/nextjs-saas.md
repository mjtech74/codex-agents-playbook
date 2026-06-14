# AGENTS.md - Next.js SaaS

## Baseline

- Inspect app router structure, data contracts, auth boundaries, and existing component patterns before editing.
- Keep pages and route handlers as orchestration surfaces.
- Move business logic, validation, data assembly, and state controllers into helpers or hooks when they grow.
- Do not add new common types inside pages or routes when a shared type location exists.

## Verification

- Run the strongest relevant local command:
  - `npm run lint`
  - `npm run typecheck`
  - `npm run build`
  - focused unit/integration tests
- For UI changes, start the dev server and verify the route in a browser when practical.
- For API changes, verify status codes, request shape, response shape, and auth behavior.

## Dev Server Recovery

- Before browser checks, confirm the server returns HTTP 200.
- If navigation times out, stop repeating browser automation and inspect the server process/logs.
- Treat stale chunks and dev manifest errors as possible dev-server/cache issues before blaming app code.
- Do not run production builds while a dev server is racing over the same output directory unless the project explicitly supports it.

## SaaS Safety

- Keep auth, billing, entitlement, and tenant boundaries explicit.
- Do not weaken permission checks to make tests pass.
- For billing or entitlement work, verify both UI gate and API/server gate.
- For migrations, document rollback or recovery assumptions.
