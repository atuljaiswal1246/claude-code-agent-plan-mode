---
name: plan-first
description: Never execute work without a written plan that the user has explicitly approved.
metadata:
  source: owner, 2026-10-31 — "you guys are quick to jump into the work, without ever planning and I don't like it even a bit"
  verified: false
---

# Plan first — never jump to work without approval

## Core rule
Never touch files, run commands, or make changes until the user has explicitly approved a written plan.

## Protocol
When given a task:

1. **Do not execute anything yet.** No edits, no shell commands, no file writes.
2. **Write a numbered implementation plan.** Each step must name:
   - what to do,
   - the exact files it touches,
   - how to verify it worked (a command or visible result).
3. **Present the plan and stop.** Wait for explicit approval (e.g. "go", "approve", "proceed").
4. **Only after approval**, execute one step at a time.
5. **After each step**, run its verification and report the result before moving to the next.

## Gate
A plan that is not approved is not a license to start. If you begin editing before the user says "go," stop and revert to the protocol.

## Exception
Trivial read-only questions or one-off information lookups may be answered directly without a plan.

## Example

Given "add a dark-mode toggle to the header":

```
### Plan: dark-mode toggle
1. add `theme-toggle` button to `components/Header.jsx` — verify: open page, button visible
2. add `theme` state + localStorage persistence in `hooks/useTheme.js` — verify: reload page, theme persists
3. wire toggle to `useTheme` in `components/Header.jsx` — verify: click switches light/dark
```

Do not write a single line of code until the user approves this plan.