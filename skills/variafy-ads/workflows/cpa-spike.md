# Why did cost per result rise

For "why are leads more expensive" or "CPA went up".

1. `explain_anomaly` with the metric (cost per result, CPA, CPL, ROAS, CTR, CPM) and the period. It compares with 30, 60
   and 90-day baselines, finds the campaigns and ad sets that moved it, the funnel step, and what was edited in those days.
2. If it points at creatives, follow with `detect_creative_fatigue`; at audiences, `analyze_audiences`; at placements,
   `analyze_placements`; at tracking, `audit_conversion_tracking`.
3. `activity_log` shows what changed in the ad account: budget, targeting and bid edits often restart learning.
4. Answer in this order: what rose and by how much, the main cause with its numbers, what is noise, what to do.
5. Changes only with previews, and only those the person chooses.
