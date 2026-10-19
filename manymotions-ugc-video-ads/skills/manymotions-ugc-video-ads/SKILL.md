---
name: manymotions-ugc-video-ads
description: Produce a UGC-style AI video ad with presenter and voice from a product brief with ManyMotions. Use when the user asks for a video ad, UGC ad, TikTok, Reels or Shorts ad for a product or brand.
---

# UGC video ads with ManyMotions

## When to use

The user wants a short video ad for a product or brand, in the style of user-generated content, with a presenter speaking to camera.

## Tools

- `prepare_ugc_video_ad`: builds the ad brief and returns the plan: `scenes`, `credits_required` and `project` (with `id`). Free, nothing is generated.
- `generate_ugc_video_ad`: starts the production of a prepared ad (`project_id`): strategy, script, keyframes, scene videos with an AI presenter and voice, final cut. Spends 250 credits per scene from the signed-in account.
- `get_ugc_video_ad`: checks the run (`project_id`): which of the 7 steps are done, the script once written, and `video_url` when the final cut is ready. Read-only.

## Steps

1. Call `prepare_ugc_video_ad` with:
   - `product_description` (required): what the product is, key benefits, what makes it unique;
   - `target_audience` (required): who the ad speaks to;
   - only if the user gave them: `product_url`, `language` (English, Spanish, Portuguese, Korean, Japanese, Mandarin, Indonesian; default English), `tone` (energetic, friendly, professional, urgent), `video_format` (`9:16` default, `1:1`, `4:5`, `16:9`), `duration` (`8s` = 2 scenes, `15s` = 3 default, `30s` = 5, `45s` = 7, `60s` = 8), `template` (`ugc_ad`, `podcast_clip`, `testimonial`, `product_demo`, `transformation`, `tutorial`, `product_review`, `unboxing`), `speech_speed` (slow, medium, medium-fast default, fast).
2. Show the user the plan: scenes and `credits_required`.
3. Wait for an explicit go-ahead. Then call `generate_ugc_video_ad` with `project_id: project.id`.
4. The run takes several minutes. Call `get_ugc_video_ad` with the same `project_id`, waiting between checks, and report the steps done. When the final cut is ready, give `video_url`.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot produce the ad yet and give `dashboard_url`. Do not insist or repeat it.
- `account_required`: the user is not signed in; give `dashboard_url`, where the same ad can be finished.

## Limits

Do not promise a real person, a celebrity or a cloned voice: the presenter and the voice are AI-generated.
