# Variafy plugin

[Variafy](https://www.variafy.com) connects AI assistants to ad results, CRM payments and account alerts through MCP.
It reads Meta Ads, Google Ads, Microsoft Advertising, LinkedIn Ads, Google Analytics 4 and Search Console. Meta ad changes
(pauses, budgets, new campaigns and ads) come back as a preview with the effect on spend first and are applied only after
you confirm them; the other platforms are read-only. Payments from Pipedrive, a Google Sheet or an uploaded file are matched
to the ads that brought them, and connected Meta accounts are checked every 15 minutes for account, delivery and spend problems.

This repository packages the Variafy connector as a plugin for Claude Code, Codex, Cursor and Gemini CLI.

The plugin brings two things:

- **The Variafy connector** (`https://www.variafy.com/mcp`). You sign in with your Variafy account the first time it is used.
- **The `variafy-ads` skill**: how to work with Variafy, and seven Meta ads workflows — morning check, wasted spend, why cost per
  result rose, launching a campaign, refreshing creatives, a client report and a tracking check.

## Access

Variafy is a free beta by invitation: $0, 3 connections per platform and 300 counted changes per UTC calendar month per
workspace. Join the waiting list at [variafy.com/waitlist](https://www.variafy.com/waitlist). While Meta app review is in
progress, Meta access also needs a tester invitation that you accept in your Facebook account. Variafy is independent and
not affiliated with Meta.

## Claude Code

```
/plugin marketplace add DenysVolynskyi/variafy-plugins
/plugin install variafy@variafy
```

Then run `/mcp`, choose **variafy** and sign in.

## Codex

```
codex plugin marketplace add DenysVolynskyi/variafy-plugins
```

Then type `/plugins`, open **Variafy** and choose **Install plugin**. Codex asks you to sign in to Variafy.

## Cursor

Issue a token in the Variafy console under **Assistant connection** and add it to `~/.cursor/mcp.json`:

```json
{ "mcpServers": { "variafy": { "url": "https://www.variafy.com/mcp", "headers": { "Authorization": "Bearer sk_live_YOUR_TOKEN" } } } }
```

## Gemini CLI

```
gemini extensions install https://github.com/DenysVolynskyi/variafy-plugins
```

Then run `/mcp auth variafy` and sign in. The extension adds the connector and the `variafy-ads` skill with the same
seven workflows.

## Other assistants

Claude, ChatGPT, Claude Code, Cursor, Grok and Mistral Vibe connect to the same address. Gemini custom apps are available
only to some accounts and regions, and we have not tested that connection ourselves. Steps for each:
[variafy.com/help](https://www.variafy.com/help#connect-assistant).

## Check that it works

Ask the assistant: "Call start_here and show my ad accounts." It answers with the connected ad accounts and your plan.

## Links

- [Help](https://www.variafy.com/help) · [Privacy](https://www.variafy.com/privacy) · [Terms](https://www.variafy.com/terms)
- Support: support@variafy.com

The connector is listed in the official MCP Registry as `com.variafy/variafy`.
