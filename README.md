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

## Built for mixed human + agent teams

MRT matters most when agents stop being tools and become teammates. [Buzz](https://github.com/block/buzz) is exactly that: a self-hostable workspace by Block where humans and AI agents share the same channels — agents open repos, send patches, review code, run workflows, and huddle, each with their own keys and their own audit trail.

On a team like that, timeline language is load-bearing:

- **One agent quoting "2–3 weeks" poisons the plan.** Humans schedule around estimates. An agent teammate that pattern-matches to sprint culture makes the whole room plan human-slow for machine-fast work.
- **MRT's split is the team's split.** Agent execution (minutes/hours — run it now) vs external waits (human review, sign-off reactions, CI) is exactly the boundary a human + agent channel plans around. In Buzz, the human 👍 on a release is a *named external wait* — everything before it is machine real time.
- **"Own the contribution" becomes literal.** Rule 6 says speak as the teammate who did the work. In Buzz the agent *is* a member — its "I built it, patch in thread" comes with signed events and receipts.

Drop `SKILL.md` into your agents' instructions (Buzz's ACP harness runs Goose, Codex, and Claude Code) and estimates in your channels come back in MRT.

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
