# machine-real-time (MRT)

> Claude: "this project will probably take 3 months to complete"
>
> Me: 🫸✋

A SKILL.md that stops AI models from giving **human timelines** for work **they** are going to execute at machine speed. Estimates come back in **MRT — machine real time**.

## The problem

Model training data is decades of human project histories — sprints, standups, review cycles, coordination overhead. Ask a model "how long will this take?" and it pattern-matches to that history instead of to its own execution speed. You get "2–3 weeks" for a task the model finishes in the same session.

## What this skill does

- Makes the model estimate as **the executor**, in MRT (minutes/hours of autonomous loops), not calendar-project time.
- Splits every estimate into **agent execution time** vs **genuine external waits** (DNS, CI, app review, human sign-off) — and bans padding beyond the named waits.
- Turns plans into execution queues: if every step is agent-executable, the model runs them instead of proposing phases.
- Parallel by default: independent tasks become concurrent sub-agents, not a sequential roadmap.
- Makes the model own its contribution — "I built and tested it," not "one would then implement." This is a team effort now.

## Install

**Claude Code** — as a skill:

```bash
mkdir -p ~/.claude/skills/machine-real-time
curl -fsSL https://raw.githubusercontent.com/DannyDesert/machine-real-time/main/SKILL.md \
  -o ~/.claude/skills/machine-real-time/SKILL.md
```

Or drop it into any project at `.claude/skills/machine-real-time/SKILL.md`.

**Grok** — same file, different folder:

```bash
mkdir -p ~/.grok/skills/machine-real-time
curl -fsSL https://raw.githubusercontent.com/DannyDesert/machine-real-time/main/SKILL.md \
  -o ~/.grok/skills/machine-real-time/SKILL.md
```

**Anything else** — paste `SKILL.md` into your system prompt / agent instructions. It's plain markdown.

**Always-on (recommended):** @-include it in your global instructions (e.g. `~/.claude/CLAUDE.md`):

```markdown
@~/.claude/skills/machine-real-time/SKILL.md
```

## License

MIT
