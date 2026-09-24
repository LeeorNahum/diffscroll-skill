# Maintenance Contract: diffscroll

This file is for agents editing the skill. Keep maintainer rules here, not in `SKILL.md`.

## Ownership

- `SKILL.md` states the launch contract of the `diffscroll` command as the application defines it. Verify every claim about arguments and window behavior against the application's own usage text and launch documentation before changing it, and change it whenever they change.
- `README.md` is the human skim layer. Keep it to a few sentences.
- Add `references/` only for a fallback viewer that has a clean command-line way to show a directory's pending changes, and tell the agent in `SKILL.md` when to read it. None qualifies today.

## Editing Rules

- The command on PATH is the only contract. Never name an operating system, a shell, an install location, or a binary. The skill must read as true on every platform Diffscroll runs on without being edited when a platform is added.
- Keep every frontmatter string quoted and free of colons.
- Do not record dates, measurements, timings, session evidence, or incident stories. State the contract and at most one clause on why a rule exists.
- Do not use em dashes, and do not use semicolons to join sentences.
- Bump `metadata.version` by the release-versioning skill's rules for skills.
