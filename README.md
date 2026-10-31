# claude-code-agent-plan-mode

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)

A Claude Code skill that forces the agent to write a plan and wait for your approval before touching anything.

## What it does

Stops the agent from jumping straight into work. When given a task, the agent must:

* **Write a numbered plan** — what to do, which files it touches, how to verify each step.
* **Stop and wait** — no edits, no commands, no changes until you say `go`, `approve`, or `proceed`.
* **Execute one step at a time** — only after your approval, then verify before moving on.

## Install

```bash
mkdir -p ~/.claude/skills
cp -r plan-first ~/.claude/skills/plan-first
```

Load it in your session:

```
/skill plan-first
```

Or add it to your `CLAUDE.md` so it's active in every session.

## How it works

```
task arrives
    ↓
agent writes a numbered plan (no execution yet)
    ↓
agent waits for your explicit approval
    ↓
you say "go" / "approve" / "proceed"
    ↓
agent runs step 1 → verifies → step 2 → verifies → ...
```

### Plan format

Each step must name three things:

1. **What to do** — a concrete action
2. **Files touched** — exact paths
3. **Verification** — a command or visible result that proves it worked

### Example

```
### Plan: add dark-mode toggle
1. add `theme-toggle` button to `components/Header.jsx` — verify: open page, button visible
2. add `theme` state + localStorage persistence in `hooks/useTheme.js` — verify: reload page, theme persists
3. wire toggle to `useTheme` in `components/Header.jsx` — verify: click switches light/dark
```

Do not write a single line of code until the plan is approved.

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | The skill — the rule, protocol, and example |

## Contributing

Pull requests welcome. Open an issue to discuss changes first.

## License

MIT