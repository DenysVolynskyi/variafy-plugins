# Morning check

For "how are my ads doing" or "anything to do today".

1. `start_here` already told you whether there is advice for today. If there is, call `get_advice` and lead with it: each
   item names the object, why, and the prepared change.
2. `get_insights {"date_preset":"yesterday","level":"campaign"}` and the same for `last_7d`: spend, results, cost per
   result. Compare yesterday with the 7-day daily average; mention only what moved by more than about 20%.
3. `list_signals`: what the watchdog found and has not seen resolved. Mention open signals in one line each.
4. Show it with `show_dashboard`, then at most three sentences: what is fine, what needs a look, the one thing to do first.
5. Offer the prepared changes (`list_pending_actions`) rather than building new ones.
