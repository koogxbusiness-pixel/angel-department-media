# POSTER runbook (laptop task, Claude in Chrome)

Runs on the owner's laptop. It only posts; the cloud maker makes everything.

1. Read `queue/post_queue.json` in this repo (koogxbusiness-pixel/angel-department-media) with the GitHub connector.
2. For each item whose `scheduled_for_et` is still in the future and has a platform with `posted_to` = null:
   - Download `media_url` into the connected folder "Angel Department daily content run" as `<key>.mp4` (if over the Chrome upload limit, make an under-10 MB copy in `upload_10mb/`, full length, no trimming).
   - Schedule it in each app's NATIVE scheduler at `scheduled_for_et` (Eastern time; check the scheduler's time zone):
     - TikTok: tiktok.com/tiktokstudio/upload -> caption -> AI-generated content ON -> Schedule.
     - Instagram: business.facebook.com (Meta Business Suite) -> Create reel -> share to Instagram only -> caption -> Schedule. `format: breakdown` items also go out as an Instagram carousel from `carousel_urls` (same caption).
     - YouTube: studio.youtube.com -> Upload -> `youtube_title`, caption as description, `youtube_tags` -> altered/synthetic content = Yes -> Schedule.
   - Before scheduling, check the app's scheduled list so nothing is scheduled twice.
   - Set `posted_to.<platform>` = "scheduled" (or "failed" after two tries, with `posted_note`). Commit the file back after each item.
3. Comments (only when posting is active): reply to new comments on the last 7 days of posts on Instagram and TikTok in the brand voice, ending with a question where it fits; pin one brand comment per new post (the next part or the waitlist). Never from a second account.
4. Add one line to the Morning Page (Claude Doc linked in AI-Video-Editing autopilot/MORNING_PAGE.md, https://claude.ai/artifact/EW4MkArBpV6aTSYVgr1EkR) under "What posted": what was scheduled where, and anything that needs the owner.

5. Outlier check (TikTok, light): only once the owner has approved accounts (listed on the Morning Page by the maker). Open each approved TikTok account's profile once, at a normal pace, read the view counts on the grid, and for any video at 10x that account's usual views add a line to the Morning Page: `POSTER OUTLIER: <url> <views> vs usual <median>`. Read only: never like, follow, comment or download.

Rules: use the Claude in Chrome browser that is signed in to TikTok Studio as angel_department (Nov 28: "Browser 1"; "Browser 2" is a dead pairing). If more than one is connected, check each by only opening tiktok.com/tiktokstudio, use the signed-in one, and say which on the Morning Page; if none or both are signed in, stop and tell the owner.
If you can't write to GitHub (permission denied), put your posted_to results as one line on the Morning Page under "What posted" starting with `POSTER RESULT:` (key, platform, scheduled/failed); the maker copies them into the queue.
If a media_url isn't on raw.githubusercontent.com and the laptop shell can't download it, download it through Chrome and look for it in the user's Downloads; if it can't be moved into the run folder, ask the owner to move it. Never type passwords or codes; if a site asks to log in, stop and tell the owner. Never create Metricool posts. Never say "made to order". Work at a normal human pace, one upload at a time.
