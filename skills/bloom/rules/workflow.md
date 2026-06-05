# Setting up a run

These are the defaults for a Bloom generation — what to do unless the user asks otherwise. Each one earns its place with a reason; override when the situation calls for it.

## Always pull references before generating

Uploaded or scraped reference images are the strongest on-brand anchor you have. Generating without them produces generic output even when the brand layer is doing its job. Pull the brand's references first, then generate with them attached.

The mechanics — which tool to call (`bloom_search_user_images`, `bloom_list_images`), how reference IDs are passed — live in the tool descriptions. Read those; don't guess.

## Pass 2–4 references when the brand has a distinctive style

If the brand has a strong existing visual language — event posters, illustrated graphics, a recurring motif — attach 2 to 4 of its references so the model has enough signal to match it. One reference can be thin; more than four starts to average out the look. This is a judgment call on how distinctive and consistent the brand's existing work is.

## Default to `pro`

Use the `pro` model tier for creative output. It's the highest-quality path and the schema default — don't downgrade to `fast` or `standard` for finals. Reach for the cheaper tiers only when the user explicitly wants speed or volume over quality (rough drafts, throwaway exploration).

## Don't onboard a brand that already exists

Before calling `bloom_onboard_brand`, check whether the brand is already there — call `bloom_list_brands` first. Onboarding takes ~60–90 seconds and creates a duplicate if one already exists. The tool description guards this too; it's worth the one-line check.

## Be honest when a batch gets pushback

When the user pushes back — "these are boring," "why is everything red?" — give a real diagnosis, not a generic apology. The pushback is usually right. Say what went wrong (the prompt leaned on the brand layer too hard and got generic; the palette override wasn't set so the accent color took over) and what you'll change in the next batch. A real answer is more useful than "sorry, let me try again."
