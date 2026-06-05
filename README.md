![Bloom MCP social card](assets/bloom-mcp-og.png)

# Bloom Agent Skills

Agent skill for using Bloom's MCP.

Bloom is brand-aware: brand visual DNA, palette, typography, and aesthetic direction are already handled by the Bloom MCP server. This skill teaches agents how to write useful prompts, choose aspect ratios, attach references, and write in-image headline copy.

## Quickstart

1. Connect the Bloom MCP server in your agent:

   ```text
   https://trybloom.ai/mcp
   ```

2. Install the Bloom skill:

   ```bash
   npx skills add TomasWard1/bloom-skills --skill bloom
   ```

3. Ask your agent to create with Bloom:

   ```text
   Generate an Instagram feed launch image for Acme with Bloom. The product box floating above a messy breakfast table, morning light, one hand reaching into frame. Photograph.
   ```

For agent-specific installs, Claude web/cloud setup, updates, and troubleshooting, see [docs/quickstart.md](docs/quickstart.md).

## Install

Install the Bloom skill with `npx skills`:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom
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

Bloom MCP setup docs:

```text
https://trybloom.ai/mcp
```

## License

MIT
