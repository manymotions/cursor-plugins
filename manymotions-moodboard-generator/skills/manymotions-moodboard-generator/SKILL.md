---
name: manymotions-moodboard-generator
description: Create a moodboard of five visual directions from a creative brief with ManyMotions. Use when the user asks for a moodboard of five visual directions from a creative brief.
---

# Moodboards with ManyMotions

## When to use

The user wants a moodboard of five visual directions from a creative brief.

## Tools

- `prepare_moodboard`: Prepare a moodboard with ManyMotions from a creative brief: five distinct visual directions (subject, setting, light, palette, style), each rendered by two image models as square images. Returns the settings and the credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare.
- `generate_result`: Start the prepared run in the user's ManyMotions account. Call it only after the user explicitly asked to generate: it consumes credits (the amount shown when preparing). It takes a few minutes: poll with get_result. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_result`: Check the progress of a run in the user's ManyMotions account and return the URLs of the finished files (audio, images or video) when it is done. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_moodboard` with:
   - `brief`: The creative brief: what the moodboard is for (brand, interior, fashion, event, project), the mood, colors, materials, era and style.
   and only the settings the user gave:

2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_result` with `project_id: project.id`.
4. The production takes several minutes. Call `get_result` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the URLs of the finished files.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

New images from a text brief only: do not use it for uploaded or reference images. Original directions only: no brand logos, artworks or artists named as the style, copyrighted characters or real people; offer an original description instead.
