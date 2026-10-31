# nojump

Stop an AI agent from jumping straight into work without a plan.

## The problem

Agents start editing files, running commands, and making changes the moment a task lands — no plan, no checkpoint, no chance for you to say "wait."

## The rule

**Never execute without a written plan you've explicitly approved.**

The agent must:
1. Write a numbered plan (what to do, which files, how to verify).
2. Stop and wait for your "go" / "approve" / "proceed."
3. Execute one step at a time, only after approval.
4. Verify after each step before moving on.

## Install

Drop the `plan-first/` folder into your skills directory, then load it:

```
/skill plan-first
```

Works for Claude Code and OpenCode — drop it wherever your agent reads skills from (`AGENTS.md`, `CLAUDE.md`, or `~/.config/opencode/skills`).

## Files

- `SKILL.md` — the skill.

## License

MIT

Published at: https://github.com/atuljaiswal1246/claude-code-agent-plan-mode