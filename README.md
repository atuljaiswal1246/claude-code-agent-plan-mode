# claude-code-agent-plan-mode

A Claude Code skill that forces the agent to write a plan and wait for your approval before touching anything.

## What it does

Stops the agent from jumping straight into work. When given a task, the agent must:

1. Write a numbered plan — what to do, which files, how to verify each step.
2. Stop and wait for your "go" / "approve" / "proceed."
3. Execute one step at a time, only after approval.
4. Verify after each step before moving on.

No edits, no commands, no changes until you say so.

## Install

Copy the skill into your Claude Code skills directory and reference it in `CLAUDE.md` or your project's agent instructions:

```bash
mkdir -p ~/.claude/skills
cp -r plan-first ~/.claude/skills/plan-first
```

Then load it in your session:

```
/skill plan-first
```

Or add it to your `CLAUDE.md` so it's active in every session.

## Files

- `SKILL.md` — the skill itself.

## License

MIT

Published at: https://github.com/atuljaiswal1246/claude-code-agent-plan-mode