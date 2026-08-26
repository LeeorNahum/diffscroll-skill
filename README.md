# diffscroll-skill

The agent skill for [Diffscroll](https://diffscroll.dev), the live read-only Git diff viewer. It hands the user a diff to review.

When an agent finishes an edit it is not committing, or the user asks to see the changes, the skill opens the folder in Diffscroll, a live read-only Git diff viewer, and keeps working while the user reads. When the `diffscroll` command is not available, the skill does nothing and the task continues unchanged.

`SKILL.md` holds the trigger, the one command, its rules, and the one line to tell the user.
