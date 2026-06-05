# Bloom Skill Quickstart

Use this guide to install the Bloom skill and connect it to the Bloom MCP server.

The short version:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom
```

Then connect Bloom MCP from:

```text
https://trybloom.ai/mcp
```

## What This Skill Does

The Bloom MCP server owns the mechanics: authentication, tool parameters, generation, editing, resizing, image lookup, and credits.

The Bloom skill improves agent judgment. It tells the agent how to:

- Write prompts that describe subject, composition, and medium instead of redundant style words
- Choose a supported aspect ratio for common channels
- Pull and pass reference images when a brand has a distinctive visual language
- Write concise in-image headline copy
- Avoid duplicate brand onboarding

The skill does not authenticate Bloom or install the MCP server by itself.

## Install For Local Coding Agents

Install for the agent detected in the current project:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom
```

Install globally so the skill is available across projects:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom --global
```

Install for a specific agent:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom --agent claude-code
npx skills add TomasWard1/bloom-skills --skill bloom --agent codex
npx skills add TomasWard1/bloom-skills --skill bloom --agent cursor
```

Install for multiple agents:

```bash
npx skills add TomasWard1/bloom-skills \
  --skill bloom \
  --agent claude-code \
  --agent codex \
  --agent cursor
```

Run without prompts for setup scripts:

```bash
npx skills add TomasWard1/bloom-skills --skill bloom --global --yes
```

## Use Without Installing

Use this when you want to hand the skill to an agent for one session:

```bash
npx skills use TomasWard1/bloom-skills@bloom
```

You can pipe that prompt into an agent CLI if your workflow supports it.

## Connect Bloom MCP

The skill only teaches the agent how to use Bloom well. The agent still needs access to Bloom's MCP tools.

Setup page:

```text
https://trybloom.ai/mcp
```

MCP endpoint:

```text
https://www.trybloom.ai/api/mcp
```

Claude Code:

```bash
claude mcp add --transport http bloom https://www.trybloom.ai/api/mcp
```

Codex:

```toml
[mcp_servers.bloom]
url = "https://www.trybloom.ai/api/mcp"
```

Cursor:

```json
{
  "mcpServers": {
    "bloom": {
      "url": "https://www.trybloom.ai/api/mcp"
    }
  }
}
```

## Claude Web Or Cloud Sessions

`npx skills` installs into local coding agents. Claude web/cloud sessions usually cannot run local install commands for you.

For Claude web, upload the skill as a ZIP:

```bash
cd skills/bloom
zip -r ../../bloom.skill.zip SKILL.md rules
```

Then upload `bloom.skill.zip` in Claude's Skills settings. The ZIP root should contain `SKILL.md` and `rules/`.

If you are giving instructions to a cloud coding agent that can run shell commands in a repository, tell it:

```text
Install the Bloom skill with:
npx skills add TomasWard1/bloom-skills --skill bloom

Then connect Bloom MCP using:
https://trybloom.ai/mcp
```

## Check That It Installed

List available skills:

```bash
npx skills list
```

Inspect this repository without installing:

```bash
npx skills add TomasWard1/bloom-skills --list
```

Expected result: one skill named `bloom`.

## Update Or Remove

Update installed skills:

```bash
npx skills update bloom
```

Remove the skill:

```bash
npx skills remove bloom
```

## Example Prompts

```text
Generate an Instagram feed launch image for Acme with Bloom. The product box floating above a messy breakfast table, morning light, one hand reaching into frame. Photograph.
```

```text
Generate a LinkedIn feature announcement image for Acme with Bloom. Three product cards arranged like physical index cards on a desk, one card pulled forward as the hero. Overhead photograph.
```

```text
Make a story-sized version of the last Bloom image.
```

## Batch Guidance

Do not default to large batches just because the agent can call Bloom repeatedly. Generations spend credits.

Ask for confirmation before creating many images, or follow the user's explicit count. For exploratory work, start small, review, then iterate.

## Troubleshooting

If the skill does not trigger:

- Confirm it is installed with `npx skills list`
- Restart the agent if it only loads skills on startup
- Ask the agent explicitly: `Use the bloom skill`
- Confirm Bloom MCP is connected separately from the skill

If Bloom tools are unavailable:

- Reopen `https://trybloom.ai/mcp`
- Reconnect or re-authenticate the MCP server
- Check that the MCP endpoint is `https://www.trybloom.ai/api/mcp`
