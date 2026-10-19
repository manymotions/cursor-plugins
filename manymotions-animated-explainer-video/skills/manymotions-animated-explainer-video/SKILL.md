---
name: manymotions-animated-explainer-video
description: Create an animated explainer of about 30 seconds with illustrated scenes and a voiceover, no presenter with ManyMotions. Use when the user asks for an animated explainer of about 30 seconds with illustrated scenes and a voiceover, no presenter.
---

# Explainer Video with ManyMotions

## When to use

The user wants an animated explainer of about 30 seconds with illustrated scenes and a voiceover, no presenter.

## Tools

- `prepare_animated_explainer`: Prepare an animated explainer video of about 30 seconds with ManyMotions that makes one topic simple: four illustrated scenes with motion and a voiceover, no presenter on camera, merged into one MP4. Returns the settings and the credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare.
- `generate_result`: Start the prepared run in the user's ManyMotions account. Call it only after the user explicitly asked to generate: it consumes credits (the amount shown when preparing). It takes a few minutes: poll with get_result. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_result`: Check the progress of a run in the user's ManyMotions account and return the URLs of the finished files (audio, images or video) when it is done. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_animated_explainer` with:
   - `topic`: What the video explains and the key points it must make.
   and only the settings the user gave:
   - `audience`: Who it is for, e.g. beginners, customers, students, investors.
   - `style`: Visual style and tone, e.g. flat 2D, isometric, hand-drawn, playful, corporate.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_result` with `project_id: project.id`.
4. The production takes several minutes. Call `get_result` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the URLs of the finished files.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

New animated videos from text only, with no presenter on camera: do not use it for uploaded footage, photos, real people, editing or captions. Original visuals only: no copyrighted characters, brand logos or real people.
