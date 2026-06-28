# AGENTS.md

## Project Operating Rules

These rules are the default policy for all agent work in this repository.

Repository purpose:

```text
Reusable AGENTS.md templates and operating rules for Codex coding agents.
```

Keep public-facing content clear enough that developers can find this repository through searches for:

- Codex AGENTS.md
- Codex agent playbook
- AI coding agent workflow
- evidence gates
- worklogs
- Next.js SaaS agent rules

## 1. Inspect First

- Before implementing, inspect the current project structure, active docs, existing patterns, and relevant tests.
- Do not assume fixed dated filenames or stale plans are still active.
- Prefer the repository's current source of truth over memory.
- If multiple docs conflict, identify the conflict before editing code.

## 2. Live Worklog

- Maintain a live worklog for meaningful work.
- Record time, action, result, and any failed command with its cause and recovery.
- Use a stable project command when available, for example:
  - `npm run log:append -- "<message>" "<detail1>" "<detail2>"`
- If no command exists, use a simple markdown log under `docs/worklogs/`.

## 3. Evidence-Based Work Loop

- For large tasks, work in `inspect -> change -> verify` stages.
- Log the evidence gathered at each stage.
- For unknown-cause bugs, keep at least two plausible causes until evidence narrows them.
- Do not claim completion until the right evidence exists: tests, build, typecheck, browser check, logs, API readback, database readback, or source inspection.
- If something cannot be verified, say exactly what remains unverified.

## 4. Change Scope

- Keep edits scoped to the request and the surrounding ownership boundary.
- Prefer existing local patterns over new abstractions.
- Do not rewrite unrelated files or normalize unrelated formatting.
- Never revert user changes unless explicitly asked.

## 5. Large-File Control

- Before editing a large page, route, hook, or editor component, ask whether the new responsibility belongs there.
- Treat these as warning levels:
  - 600+ lines: inspect split candidates.
  - 900+ lines: prefer a split plan or immediate extraction.
  - 1200+ lines: do not add new responsibilities unless there is a strong reason.
- Extract seed assembly, modal state, controllers, validation maps, submit helpers, and panel blocks when they start to crowd orchestration files.
- If you keep the change in a large file, document why and what should be split next.

## 6. Documentation Sync

- When behavior changes, update the relevant docs in the same work cycle.
- For major changes, document:
  - what changed
  - why it changed
  - what remains
- If code and docs disagree, either fix both or clearly log the remaining mismatch.
- For README changes, keep the first screen searchable and concrete:
  - what this repo is
  - who it is for
  - which template to copy first
  - which keywords describe the repo

## 7. Verification

- Run the narrowest strong verification that covers the change.
- For code changes, prefer tests, typecheck, lint, build, or focused scripts.
- For UI changes, use browser verification when practical.
- For API or data changes, verify request/response shape and persistence/readback.
- Record verification commands and results in the worklog.

## 8. Frontend Verification

- Check important UI changes at desktop and mobile widths.
- Ensure text does not overlap, controls remain reachable, and loading/error states are understandable.
- For interactive or visual-heavy work, verify the running app rather than only reading code.
- Prefer existing design system patterns and icons.

## 9. Local Dev Server Safety

- Before browser automation, confirm the local server is listening and returns HTTP 200.
- If the server times out, fix server state before repeating browser navigation.
- Avoid leaving long-running dev servers attached to timed-out shell sessions.
- For stale chunks or manifest errors, separate dev cache/server issues from code issues before debugging application logic.

## 10. Encoding And Text Safety

- Save text files as UTF-8.
- If the repo has a mojibake or encoding check, run it after editing docs or text-heavy files.
- If text corruption appears, rewrite the affected section cleanly instead of patching fragments.

## 11. Asset And Bundle Safety

- Treat seed images and public assets as code assets.
- Keep large static assets out of serverless bundle read paths.
- Prefer URL-based asset references for runtime/public assets when bundling size matters.
- When asset changes affect deployment, verify the build.

## 12. Final Review

- Before final response, perform a short self-review:
  - Did the change answer the newest user request?
  - Did it touch only intended files?
  - Did docs/worklog stay in sync?
  - Was verification run or explicitly marked unavailable?
  - Are remaining risks stated plainly?

## 13. Final Response

- Lead with the outcome.
- Mention changed files when useful.
- Mention verification run and any failures.
- Keep residual risks and follow-up work specific.
