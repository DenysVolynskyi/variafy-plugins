# Client report

For "make a report for my client" or "weekly summary".

1. Period: the one the person names, else last week (Monday to Sunday) in the ad account time zone.
2. `get_insights` by campaign for the period and the one before it; `revenue_report` if payments are sent in.
3. `audit_account` for anything broken: rejected ads, tracking, learning limited.
4. Structure: results against the business profile's goal; what changed against the previous period; what was done
   (`activity_log`); what is next. Numbers with currency and period; no jargon the client would not know.
5. Show it with `show_dashboard`. For a regular email, `schedule_brief` sends one on a schedule.
6. For a file the person sends to the client: `client_report_file` — the agency name and logo at the top, your summary from
   step 4 as `commentary`. Give the person the download link from the result right away: it works for an hour, and Variafy
   keeps no copy. The file opens offline and prints to PDF; next month, make a new one.
