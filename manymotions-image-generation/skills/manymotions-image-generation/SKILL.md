---
name: manymotions-image-generation
description: Generate AI images from a text prompt with ManyMotions (Nano Banana, Flux, Seedream, Ideogram). Use when the user asks for an image, illustration, photo, poster, thumbnail or visual made from a description.
---

# AI image generation with ManyMotions

## When to use

The user wants images made from a text description: illustrations, product photos, posters, thumbnails, concept art, social visuals.

## Tools

- `prepare_media_forge_project`: builds the project from the prompt and settings and returns `project` (with `id`, `model_name`, `ratio`, `resolution`, `duration`, `count`) and `credits_required`. Free, nothing is generated.
- `generate_media_forge`: starts the generation of a prepared project (`project_id`, plus any setting the user changed). Spends credits from the signed-in account.
- `get_media_forge_job`: checks a job (`job_id`) and returns `job.status` and, when completed, `job.result`. It never starts a new generation, and a failed job gets its credits refunded.

## Steps

1. Write the prompt as an image description: subject, composition, setting, lighting, style and any text that must appear (up to 3,000 characters). Do not ask clarifying questions first: infer sensible settings.
2. Call `prepare_media_forge_project` with `tab: "image"`, the `prompt`, and only the settings the user asked for:
   - `ratio`: for example `"1:1"`, `"16:9"`, `"9:16"`, `"4:5"` or `"3:2"`;
   - `resolution`: `"1K"`, `"2K"` or `"4K"`, depending on the model;
   - `count`: 1 to 4 images;
   - `model_name`: for example `"Nano Banana Pro"` (the default), `"Flux 2 Pro"`, `"Seedream 4.5"` or `"Ideogram v3"`.
3. Show the user `project.model_name`, ratio, resolution, count and `credits_required`. If the user named a model and `project.model_name` is different, say that model is not available here and the default was used.
4. Wait for an explicit go-ahead. Then call `generate_media_forge` with `project_id: project.id`.
5. Call `get_media_forge_job` with `job_id: job.id` until `job.status` is `completed`. Then give the absolute links in `job.result.images`.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- `account_required`: the user is not signed in; give `dashboard_url`, where the same project can be finished.
- `job.status` `failed` or `timeout`: report `job.error`; the credits of a failed job are refunded.

## Limits

Text-to-image and text-to-video only. Do not use these tools for uploaded or reference images, image editing, background replacement, image-to-video, video-to-video, remixing or upscaling: say the plugin does not support it and that https://manymotions.com has those tools.
