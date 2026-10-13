---
name: variafy-ads
description: Work on Meta ad accounts through the Variafy connector — read results, find wasted spend, explain why cost per result rose, prepare and launch campaigns, report to a client — with every change previewed first. Use whenever the person asks about their Meta (Facebook, Instagram) ads, ad accounts, campaigns, budgets, creatives, leads, ROAS or tracking and the Variafy tools are connected.
---

# Variafy: Meta ads from the assistant

Variafy connects this conversation to the person's own Meta ad accounts. Reading is free and changes nothing. Every change
takes two calls: the first returns a preview (what changes, in which ad account, what it does to spend), the second —
with the `confirm_token` from that preview — applies it.

## Start of every conversation

1. Call `start_here` once. It names the connected ad accounts, today's advice, the business profile of each ad account and
   the rules for changes. Keep to the business profile's goal, target cost per result or ROAS, and rules in every answer.
2. With several ad accounts connected, name the ad account you are working in, and pass `connection` in the arguments.
3. No business profile yet: offer once to build one — `infer_business_profile`, show the suggestion, correct it with the
   person, then `save_business_profile`.

## How to call

- Operations sit behind routers: `meta_ads_read`, `meta_ads_create`, `meta_ads_update`, `meta_ads_delete`, called as
  `{"action":"execute","tool_name":"…","arguments":{…}}`. `get_insights`, `audit_account`, `audit_conversion_tracking` and
  `revenue_report` are their own tools.
- Before the first call of an operation, read its schema: `get_tool_schema {"tool_names":[…]}`. `search_tools` finds an
  operation by words; `meta_ads_read {"action":"list_tools"}` lists them all.
- Money is in the ad account currency, regular units ("150", not cents). Dates are in the ad account time zone.

## Changes

- Show the preview to the person in plain words before confirming. Never confirm a change they did not ask for.
- If the preview says spend can grow, say so plainly. If there is no `confirm_token`, only `approve_url`, give the person the
  link: a signed-in person approves it in the console.
- New campaigns, ad sets and ads are created paused. Turning them on is a separate step the person asks for.
- To make an ad set in a leads or sales campaign optimise for something else (another pixel event, landing page views,
  purchase value with a minimum ROAS), use `rebuild_adset`: Meta does not change these on a published ad set. Then the person
  launches the new ad set and pauses the old one. `update_optimization_goal` is for traffic and awareness campaigns.
- After a change, read the object back and say what is true now.
- When something did not work — or the person asks why — call `why_did_this_fail`: it names the real error, the cause and
  who fixes it. If it says the call was wrong, fix the call yourself; do not ask the person to reconnect at random.
  A pasted error message goes to `explain_error`.

## When numbers are asked for

Finish the read with `show_dashboard` (cards and a sortable table in the chat), then one or two sentences in words. Do not
draw tables by hand when the dashboard is available.

## Workflows

Pick the one that matches the request and follow it:

- [Morning check](workflows/morning-check.md) — "how are my ads doing", "anything I should do today"
- [Find wasted spend](workflows/find-waste.md) — "where am I wasting money", "what to pause"
- [Why did cost per result rise](workflows/cpa-spike.md) — "why did leads get expensive", "CPA went up"
- [Launch a campaign](workflows/launch-campaign.md) — "create a campaign", "promote this offer"
- [Refresh creatives](workflows/creative-refresh.md) — "ads are tired", "new texts", "which ads need a new creative"
- [Client report](workflows/client-report.md) — "report for my client", "weekly summary"
- [Tracking check](workflows/tracking-check.md) — "is my pixel working", "conversions look wrong"

## Never

- Never invent numbers: every figure comes from a Variafy call in this conversation.
- Never pause or change what the person did not name, even when it looks right — propose it instead.
- Never paste tokens, passwords or customer personal data into the chat.
