# ResonanceMetrics MCP server

A read-only MCP server. Ask for brand reports in the assistant you already use. The Advanced plan includes it.

ResonanceMetrics is a GEO visibility platform that measures and improves how brands appear in ChatGPT, Claude, Gemini, Perplexity and Google AI Overviews: https://www.resonancemetrics.com

This repository holds documentation only. It does not contain server source code.

## What the server returns

Nine read-only tools return:

- the brands you can open
- a brand profile
- visibility by AI engine
- cited domains
- open recommendations
- the activity digest
- when the workspace has product optimization: a product page, its open issues, and the answers that mention it

Only the visibility summary links back to the dashboard. Results are aggregates and capped lists. MCP data tools run when the workspace is on the Advanced plan.

## Connect from Claude

1. In Claude, add a custom connector.
2. Use the server URL below. Sign in with your ResonanceMetrics account and accept the consent screen.
3. The grant can read the workspaces that account can open. MCP data tools run when the workspace is on the Advanced plan.

Server URL:

```
https://www.resonancemetrics.com/api/mcp
```

## Cursor and other clients

Clients other than Claude use a personal token that starts with `rm_`. Create it in Settings → Personal and send it as a Bearer token. The token can read every workspace that account can open. Claude uses sign-in instead of this token.

## Revoke access

In ResonanceMetrics, open Settings → Personal and revoke the grant or the personal token. The next call with that credential is refused. Create a new personal token there if you use a client other than Claude.

## Example prompts

These examples are taken from the MCP guide. Each prompt is listed with the tool it uses.

**Which ResonanceMetrics brands can I open, and which workspaces are on the Advanced plan?**  
`rm_list_brands`

**How visible is this brand across AI engines over the last 30 days? Show the split by engine.**  
`rm_get_visibility_summary`

**Which domains do AI engines cite most for this brand over the last 90 days?**  
`rm_get_sources_summary`

**List the recommendations still open for this brand and summarize them in five lines.**  
`rm_list_recommendations`

**What is still wrong with this product page, and which AI answers mention it?**  
`rm_list_apo_issues`

## Privacy and support

The [privacy policy](https://www.resonancemetrics.com/en/legal/privacy) describes what a tool call reads, what is logged, and how to revoke a grant.

- Product support for the server: contact@resonancemetrics.com
- Privacy requests: privacy@resonancemetrics.com

## Links

- [MCP guide (English)](https://www.resonancemetrics.com/en/mcp)
- [Guide MCP (French)](https://www.resonancemetrics.com/fr/mcp)
- [Advanced plan](https://www.resonancemetrics.com/en/pricing)
