---
name: manymotions-ai-video-editor
description: Edit an existing ManyMotions video project: timeline clips, order, transitions, subtitles and MP4 export. Use when the user asks to edit, cut, reorder, caption or export a video in their ManyMotions account.
---

# Edit ManyMotions videos

## When to use

The user wants to edit a video project that already exists in their ManyMotions account: arrange library clips on the timeline, change their order, add transitions or subtitles, and export the MP4.

## Tools

- `video_editor_list_projects`: List the user's ManyMotions video projects with id, name, aspect ratio and last update. Start here to find the project to edit.
- `video_editor_list_videos`: List the videos inside a project. The videos of a project share its media library and each has its own timeline; pass a video_id to the other tools to work on one of them.
- `video_editor_get_state`: Get a project's videos, its media library (assets with id, kind, name and url) and the clip ids of one video's timeline. Use the asset ids with video_editor_add_clip; for durations and positions use video_editor_get_timeline. Asset and clip ids are in the `id` field; urls are absolute.
- `video_editor_get_timeline`: Read a video's full timeline: every clip per track in playback order with clip_id, asset_id, name, kind, duration_sec, timeline_start_sec and any non-default trim, speed or volume, plus the captions and the total duration of the video track. Read it before editing and reference clips by clip_id.
- `video_editor_add_clip`: Place an asset of the project's library on a video's timeline. When track is omitted it follows the asset kind: video and image go on the video track (an image is held for duration_sec, default 1 second), audio on the voice track. position is the 0-based index on that track (default: the end). Returns clip_id.
- `video_editor_remove_clip`: Remove a clip from its timeline by clip_id. The asset stays in the library and can be placed again with video_editor_add_clip.
- `video_editor_reorder_clip`: Move a clip to a new 0-based position on its track; the other clips of that track shift to make room.
- `video_editor_set_transition`: Set or clear the transition from a clip into the next clip of the project's main video, rendered on export. type is a preset such as fade, dissolve, slideleft, slideright, wipeleft or circleopen, or "none" to clear it. Reference the clip by clip_id.
- `video_editor_upload_captions`: Add subtitles to a video from SRT or VTT text passed in srt. The cues become timed captions burned into the exported MP4. render "static" (default) shows each cue as a line, "wordpop" one word at a time, "karaoke" a highlight sweeping across the line. Replaces the video's existing captions unless append is true.
- `video_editor_export_captions`: Export a video's captions as SRT or VTT text.
- `video_editor_export`: Render a video's timeline into one MP4 (clips in order, transitions, audio mix, burned-in captions) and return its video_url, which also lands in the project's library. fit letterboxes clips of a different shape, fill crops them.

## Steps

1. Call `video_editor_list_projects` and pick the project with the user. If it has several videos, `video_editor_list_videos` lists them; pass `video_id` to work on one (omitted = the project's main video).
2. Read `video_editor_get_timeline` before editing, and `video_editor_get_state` for the media library. Reference clips by `clip_id` and library assets by asset `id`, never by name.
3. Edit with `video_editor_add_clip`, `video_editor_remove_clip`, `video_editor_reorder_clip`, `video_editor_set_transition` and `video_editor_upload_captions`, reading the timeline again after changes.
4. Call `video_editor_export` and give the user the absolute `video_url`.

## Limits

Editing only: this plugin does not generate videos, images, voices or music, does not upload or import files, does not create projects and does not trim clips or change their speed or volume. For those, point the user to the ManyMotions editor at https://manymotions.com/dashboard/media-studio. Editing and exporting do not spend credits; every tool needs the user's ManyMotions account.
