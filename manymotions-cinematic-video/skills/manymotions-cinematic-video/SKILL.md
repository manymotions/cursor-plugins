---
name: manymotions-cinematic-video
description: Create a single cinematic text-to-video shot with a named camera move with ManyMotions. Use when the user asks for a single cinematic text-to-video shot with a named camera move.
---

# Cinematic Video with ManyMotions

## When to use

The user wants a single cinematic text-to-video shot with a named camera move.

## Tools

- `prepare_cinematic_video`: Prepare a cinematic text-to-video shot with ManyMotions from a scene description and one named camera move from the Cinema Studio catalog (61 moves: dolly, crane, orbit, crash zoom, dolly zoom, FPV drone, bullet time, whip pan...), plus shot size, lighting, look, format, length and a cinema video model. Returns the settings and the credits required. Nothing is generated and no credits are spent. No sign-in is needed to prepare. Text-to-video only: do not use it for uploaded, attached or reference images or videos (image-to-video, editing, upscaling); for those, point the user to ManyMotions.
- `generate_media_forge`: Start generation for a prepared text-to-image or text-to-video Media Forge project for the signed-in ManyMotions user. Call this only after the user has explicitly asked to generate — never on your own initiative, since it consumes the user's credits. Returns job id and status. It needs the user's ManyMotions account: the client asks the user to sign in when it is missing. Use this only for text-to-image or text-to-video prompts.
- `get_media_forge_job`: Refresh an existing ManyMotions Media Forge generation job in the user's ManyMotions account. Refresh can save completed media or refund credits for a failed job; it never starts a new generation.

## Steps

