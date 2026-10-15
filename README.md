# Variafy plugin

[Variafy](https://www.variafy.com) connects Claude, ChatGPT, Codex, Cursor and Gemini CLI to your Meta (Facebook and Instagram) ad accounts. Read
results and payments, find wasted spend, explain why cost per result rose, build paused campaigns and report to clients.
Every change comes back as a preview first and is applied only when you confirm it.

The plugin brings two things:

- **The Variafy connector** (`https://www.variafy.com/mcp`). You sign in with your Variafy account the first time it is used.
- **The `variafy-ads` skill**: how to work with Variafy, and seven workflows — morning check, wasted spend, why cost per
  result rose, launching a campaign, refreshing creatives, a client report and a tracking check.

You need a Variafy account with a Meta ad account connected: [variafy.com](https://www.variafy.com).

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

Then run `/mcp auth variafy` and sign in. The extension adds the connector; the workflows from the skill are on
[variafy.com/help](https://www.variafy.com/help#skills).

## Other assistants

Claude, ChatGPT, Gemini, Copilot, Perplexity and others connect to the same address. Steps for each:
[variafy.com/help](https://www.variafy.com/help#connect-assistant).

## Check that it works

Ask the assistant: "Call start_here and show my ad accounts." It answers with the connected ad accounts and your plan.

## Links

- [Help](https://www.variafy.com/help) · [Privacy](https://www.variafy.com/privacy) · [Terms](https://www.variafy.com/terms)
- Support: support@variafy.com

The connector is listed in the official MCP Registry as `com.variafy/variafy`.
