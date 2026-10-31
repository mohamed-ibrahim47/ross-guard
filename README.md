# ross-guard 🦕

A tiny [Claude Code](https://claude.com/claude-code) skill that levels up your English while you work.
Like Ross Geller, it can't let a grammar mistake slide. Unlike Ross, it keeps it short.

## Install

With the [skills CLI](https://skills.sh/):

```bash
npx skills add mohamed-ibrahim47/ross-guard -g
```

Or by hand: copy `skills/ross-guard/SKILL.md` to `~/.claude/skills/ross-guard/SKILL.md`, then restart Claude Code.

## Use

**Coaching.** Run this once at the start of a session:

```
/ross-guard
```

Each message you send then gets up to two quick fixes above the normal answer. Clean messages get none.

> 🦕 **Ross:** "grammer" → **grammar**. "without burning tokens" → **without burning through tokens**. *("burn through" is the natural phrase.)*

Say "stop" to turn it off.

**Polishing.** Pass the text you want to send to someone:

```
/ross-guard hi team i didnt finished the report yet, will send tomorow
```

You get a corrected version and a more sophisticated one, with one idiom at most.

## Token cost

- Nothing until you run it, because `disable-model-invocation` keeps it out of the skill list.
- About 300 tokens to load, once per session.
- A short correction block on messages that need one.

## License

[MIT](LICENSE)
