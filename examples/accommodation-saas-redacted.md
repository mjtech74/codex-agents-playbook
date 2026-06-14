# Redacted Example - Accommodation SaaS

This example shows how a large accommodation SaaS project might customize the playbook without exposing internal product names, domains, billing partners, or incident history.

## Active Docs

- Product and business spec: `docs/product_and_business_spec.md`
- API contract: `docs/api_contract.md`
- UI/UX baseline: `docs/ui_ux_spec.md`
- Type contract guide: `docs/type_contract_guide.md`
- Operational asset status: `docs/operational_asset_status.md`
- Workboard: `docs/workboard.md`

## Project-Specific Rules

- Always resolve active docs through `docs/workboard.md`; do not assume fixed dated filenames.
- Keep a daily KST worklog under `docs/YYYYMMDD_walk.md`.
- Homepage, booking, PMS, billing, and domain features must keep docs and code synchronized in the same work cycle.
- Page and route files should stay orchestration-focused.
- Public accommodation sites must show the customer's brand, not the platform brand, on metadata and public surfaces.
- Large seed assets must not be scanned from serverless functions at runtime.
- Browser checks must confirm local server health before navigation.

## Verification Examples

- After text/doc edits: run encoding and spec health checks.
- After route changes: verify request/response and auth behavior.
- After UI changes: run browser checks on the target route.
- After billing or entitlement changes: verify both UI and server-side gates.

## Redaction Notes

Remove before publishing a real project example:

- customer domains
- production URLs
- billing partner secrets
- database project names
- private migration identifiers
- incident logs that reveal internal operations
- user or customer data
