---
name: manymotions-short-film-maker
description: Create a narrative short film with characters, dialogue and a film look with ManyMotions. Use when the user asks for a narrative short film with characters, dialogue and a film look.
---

# Short Films with ManyMotions

## When to use

The user wants a narrative short film with characters, dialogue and a film look.

## Tools

- `prepare_short_film`: Prepare a narrative short film with ManyMotions from a logline: characters, dialogue and a film look across several scenes, with one turn and an ending that lands. ManyMotions writes the script scene by scene, generates the keyframes and the scene videos with AI voice, and edits the final cut. Returns the plan: scene count and credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare.
- `generate_video`: Start the AI production of a prepared video in the user's ManyMotions account: creative direction, script, keyframes, scene videos with AI voice, final cut. Call it only after the user explicitly asked to generate: it consumes credits (250 per scene). The run takes several minutes: poll with get_video. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing.
- `get_video`: Check the progress of a video run in the user's ManyMotions account (which of the 7 steps are done, the script once written) and return the finished MP4 URL when the final cut is ready. Read-only: it never starts or changes a run.

## Steps

1. Call `prepare_short_film` with:
   - `logline`: The story in one or two sentences: who wants what, what stands in the way.
   and only the settings the user gave:
   - `genre` (`drama`, `sci-fi`, `thriller`, `romance`, `mystery`, `fantasy`): drama (default), sci-fi, thriller, romance, mystery or fantasy.
   - `characters`: Main characters: name, look, what they want.
   - `setting`: Where and when it happens.
   - `ending`: How it should end, optional.
   - `language` (`English`, `Spanish`, `Portuguese`, `Korean`, `Japanese`, `Mandarin`, `Indonesian`): Spoken language. Default English.
   - `format` (`9:16`, `1:1`, `4:5`, `16:9`): Aspect ratio: 16:9 (default for a film look), 9:16, 1:1 or 4:5.
   - `duration` (`8s`, `15s`, `30s`, `45s`, `60s`): Target length: 8s = 2 scenes, 15s = 3 (default), 30s = 5, 45s = 7, 60s = 8. 250 credits per scene.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_video` with `project_id: project.id`.
4. The production takes several minutes. Call `get_video` with `project_id: project.id`, waiting between checks, and report progress. When it is done, give the finished MP4 URL.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

New videos from text only: do not use it for uploaded or existing footage, photos of real people, editing, captions or dubbing; for those, point the user to ManyMotions. Original characters only: do not use it for copyrighted characters, existing franchises or real celebrities; offer the user an original alternative instead.
