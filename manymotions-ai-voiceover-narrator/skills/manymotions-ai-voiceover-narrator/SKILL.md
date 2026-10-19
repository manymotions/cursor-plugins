---
name: manymotions-ai-voiceover-narrator
description: Create a spoken voiceover of the user's own text, returned as an MP3 with ManyMotions. Use when the user asks for a spoken voiceover of the user's own text, returned as an MP3.
---

# AI Voiceover with ManyMotions

## When to use

The user wants a spoken voiceover of the user's own text, returned as an MP3.

## Tools

- `prepare_voiceover`: Prepare a spoken voiceover of a text with ManyMotions: the text is paced for listening (pauses, emphasis, emotional cues) in the delivery style the user describes, then read by a stock AI voice and returned as an MP3. Returns the settings and the credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare. Text to speech of the user's own text, read by one stock AI voice: do not use it for voice cloning, imitating a real person's voice, uploaded audio, songs or music.
- `generate_result`: Start the prepared run in the user's ManyMotions account. Call it only after the user explicitly asked to generate: it consumes credits (the amount shown when preparing). It takes a few minutes: poll with get_result. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_result`: Check the progress of a run in the user's ManyMotions account and return the URLs of the finished files (audio, images or video) when it is done. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_voiceover` with:
   - `text`: The text to read, in the user's own words: a script, an article, a lesson, a story or a product description.
   and only the settings the user gave:
   - `delivery_style`: How it should sound, e.g. warm narrator, calm and slow, energetic promo, documentary, bedtime story. Default: warm narrator.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_result` with `project_id: project.id`.
4. The production takes several minutes. Call `get_result` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the URLs of the finished files.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

Text to speech of the user's own text, read by one stock AI voice: do not use it for voice cloning, imitating a real person's voice, uploaded audio, songs or music.
