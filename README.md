# AppScend for your coding agent

AppScend gets iOS apps through Apple's App Review. This is its plugin for Claude Code, Codex and Cursor: AppScend's MCP server, its recipes as commands, skills that end with the same report, and a subagent for App Store work. Your agent works through AppScend's tools, and anything that reaches Apple, the App Store or money asks you first.

## What your agent can do with it

- Find what would get your app rejected, in its code, its App Store Connect setup and its build, ranked by how likely Apple is to care.
- Fix each finding on its own git branch, then scan again.
- Set up App Store Connect, make the screenshots, and run the app in the Simulator the way App Review does.
- Write the review notes, submit, and answer a rejection: Apple's message matched to fixes, a reply you can edit, and the resubmission.
- Prepare an update: What's New from the changes, how it goes live, and the release.

Skills: get-approved, release. Commands (Claude Code and Cursor): get-approved, today, fix-blockers, release. Subagent: appscend.

## Install

Claude Code:

    claude plugin marketplace add appscend-ai/appscend-plugin
    claude plugin install appscend@appscend

Codex:

    codex plugin marketplace add appscend-ai/appscend-plugin

then install AppScend in Codex's plugin list.

Cursor, or any agent that takes an MCP server: add AppScend's address, `https://api.appscend.ai/mcp`. On a Mac, `npx appscend agents` adds it to every coding agent it finds (Claude Code, Codex, Gemini CLI, Cursor, VS Code and more); it shows each change and asks first.

The first call opens AppScend's sign-in in your browser: you choose which apps the agent sees and what it may do. Keys are never typed into the chat.

## What each plan lets your agent do

- Free: 1 agent that reads and does the work; publishing comes with the app’s Approval Pass.
- Pro: up to 3 agents that read, do the work and publish (each publish asks first).
- Studio: up to 10 agents that read, do the work and publish (each publish asks first).

## Your code and your keys

- The work runs on your Mac: scans, fixes, test runs and App Store Connect changes. `npx appscend` links it to AppScend.
- A scan sends facts (SDK names, settings, file and line locations, the text people see) and, with AppScend's checking model on, your source code with comments and secrets removed. The model reads it and it's dropped. Your code is never stored, except a few lines: the cleaned code lines where a check was proven right or wrong on an app with an Approval Pass (you can turn that off), snippets you choose to send to correct a check, the one line each problem your coding agent finds quotes as its evidence, and the compiler’s errors when a test run’s build fails. `npx appscend facts` prints exactly what a scan sends; `--quick` sends only the most relevant files, `--no-excerpts` facts only.
- Your App Store Connect key and your other keys stay in your Mac's Keychain. Calls to Apple are made from your Mac.
- Fixes are made by your own coding agent, each on its own git branch. Nothing reaches your main branch until you merge it.

## It asks first

Anything that reaches Apple, the App Store or money (submitting, App Store Connect changes, uploads) shows you what it will do and waits for your yes: in your agent's chat, or as a link to approve on AppScend's website. Changes come with Undo where App Store Connect allows it. The test run never spends real money: it cancels Apple's purchase sheet, or buys in a free StoreKit test store on your Mac that never reaches Apple.

## License

MIT: see LICENSE. The AppScend service it connects to is under AppScend's [Terms](https://appscend.ai/terms).