1. Call `prepare_cinematic_video` with:
   - `scene`: What happens in the shot: subject, action and setting.
   and only the settings the user gave:
   - `camera_move` (`zoom-in`, `zoom-out`, `crash-zoom-in`, `crash-zoom-out`, `rapid-zoom-in`, `rapid-zoom-out`, `yoyo-zoom`, `eating-zoom`, `dolly-in`, `dolly-out`, `dolly-left`, `dolly-right`, `dolly-zoom-in`, `dolly-zoom-out`, `super-dolly-in`, `super-dolly-out`, `double-dolly`, `crane-up`, `crane-down`, `crane-over-head`, `jib-up`, `jib-down`, `pan-left`, `pan-right`, `whip-pan`, `tilt-up`, `tilt-down`, `arc-left`, `arc-right`, `360-orbit`, `lazy-susan`, `3d-rotation`, `fpv-drone`, `handheld`, `head-tracking`, `object-pov`, `hero-cam`, `car-chasing`, `car-grip`, `buckle-up`, `road-rush`, `dutch-angle`, `snorricam`, `bullet-time`, `overhead`, `fisheye`, `focus-change`, `bts`, `robo-arm`, `wiggle`, `glam`, `incline`, `hyperlapse`, `timelapse`, `low-shutter`, `through-object-in`, `through-object-out`, `mouth-in`, `eyes-in`, `flying-cam-transition`, `static`): One camera move: zoom-in (Zoom In), zoom-out (Zoom Out), crash-zoom-in (Crash Zoom In), crash-zoom-out (Crash Zoom Out), rapid-zoom-in (Rapid Zoom In), rapid-zoom-out (Rapid Zoom Out), yoyo-zoom (YoYo Zoom), eating-zoom (Eating Zoom), dolly-in (Dolly In), dolly-out (Dolly Out), dolly-left (Dolly Left), dolly-right (Dolly Right), dolly-zoom-in (Dolly Zoom In), dolly-zoom-out (Dolly Zoom Out), super-dolly-in (Super Dolly In), super-dolly-out (Super Dolly Out), double-dolly (Double Dolly), crane-up (Crane Up), crane-down (Crane Down), crane-over-head (Crane Over The Head), jib-up (Jib Up), jib-down (Jib Down), pan-left (Pan Left), pan-right (Pan Right), whip-pan (Whip Pan), tilt-up (Tilt Up), tilt-down (Tilt Down), arc-left (Arc Left), arc-right (Arc Right), 360-orbit (360 Orbit), lazy-susan (Lazy Susan), 3d-rotation (3D Rotation), fpv-drone (FPV Drone), handheld (Handheld), head-tracking (Head Tracking), object-pov (Object POV), hero-cam (Hero Cam), car-chasing (Car Chasing), car-grip (Car Grip), buckle-up (Buckle Up), road-rush (Road Rush), dutch-angle (Dutch Angle), snorricam (Snorricam), bullet-time (Bullet Time), overhead (Overhead), fisheye (Fisheye), focus-change (Focus Change), bts (BTS), robo-arm (Robo Arm), wiggle (Wiggle), glam (Glam), incline (Incline), hyperlapse (Hyperlapse), timelapse (Timelapse), low-shutter (Low Shutter), through-object-in (Through Object In), through-object-out (Through Object Out), mouth-in (Mouth In), eyes-in (Eyes In), flying-cam-transition (Flying Cam Transition), static (Static). One move per shot.
   - `shot` (`extreme-wide`, `wide`, `medium`, `medium-close-up`, `close-up`, `extreme-close-up`, `low-angle`, `high-angle`, `over-the-shoulder`, `aerial`): Shot size or angle the clip opens on.
   - `lighting`: Lighting, e.g. golden hour backlight, neon noir, candlelight, overcast daylight.
   - `look`: Color grade or film look, e.g. teal and orange, 35mm film grain, black and white, anamorphic flares.
   - `format` (`landscape`, `vertical`, `square`): landscape 16:9 (default), vertical 9:16 or square 1:1 (square not on Veo).
   - `duration`: Length in seconds; must be one the model supports (Kling 5/10/15, Veo 4/6/8, Seedance 4-15, Wan 3-15). Default: the model's shortest.
   - `model_id` (`fal-ai/veo3.1`, `fal-ai/veo3.1/fast`, `fal-ai/kling-video/v3/pro/text-to-video`, `fal-ai/kling-video/v3/standard/text-to-video`, `fal-ai/kling-video/v2.6/pro/text-to-video`, `bytedance/seedance-2.5/text-to-video`, `fal-ai/wan/v2.7/text-to-video`, `bytedance/seedance-2.0/text-to-video`, `bytedance/seedance-2.0/fast/text-to-video`, `fal-ai/kling-video/o3/pro/text-to-video`, `fal-ai/bytedance/seedance/v1.5/pro/text-to-video`): Cinema video model: fal-ai/veo3.1 (Veo 3.1), fal-ai/veo3.1/fast (Veo 3.1 Fast), fal-ai/kling-video/v3/pro/text-to-video (Kling 3.0 Pro), fal-ai/kling-video/v3/standard/text-to-video (Kling 3.0 Standard), fal-ai/kling-video/v2.6/pro/text-to-video (Kling 2.6 Pro), bytedance/seedance-2.5/text-to-video (Seedance 2.5), fal-ai/wan/v2.7/text-to-video (Wan 2.7), bytedance/seedance-2.0/text-to-video (Seedance 2.0), bytedance/seedance-2.0/fast/text-to-video (Seedance 2.0 Fast), fal-ai/kling-video/o3/pro/text-to-video (Kling O3 Pro), fal-ai/bytedance/seedance/v1.5/pro/text-to-video (Seedance v1.5 Pro). Default Kling 3.0 Pro.
2. Show the user the plan and `credits_required`. Nothing is generated and no credits are spent yet.
3. Wait for an explicit go-ahead. Then call `generate_media_forge` with `project_id: project.id`. If it returns `state: "confirmation_required"`, tell the user the cost and, after they say yes to it, call `generate_media_forge` again with `confirm_credits` equal to `credits_required`.
4. The production takes several minutes. Call `get_media_forge_job` with `job_id: job.id`, waiting between checks, and report progress. When it is done, give the absolute link in `job.result.video`.

## Account states

- `billing_required` or `insufficient_credits`: say plainly that the account cannot generate yet and give `dashboard_url`. Do not insist or repeat it.
- Every tool needs the user's ManyMotions account: Cursor asks the user to sign in when the plugin connects.

## Limits

Text-to-video only: do not use it for uploaded, attached or reference images or videos (image-to-video, editing, upscaling); for those, point the user to ManyMotions.
