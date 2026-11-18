---
name: fix-blockers
description: "Fix every blocker in this code. Fix every code finding in the repository you are in, then scan again."
argument-hint: "[app name or bundle ID]"
---

The app: $ARGUMENTS (when that's empty, the app in this repository; ask me which when AppScend has several).

In this repository, fix everything AppScend found in that app's code. Get the brief with get_finding (format "all"), work on a new git branch, fix blockers first, then warnings, in the code's own style. Then scan_app (or run `npx appscend scan --json`) and check they're gone. Summarize each fix.
