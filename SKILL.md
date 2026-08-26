---
name: "diffscroll"
description: "Open pending Git changes in Diffscroll, a live read-only diff viewer, so the user reads a change on screen instead of in a terminal. Use when an edit is finished and not being committed, when the user asks to see or review changes, or when handing work over for review. Skip silently when the diffscroll command is not available."
metadata:
  author: "Leeor Nahum"
  version: "1.0.0"
---

# Diffscroll

Diffscroll shows every pending Git change under a folder, submodules included, as one syntax-highlighted scroll in its own window, and re-renders as files change. Open it once when a change is ready for a human, then keep working.

The `diffscroll` command is on PATH wherever Diffscroll is installed. That is the whole test: if the command resolves, use it. If it does not, finish the task as if this skill had not loaded. Never install it, suggest installing it, or look for the application any other way.

```text
diffscroll "<absolute path>"
```

- A directory opens as a repository view. A file opens its repository with that file as the target. Prefer the repository root or the folder the change lives in, and a file only when the change is that one file.
- The path must exist. A path that does not opens the folder picker instead.
- The command returns at once. Do not wait on it or read its output.
- Every launch opens a new independent window, and an open window is already live, so open one window per task and never relaunch to refresh.
- Diffscroll is read-only. It never stages, commits, or edits anything.

Tell the user in one line what was opened, in the form "Opened <folder or file name> in Diffscroll." Say nothing about Diffscroll when it was not available.
