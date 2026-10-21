# FindSkills plugin

One skill that finds and loads every other agent skill on demand from your
[FindSkills](https://findskills.cc) profile and the community (skills.sh, GitHub), so you don't
keep them all installed or in your agent's context.

## Install

In Claude Code:

```
/plugin marketplace add Justar96/findskills-plugin
/plugin install findskills@findskills
```

In Codex:

```bash
codex plugin marketplace add Justar96/findskills-plugin
codex plugin add findskills@findskills
```

Or open `/plugins` in Codex and install it from the FindSkills tab. Start a new session to load it.

The skill calls the `findskills` CLI. Install it once per machine and log in:

```bash
curl -fsSL https://findskills.cc/install.sh | sh   # or: npm i -g @findskills/cli
findskills login
```

Other agents (Cursor, Gemini CLI and more) can run `findskills init` instead, which
installs the same skill for each agent it finds.

## Prompt hook (optional)

Turn on the plugin's `auto_route` option to have FindSkills check every prompt before Claude reads
it. When one skill in your profile clearly fits, or you name one ("use humanizer"), Claude is told
to load it, as if it were installed. Prompts under three words are skipped, and code blocks and
secret-looking lines are removed before the prompt is sent to the FindSkills hub, which asks
TypeSafe which of your skills fits. It needs `findskills login` and never blocks a prompt. For 90
days the hub keeps which skill it suggested and which one was loaded next (skill IDs, scores and
timing, never the prompt), to tune when it picks a skill; `FINDSKILLS_JUDGE=0` turns judging and
this record off.

## About this repo

This is a read-only mirror of the plugin, published from the FindSkills source on every change.
Report problems at https://findskills.cc.
