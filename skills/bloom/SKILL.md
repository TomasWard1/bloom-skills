---
name: bloom
description: |
  Use when about to call bloom_generate_image or bloom_edit_image, when constructing a prompt or writing headline copy for the Bloom MCP server, when choosing an aspect ratio for a platform, or when an image generation request has been routed to Bloom.
---

# Bloom

## The world model

Bloom is the system that owns brand. When you call `bloom_generate_image` or `bloom_edit_image`, the brand's visual DNA (palette, typography, tone, aesthetic, logo treatment) is already attached as image references, and a generation system prompt that knows the brand is applied on top — enforcing quality stances like restraint, whitespace, and no tech clichés.

So your prompt's job is narrow: describe the **subject**, the **composition**, and the **medium**. That's where your prompt adds information; everything else is already handled.

## Where to look

Read the rule for the task you're on:

| Task | Rule |
|---|---|
| Writing the prompt text | [`rules/prompting.md`](rules/prompting.md) |
| Writing the headline copy on the image | [`rules/copy.md`](rules/copy.md) |
| Setting up a run (references, model, batch) | [`rules/workflow.md`](rules/workflow.md) |
| Choosing an aspect ratio | [`rules/channels.md`](rules/channels.md) |

## References

- For tool semantics (parameters, async behavior, reference images, workspaces, credits), the tool descriptions on `bloom_generate_image`, `bloom_edit_image`, `bloom_list_images`, etc. are the source of truth. Read those rather than restating them here.
- Bloom has no memory between calls. If your prompt references an image (with a pronoun, a definite article, or "this"), that image has to be attached. The MCP server's `instructions` field covers the architectural details.
