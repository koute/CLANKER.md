# CLANKER.md

## What is this?

This is my customized system prompt for LLMs, mainly targetting Claude, derived from Claude Code's default system prompt and heavily modified.

It also contains potentially useful prompts in the `prompts` directory, ready to be copy-pasted.

## How to use this?

Put it in your ~/.claude and then run (I recommend making an alias):

```
claude --system-prompt-file=$HOME/.claude/CLANKER.md
```

## How is this different from `CLAUDE.md`/`AGENTS.md`?

`CLAUDE.md`/`AGENTS.md` do **not** replace your system prompt, and are appended to your session while the default system prompt is still used.

## Why?

Because the default system prompt[1] sucks. Mine still sucks, but a little less.

[1]: https://github.com/navanchauhan/agent-autopsy/blob/6d9c00e541bde8879266a14a280f09c5ae75f48c/claude-code/prompts/claude-fable-5-1.md?plain=1

## How do you know it sucks less?

I don't. But at least I don't have to swear at the clanker's "load-bearing honest caveats" as much when I'm using it, so that has to count for something?
