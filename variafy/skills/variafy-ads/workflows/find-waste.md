# Find wasted spend

For "where am I wasting money" or "what should I pause".

1. Use the business profile's goal and target (start_here). For lead accounts the target is cost per lead; for sales,
   ROAS. If the person sends payments to Variafy, `revenue_report` judges by real money — prefer it.
2. `analyze_wasted_spend` over 30 days (or the window the person names). It classifies campaigns: wasted, below target,
   learning, too little data.
3. For the wasted and below-target ones, look one level down when it matters: `analyze_placements`,
   `analyze_audiences` or `detect_creative_fatigue` for the campaign.
4. Present: total spend without results, the 3–5 biggest items, and why. Never call learning or too-little-data
   campaigns waste.
5. Propose pauses or lower budgets with previews (`pause_adset`, `pause_ad`, `lower_budget`). Confirm only what the person
   picks.
