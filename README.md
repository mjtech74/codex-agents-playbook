# Codex AGENTS Playbook

A practical `AGENTS.md` playbook for running Codex on real production projects.

This repository is for teams that want their coding agent to work with project memory, worklogs, evidence gates, frontend verification, and safer long-running workflows instead of one-off prompt vibes.

It is not a giant prompt dump. It is a set of small, copyable operating rules for agents that need to survive real codebases: stale dev servers, drifting docs, oversized files, browser verification, and "it should work" claims with no evidence.

Unofficial project. Not affiliated with OpenAI.

## The Pitch

Most agent instructions optimize for style. This playbook optimizes for operational reliability.

Use it when you want Codex to:

- inspect the current project truth before editing
- keep a live worklog across long tasks
- avoid dumping every new responsibility into one large file
- verify UI changes in a browser instead of only reading code
- record evidence before saying "done"
- leave enough context for the next human or agent to continue

## Quick Start

Choose the smallest template that fits your repo:

| Project type | Start here |
| --- | --- |
| Small library or script | `templates/minimal.md` |
| Next.js or SaaS app | `templates/nextjs-saas.md` |
| Design-heavy frontend | `templates/design-heavy-app.md` |
| Long-running production project | `templates/production-ops.md` |
| Large mixed project | root `AGENTS.md` |

Then copy it into your project:

```bash
cp templates/nextjs-saas.md ../your-project/AGENTS.md
```

Edit the copied file so it names your real commands, docs, and verification gates.

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
- `examples/vertical-saas-redacted.md`: a redacted example for a large vertical SaaS-style project.
- `docs/*`: focused guides for worklogs, evidence gates, large-file control, and dev-server recovery.

## Core Ideas

1. Inspect before changing.
2. Keep a live worklog.
3. Treat docs and code as one system.
4. Break large work into `inspect -> change -> verify`.
5. Do not claim completion without evidence.
6. Prevent large files from absorbing every new responsibility.
7. Verify UI work in a real browser when possible.
8. Record what changed, why it changed, and what remains.

## What Makes This Different

- **Evidence gates over confidence.** The agent should show what it checked before claiming completion.
- **Worklogs as project memory.** Long tasks leave a trail instead of disappearing into chat history.
- **Large-file control.** The playbook explicitly pushes back when pages, routes, hooks, and editors become junk drawers.
- **Frontend reality checks.** UI work should be observed in the app when practical, not guessed from JSX.
- **Dev-server recovery.** It treats local server hangs, stale chunks, and browser timeouts as operational states to diagnose.
- **Template weight control.** You can use the minimal version for small repos instead of forcing every rule everywhere.

## When Not To Use The Full Version

Do not start with the root `AGENTS.md` if your project is tiny. Heavy instructions can slow the agent down or distract it from simple work.

Start minimal, then add:

- worklogs when tasks span multiple sessions
- evidence gates when "done" needs proof
- large-file control when files are growing too fast
- browser verification when UI quality matters
- production ops rules when incidents and handoffs matter

## Not A Model Wrapper

This project does not provide a new model, hidden prompt, or provider bridge. It is just a practical operating playbook for Codex-style coding agents.

## License

MIT. See `LICENSE`.
