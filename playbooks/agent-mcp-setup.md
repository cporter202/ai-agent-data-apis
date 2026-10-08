# Playbook: Agent + MCP Setup

Let your AI agent call web scrapers as tools — no integration code. Apify's MCP server exposes actors as tools that MCP-compatible agents (Claude, Codex, Cursor, and others) can discover and invoke directly.

## What you get

An agent that can browse the live web: scrape pages, pull datasets, and run actors — all by calling tools in natural language.

## Step 1 — Pick your actors

From the [catalog](../catalog/README.md):

- **MCP servers** (170) — start here; these are built for agent consumption
- **Live web data for agents** (496) — browser actors for any page
- **LLM & chatbot actors** (120) — language utilities your agent can chain

## Step 2 — Connect the MCP server

In your MCP-compatible client (Claude Code, Codex, Cursor), add the Apify MCP server with your Apify API token. The server lists available actors as tools — your agent sees names, descriptions, and input schemas automatically.

Get your free token at [apify.com](https://apify.com?fpr=p2hrc6) → Settings → Integrations.

## Step 3 — Let the agent discover tools

Ask the agent what it can do: "What web scraping tools do you have?" It will list the actors available through MCP. Then give it a job in plain language:

- "Find me the 20 highest-rated plumbers in Erie PA with phone numbers"
- "Monitor this product page and tell me when the price drops below $50"
- "Summarize the top 10 posts on this subreddit from today"

The agent picks the right actor, fills the inputs, runs it, and works with the JSON results.

## Step 4 — Set budget guards

Agents can run actors enthusiastically. Set `maxTotalChargeUsd` on actor inputs or account-level spend limits in the Apify Console so a curious agent doesn't burn your budget.

## Why this beats custom tool code

Before MCP, every web tool your agent needed was a custom integration: auth, parsing, retries, proxies. Now the actor authors maintain all of that. Your agent gets hundreds of maintained tools; you maintain zero.

**[→ Get your free Apify token](https://apify.com?fpr=p2hrc6)**
