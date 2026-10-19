---
name: manymotions-video-generation
description: Generate a short AI video clip from a text prompt with ManyMotions (Kling, Veo, Seedance, Wan). Use when the user asks for a video, clip, shot, b-roll or animation made from a description.
---

# AI video generation with ManyMotions

## When to use

The user wants a video clip made from a text description: a product shot, b-roll, a scene, an animation, a social clip. One generation is one clip; for several shots, prepare one project per shot.

## Tools

- `prepare_media_forge_project`: builds the project from the prompt and settings and returns `project` (with `id`, `model_name`, `ratio`, `resolution`, `duration`, `count`) and `credits_required`. Free, nothing is generated.
- `generate_media_forge`: starts the generation of a prepared project (`project_id`, plus any setting the user changed). Spends credits from the signed-in account.
- `get_media_forge_job`: checks a job (`job_id`) and returns `job.status` and, when completed, `job.result`. It never starts a new generation, and a failed job gets its credits refunded.

## Steps

1. Write the prompt as a shot description: subject, action, setting, camera movement, lighting and style (up to 3,000 characters). Do not ask clarifying questions first: infer sensible settings.
2. Call `prepare_media_forge_project` with `tab: "video"`, the `prompt`, and only the settings the user asked for:
   - `ratio`: for example `"16:9"`, `"9:16"` or `"1:1"`;
   - `duration`: seconds, one of 4, 5, 6, 8, 10, 15 or 20 (each model supports its own subset; most go from 4 to 15);
   - `model_name`: for example `"Kling 3.0 Pro"` (the default), `"Veo 3.1"`, `"Seedance 2.0"` or `"Wan 2.7"`;
   - `count`: 1 to 4 clips.
3. Show the user `project.model_name`, ratio, duration and `credits_required`. If the user named a model and `project.model_name` is different, say that model is not available here and the default was used.
4. Wait for an explicit go-ahead. Then call `generate_media_forge` with `project_id: project.id`.
5. Video takes several minutes. Call `get_media_forge_job` with `job_id: job.id`, waiting between checks, until `job.status` is `completed`. Then give the absolute link in `job.result.video`.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- `account_required`: the user is not signed in; give `dashboard_url`, where the same project can be finished.
- `job.status` `failed` or `timeout`: report `job.error`; the credits of a failed job are refunded.

## Limits

Text-to-image and text-to-video only. Do not use these tools for uploaded or reference images, image editing, background replacement, image-to-video, video-to-video, remixing or upscaling: say the plugin does not support it and that https://manymotions.com has those tools.
