# Codex AGENTS Playbook

A practical `AGENTS.md` playbook for running Codex on real production projects.

This repository is for teams that want their coding agent to work with project memory, worklogs, evidence gates, frontend verification, and safer long-running workflows instead of one-off prompt vibes.

## Why This Exists

Most `AGENTS.md` files say useful but generic things:

- write tests
- be concise
- follow existing patterns
- do not break things

Those are fine, but production projects usually need more durable operating rules:

- Which documents define the current truth?
- Where should work-in-progress decisions be logged?
- What evidence is required before claiming completion?
- How should the agent avoid growing already-large files?
- How should local dev servers and browser verification be recovered?
- What must be documented for handoff?

This playbook turns those lessons into reusable templates.

## What You Get

- `AGENTS.md`: a strong default for production projects.
- `templates/minimal.md`: a small version for simple repositories.
- `templates/nextjs-saas.md`: rules for Next.js/SaaS projects.
- `templates/design-heavy-app.md`: frontend and visual verification rules.
- `templates/production-ops.md`: worklogs, evidence gates, and operational discipline.
- `examples/accommodation-saas-redacted.md`: a redacted example based on a large hospitality SaaS-style project.
- `docs/*`: focused guides for worklogs, evidence gates, large-file control, and dev-server recovery.

## Recommended Use

Copy the closest template into your project as `AGENTS.md`, then edit it for your repo.

```bash
cp templates/nextjs-saas.md ../your-project/AGENTS.md
```

For larger projects, start from the root `AGENTS.md` and add repo-specific document maps, commands, and verification gates.

## Core Ideas

1. Inspect before changing.
2. Keep a live worklog.
3. Treat docs and code as one system.
4. Break large work into `inspect -> change -> verify`.
5. Do not claim completion without evidence.
6. Prevent large files from absorbing every new responsibility.
7. Verify UI work in a real browser when possible.
8. Record what changed, why it changed, and what remains.

## Not A Model Wrapper

This project does not provide a new model, hidden prompt, or provider bridge. It is just a practical operating playbook for Codex-style coding agents.

## License

MIT. See `LICENSE`.
