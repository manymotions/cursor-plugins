---
name: manymotions-fitness-video
description: Create a workout or training short with an AI athlete and a short narration with ManyMotions. Use when the user asks for a workout or training short with an AI athlete and a short narration.
---

# Fitness Videos with ManyMotions

## When to use

The user wants a workout or training short with an AI athlete and a short narration.

## Tools

- `prepare_fitness_video`: Prepare a workout or training video with ManyMotions from the exercise or routine you describe: an AI athlete training in a gym, outdoors or at home, with effort and form shown clearly and a short narration. ManyMotions writes the script scene by scene, generates the keyframes and the scene videos with AI voice, and edits the final cut. Returns the plan: scene count and credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare.
- `generate_video`: Start the AI production of a prepared video in the user's ManyMotions account: creative direction, script, keyframes, scene videos with AI voice, final cut. Call it only after the user explicitly asked to generate: it consumes credits (250 per scene). The run takes several minutes: poll with get_video. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_video`: Check the progress of a video run in the user's ManyMotions account (which of the 7 steps are done, the script once written) and return the finished MP4 URL when the final cut is ready. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_fitness_video` with:
   - `workout`: The exercise, routine or training goal, e.g. a 3-move kettlebell finisher, hill sprints.
   and only the settings the user gave:
   - `setting` (`gym`, `outdoor`, `home`): gym (default), outdoor or home.
   - `athlete`: How the AI athlete looks, e.g. a woman in her 30s in black training gear.
   - `message`: What the narration should say: a cue, a motivation, the key form points.
   - `language` (`English`, `Spanish`, `Portuguese`, `Korean`, `Japanese`, `Mandarin`, `Indonesian`): Spoken language. Default English.
   - `format` (`9:16`, `1:1`, `4:5`, `16:9`): Aspect ratio: 9:16 (default, TikTok, Reels, Shorts), 1:1, 4:5 or 16:9 (YouTube).
   - `duration` (`8s`, `15s`, `30s`, `45s`, `60s`): Target length: 8s = 2 scenes, 15s = 3 (default), 30s = 5, 45s = 7, 60s = 8. 250 credits per scene.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_video` with `project_id: project.id`.
4. The production takes several minutes. Call `get_video` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the finished MP4 URL.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

New videos from text only: do not use it for uploaded or existing footage, photos of real people, editing, captions or dubbing; for those, point the user to ManyMotions. Original characters only: do not use it for copyrighted characters, existing franchises or real celebrities; offer the user an original alternative instead.
