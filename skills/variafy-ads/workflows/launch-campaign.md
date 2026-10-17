# Launch a campaign

For "create a campaign" or "promote this offer".

1. `select_campaign_type` for the goal: it lists the steps and what is needed before building.
2. Read the landing page with `read_landing_page` to write texts from its facts, in its language.
3. Images: `list_images`, or `upload_link` for the person to add files, or `upload_image` from links. Videos:
   `list_videos` or `upload_video`.
4. Build with `build_campaign` (a form, two questions at a time) or `create_campaign` with all fields. Check
   `search_targeting` for interest ids; never guess them.
5. Show the preview: objective, budget, audience size, placements, texts, creative. The campaign is created paused.
6. Turn on only when the person asks: `launch_campaign` or `launch_adset` — say plainly that spend starts.
