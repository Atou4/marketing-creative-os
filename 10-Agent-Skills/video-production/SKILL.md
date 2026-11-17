---
name: video-production
description: Plan and produce product demos, explainers, launch videos and social clips from a creative brief. Use when asked to script, storyboard, record, narrate, edit or review a video, including web or mobile product walkthroughs.
---
# Video production

Create a useful, truthful video for a specific audience. Follow explicit user directions, including their budget and permission to publish.

For platform-specific short-form guidance (hooks, safe zones, pacing for Reels, TikTok, Shorts), use the `reel` skill alongside this one. This skill covers the whole pipeline: brief, script, capture, narration, edit, and verification of the exported file.

## Mandatory context
Read `01-Brand-Brain/MASTER-CONTEXT.md`, relevant `02-Product-Marketing/` notes, and project context first.

## Truth
Never invent capabilities, results, customers, endorsements, statistics, testimonials, partnerships, or product behavior. Distinguish evidence, assumptions and hypotheses.

## Strategy
1. Identify audience, objective, distribution, format, language, duration, budget, and intended action. Infer reasonable defaults; ask only when a missing choice materially affects the work.
2. Choose a clear message and an angle before drafting.
3. Write a concise creative brief before rendering: a story with a hook, visual proof, outcome and call to action.

## Script and production plan
4. Produce narration, concise on-screen text and a timed storyboard showing the actual visual for each claim. Specify which footage exists and what must be captured or verified. Use fictional demo data for public-facing examples.
5. Choose methods from the brief: record real browser, device or simulator workflows; use user-provided assets or generated visuals only where appropriate. Never portray a generated screen as a real product capability.
6. Respect budget. Prefer free or locally runnable tools where requested. Kokoro is one option for local generated narration; check the actual model, voice and asset licence and suitability for the language and intended use. Do not promise a particular service is always free.
7. Generate short narration samples when voice choice matters. Save the reusable script, source assets and individual clips. Use music only where it helps and the licence permits.

## Assemble
8. Edit for the destination and provide captions. Make key ideas understandable with audio muted; keep text readable on the target device. Do not claim a workflow was demonstrated until it has actually been tested.

## Verify the exported file
9. Inspect the exported video from first frame to last. Do not review the project file or the plan instead of the output.

   Measure with `ffprobe` and `ffmpeg` (check they are installed first):

   ```bash
   # duration, resolution, frame rate, codecs
   ffprobe -v error -show_entries stream=codec_type,codec_name,width,height,r_frame_rate:format=duration -of default=nw=1 video.mp4
   # one frame per second to look at, for artifacts, text legibility and sensitive information
   mkdir -p frames && ffmpeg -v error -i video.mp4 -vf fps=1,scale=640:-1 frames/f_%03d.png
   # audio level: flag silence or clipping
   ffmpeg -i video.mp4 -af volumedetect -vn -f null - 2>&1 | grep -E "mean_volume|max_volume"
   ```

   Check each of these and report what you saw, not that you checked:
   - It plays end to end, and the duration and aspect ratio match the brief and the destination.
   - Narration is audible and not clipped, and captions match the audio and are timed correctly.
   - Every claim on screen matches what the real product does. Mark anything you could not confirm.
   - No visual artifacts, and no real names, emails, tokens, or customer data visible in any frame.
   - The final call to action is present and correct.
10. Deliver the video, the source project or reproducible assets, the script, licence and source details for any third-party material, and a list of unverified claims and limitations. Stage for review unless the user has already authorized publication; follow project rules and user instructions.
