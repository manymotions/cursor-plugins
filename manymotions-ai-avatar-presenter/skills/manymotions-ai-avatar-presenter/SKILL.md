---
name: manymotions-ai-avatar-presenter
description: Create an explainer, a lesson or a self-introduction spoken to camera by an AI presenter with ManyMotions. Use when the user asks for an explainer, a lesson or a self-introduction spoken to camera by an AI presenter.
---

# AI Avatar Video with ManyMotions

## When to use

The user wants an explainer, a lesson or a self-introduction spoken to camera by an AI presenter.

## Tools

- `prepare_presenter_video`: Prepare a talking AI avatar presenter video with ManyMotions: an explainer or lesson that teaches one concept, or a self-introduction for a person, a business or a channel, spoken to camera by an AI presenter with an AI voice. Not an advertisement: no product pitch and no call to action. ManyMotions writes the script scene by scene, generates the keyframes and the scene videos with AI voice, and edits the final cut. Returns the plan: scene count and credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare.
- `generate_video`: Start the AI production of a prepared video in the user's ManyMotions account: creative direction, script, keyframes, scene videos with AI voice, final cut. Call it only after the user explicitly asked to generate: it consumes credits (250 per scene). The run takes several minutes: poll with get_video. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_video`: Check the progress of a video run in the user's ManyMotions account (which of the 7 steps are done, the script once written) and return the finished MP4 URL when the final cut is ready. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_presenter_video` with:
   - `topic`: What the video explains, or who or what it introduces.
   and only the settings the user gave:
   - `video_type` (`explainer`, `introduction`): explainer (default): teaches one concept, lesson or how-to; introduction: introduces a person, a business or a channel.
   - `audience`: Who it is for and their level, e.g. high-school students, new employees, beginners.
   - `key_points`: Points, facts or steps that must be covered.
   - `presenter`: How the AI presenter looks and sounds, e.g. a friendly teacher in her 40s in a bright classroom.
   - `language` (`English`, `Spanish`, `Portuguese`, `Korean`, `Japanese`, `Mandarin`, `Indonesian`): Spoken language. Default English.
   - `format` (`9:16`, `1:1`, `4:5`, `16:9`): Aspect ratio: 9:16 (default, TikTok, Reels, Shorts), 1:1, 4:5 or 16:9 (YouTube).
   - `duration` (`8s`, `15s`, `30s`, `45s`, `60s`): Target length: 8s = 2 scenes, 15s = 3 (default), 30s = 5, 45s = 7, 60s = 8. 250 credits per scene.
   - `speech_speed` (`slow`, `medium`, `medium-fast`, `fast`): Default medium.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_video` with `project_id: project.id`.
4. The production takes several minutes. Call `get_video` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the finished MP4 URL.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

New videos from text only: do not use it for uploaded or existing footage, photos of real people, editing, captions or dubbing; for those, point the user to ManyMotions.
