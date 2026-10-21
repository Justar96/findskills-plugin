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

The skill calls the `findskills` CLI. Install it once per machine and log in:

```bash
curl -fsSL https://findskills.cc/install.sh | sh   # or: npm i -g @findskills/cli
findskills login
```

Other agents (Codex, Cursor, Gemini CLI and more) can run `findskills init` instead, which
installs the same skill for each agent it finds.

## About this repo

This is a read-only mirror of the plugin, published from the FindSkills source on every change.
Report problems at https://findskills.cc.
