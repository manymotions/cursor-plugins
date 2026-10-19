---
name: manymotions-logo-maker
description: Create AI logo concepts for a brand with ManyMotions Logo Maker. Use when the user asks for a logo, brand mark, icon or logo ideas for a company, product or project.
---

# AI logo concepts with ManyMotions

## When to use

The user wants logo concepts for a brand, product, app, shop or project.

## Tools

- `prepare_logo_project`: builds the logo project from the brief and returns `project` (with `id`, `model_name`, `count`) and `credits_required`. Free, nothing is generated.
- `generate_logo`: starts the generation of a prepared project (`project_id`); by default 4 raster logo concepts in one job. Spends credits from the signed-in account.
- `get_logo_job`: checks a job (`job_id`) and returns its status and, when completed, the logo images. It never starts a new generation, and a failed job gets its credits refunded.

## Steps

1. Write the `prompt` as a logo brief: brand name, industry, style, colors, and end with "flat vector logo design on a plain background, no mockup" (up to 3,000 characters).
2. Call `prepare_logo_project` with the `prompt`. Pass `count` (1 to 4) only if the user asked for a number of concepts.
3. Show the user the brief, the number of concepts and `credits_required`.
4. Wait for an explicit go-ahead. Then call `generate_logo` with `project_id: project.id`.
5. Call `get_logo_job` with `job_id: job.id` until the job is completed, then give the absolute PNG links.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- A failed job: report the error; its credits are refunded.

## Limits

The output is raster PNG concepts, not vector files. Do not use these tools to edit an uploaded logo or image.
