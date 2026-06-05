<div align="center">

<img src="assets/bloom-mcp-og.png" alt="Bloom" width="100%" />

<br />

# Bloom Agent Skill

**Teach your agent to create on-brand images with Bloom.**

[![skills.sh](https://skills.sh/b/TomasWard1/bloom-skills)](https://skills.sh/TomasWard1/bloom-skills)
&nbsp;
[![MCP](https://img.shields.io/badge/MCP-trybloom.ai-7C3AED)](https://trybloom.ai/mcp)
&nbsp;
[![License](https://img.shields.io/badge/License-MIT-191919)](LICENSE)

<br />

![Claude Code](https://img.shields.io/badge/Claude_Code-191919?logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-191919?logo=openai&logoColor=white)
![Cursor](https://img.shields.io/badge/Cursor-191919?logo=cursor&logoColor=white)
![Windsurf](https://img.shields.io/badge/Windsurf-191919?logo=windsurf&logoColor=white)
![OpenCode](https://img.shields.io/badge/OpenCode-191919)

</div>

---

Bloom already owns the brand — palette, typography, logo, aesthetic. This skill teaches your agent the rest: how to write prompts, pick aspect ratios, attach references, and write in-image headline copy.

## Quickstart

```bash
npx skills add TomasWard1/bloom-skills --skill bloom --global
```

Then connect the Bloom MCP server in your agent:

```text
https://trybloom.ai/mcp
```

And ask:

```text
Generate an Instagram feed launch image for Acme with Bloom. The product box
floating above a messy breakfast table, morning light, one hand reaching into
frame. Photograph.
```

## Install

| Your agent | How to install |
|---|---|
| **Claude Code, Codex, Cursor, Windsurf, OpenCode** | Run `npx skills add TomasWard1/bloom-skills --skill bloom --global` |
| **Claude Desktop, Claude Web, Cowork** | Download [`bloom.skill.zip`](https://github.com/TomasWard1/bloom-skills/raw/main/dist/bloom.skill.zip) and upload it in Skills settings |

Drop `--global` to install in the current project only. Full per-agent setup, updates, and troubleshooting live in [docs/quickstart.md](docs/quickstart.md).

> Bloom MCP must be connected separately — the skill guides the agent, the MCP does the work.

## What's inside

```text
skills/bloom/
  SKILL.md          dispatcher — loads first, points to the right rule
  rules/
    prompting.md    subject, composition, medium
    copy.md         in-image headline copy
    workflow.md     references, generation flow
    channels.md     aspect ratios per platform
```

<div align="center">
<br />
<sub>MIT · <a href="https://trybloom.ai/mcp">trybloom.ai/mcp</a></sub>
</div>
