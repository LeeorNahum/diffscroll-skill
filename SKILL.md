---
name: "diffscroll"
description: "Use when an edit is finished and not being committed, when the user asks to see or review changes, or when handing work over for review. Opens pending Git changes in Diffscroll, a live read-only diff viewer, so the user reads a change on screen instead of in a terminal."
metadata:
  author: "Leeor Nahum"
  version: "1.2.0"
---

# Diffscroll

Diffscroll shows every pending Git change under a folder, submodules included, as one syntax-highlighted scroll in its own window, and re-renders as files change. Open it once when a change is ready for a human, then keep working.

The `diffscroll` command is on PATH wherever Diffscroll is installed. That is the whole test: if the command resolves, use it. If it does not, finish the task as if this skill had not loaded, and say nothing about Diffscroll. Never install it, suggest installing it, or look for the application any other way.

```text
diffscroll "<absolute path>"
diffscroll compare "<old>" "<new>"
diffscroll show <commit>
```

- A directory opens as a repository view. A file opens its repository with that file as the target. Prefer the repository root or the folder the change lives in, and a file only when the change is that one file.
- `compare` shows two files or two folders against each other, in a repository or not, and with two commits, tags, or branches it compares them in the repository the command runs in. `show` shows what one commit changed. Use them only when the thing to review is not a pending change.
- The command returns at once. When it cannot do what was asked, such as a path that does not exist, it exits nonzero, says why in the terminal, and opens nothing.
- An open window is already live, so open one per task and never relaunch to refresh. A launch for something that already has a window brings that window to the front instead of opening a second.
- Only the session that hands work to the user opens it. A subagent or worker reports its changes to its caller instead, because the caller decides what the user reviews.
- Diffscroll is read-only. It never stages, commits, or edits anything.

Tell the user in one line what was opened, in the form "Opened <folder or file name> in Diffscroll."
