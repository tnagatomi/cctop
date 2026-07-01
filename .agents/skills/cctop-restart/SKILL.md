---
name: cctop-restart
description: Restart cctop for local development and testing. Use when the user asks to restart, relaunch, run, or prepare the cctop app locally; ensures the current cctop-hook is installed before the menubar app is relaunched and verified.
---

# cctop Restart

When the user asks to restart or relaunch cctop during development, treat it as an end-to-end client refresh:

1. Run `./script/build_and_run.sh --verify` from the repo root when available.
2. If the script is unavailable, run `make restart`.
3. Verify `~/.cctop/bin/cctop-hook` reports or contains the current `Config.hookVersion`.
4. Verify the running `CctopMenubar` process path points at the current worktree/debug app.

Do not use `make run` or `open ...CctopMenubar.app` alone for restart requests; those can leave shims using a stale installed hook.

After cctop investigation, validation, delegated PR work, or any workflow that launches or kills the dev app, leave the verified debug app running for the developer unless the user explicitly asks to stop it or a concrete blocker prevents a safe relaunch. Report the running app path and installed hook version. Do not stop the app at the end merely to keep the process table tidy; the developer uses the app while reviewing the work.

For delegated task closeout after merge, make restart/app state part of the handoff: confirm the developer-facing app is running when relevant, then archive or park the driver thread. Only remove the driver worktree after confirming no app, build, test, or agent process is still running from it.
