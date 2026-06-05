# Bloom Agent Skills

Agent skill for using Bloom's MCP.

Bloom is brand-aware: brand visual DNA, palette, typography, and aesthetic direction are already handled by the Bloom MCP server. This skill teaches agents how to write useful prompts, choose aspect ratios, attach references, and write in-image headline copy.

## Install

Install the Bloom skill with `npx skills`:

```bash
npx skills add trybloomai/bloom-skills --skill bloom
```

For local testing from this repository:

```bash
npx skills add . --skill bloom
```

## What This Includes

```text
skills/bloom/
  SKILL.md
  rules/
    prompting.md
    copy.md
    workflow.md
    channels.md
```

`SKILL.md` is the dispatcher. The files in `rules/` are task-specific guidance the agent reads only when needed.

## Requirements

This skill assumes the Bloom MCP server is already connected in your agent. The skill does not install or authenticate the MCP server by itself.

Bloom MCP setup docs live at:

```text
https://trybloom.ai/mcp
```

## License

MIT
