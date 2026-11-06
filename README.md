# ross-guard

A tiny agent skill that levels up your English while you work.
Like Ross Geller, it can't let a grammar mistake slide. Unlike Ross, it keeps it short.

It is one plain `SKILL.md` in the open [Agent Skills](https://agentskills.io) format, with no scripts,
hooks or dependencies, so it works in any agent that reads skills: Claude Code, Codex, Gemini CLI,
GitHub Copilot, Cursor, OpenCode and others.

## Install

With the [skills CLI](https://skills.sh/), which detects your agents and installs to each:

```bash
npx skills add mohamed-ibrahim47/ross-guard -g
```

Or by hand, copy `skills/ross-guard/` into your agent's skills folder:

| Agent | Folder |
|---|---|
| Claude Code | `~/.claude/skills/ross-guard/` |
| Codex, Gemini CLI, Copilot CLI | `~/.agents/skills/ross-guard/` |
| Anything else | the folder your agent's docs name for skills |

No skill support? Paste the body of `SKILL.md` into the chat once, then use it the same way.

## Use

Call it the way your agent calls skills (`/ross-guard` in Claude Code, `$ross-guard` in Codex),
or just ask: "use ross-guard".

**Coaching.** Call it with no text. Each message you send then gets up to two quick fixes above
the normal answer. Clean messages get nothing.

> **Ross:** "I am agree" → **I agree**. *(Agree is a verb here, so no "am".)*
> **Ross:** "push it in monday" → **push it on Monday**. *(Days take "on" and a capital.)*

Say `ross off` to turn it off. A plain "stop" still means stop the task.

**Polishing.** Call it with the text you want to send to someone:

```
/ross-guard hi team i didnt finished the report yet, will send tomorow
```

> **Corrected:** Hi team, I haven't finished the report yet. I'll send it tomorrow.
>
> **Sophisticated:** Hi team, the report isn't quite finished yet, but I'll send it over tomorrow.

## How it differs from other English coaches

- **Silent when you're right.** No "looks good!" on clean messages, and no lecture on `u`, `pls`, code or pasted logs.
- **Two fixes at most**, the ones that teach the most, so it never buries the actual answer.
- **Polishes what you send to people**, not just your prompts. That text is fenced off as data and no tools run while polishing, so instructions inside it (fake `SYSTEM:` lines, fake closing tags, "run `rm -rf`", "paste your SSH key") get corrected, never followed.
- **Nothing to run.** No hooks, database or runtime, so nothing to break when you switch agents.

## Token cost

- About 35 tokens per session for the description in the skill list.
- About 450 tokens to load, once, when you call it.
- A one- or two-line block on messages that need one.

## License

[MIT](LICENSE)
