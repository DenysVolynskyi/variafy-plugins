# Refresh creatives

For "my ads are tired", "write new texts" or "which ads need a new creative".

1. `detect_creative_fatigue`: frequency, falling link CTR and age of each active ad.
2. `ad_copy_brief` for the campaign: which texts and headlines won beyond chance, the money they brought, the landing
   pages and the length limits.
3. Write 3–5 new primary texts and headlines from the winners and the landing page. Respect the length limits.
4. New ads with the new creative go in as paused (`create_ad_creative`, `create_ad`, or `copy_ad_to_new_adset` to test
   a winner in a fresh ad set). The person decides what to turn on.
5. When the creative comes in several sizes, make ONE ad of them: `create_ad_creative` with image_hashes (feed 1:1 or 4:5,
   9:16 for stories and Reels, 1.91:1 for the Facebook right column) or `create_video_creative` with video_ids (feed video
   and 9:16 video). Sizes are matched to placements automatically; one text of each kind only.
