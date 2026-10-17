# Tracking check

For "is my pixel working" or "conversions look wrong".

1. `audit_conversion_tracking`: whether the events the active ad sets optimise for are arriving, from browser and server.
2. `list_pixels`, then `pixel_stats` (up to 28 days, by event and hour) and `pixel_quality` (how well server events match
   people).
3. Compare with what the business counts: `revenue_report` if payments are sent in.
4. Name what is broken, since when, and the fix — in the site, the CRM or the Conversions API — in plain words.
