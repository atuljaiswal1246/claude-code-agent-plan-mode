# plan-first

OpenCode / Claude Code skill that stops an AI agent from jumping straight into work without a plan.

## The problem

Agents are quick to start editing files, running commands, and making changes the moment a task arrives — with no plan, no checkpoint, and no chance for you to say "wait, that's not what I meant."

## The rule

**Never execute work without a written plan that you have explicitly approved.**

When given a task, the agent must:
1. Write a numbered plan (what to do, which files, how to verify).
2. Stop and wait for your approval.
3. Only after you say "go" / "approve" / "proceed", execute one step at a time.
4. Verify after each step before moving on.

## Install

```bash
# Clone or copy this folder into your skills directory:
mkdir -p ~/.config/opencode/skills
cp -r plan-first ~/.config/opencode/skills/plan-first
```

Then load it in your session:

```
/skill plan-first
```

## Files

- `SKILL.md` — the skill itself (frontmatter + protocol).

## License

MIT