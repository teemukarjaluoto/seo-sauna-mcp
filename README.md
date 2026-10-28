# SEO Sauna MCP server

Remote MCP server for [SEO Sauna](https://seosauna.com), an affordable SEO and AI visibility tool. Connect Claude, ChatGPT, Cursor, Codex or any MCP client to live SEO data: keyword research, SERPs, rank tracking, site audits, backlinks, Google Search Console, Google Analytics 4, local SEO and AI visibility in ChatGPT, Gemini and AI Overviews.

```
https://app.seosauna.com/mcp
```

Transport: Streamable HTTP. Auth: OAuth sign-in (or an API key for clients without OAuth).

This repository holds the connection instructions, the registry metadata and the free [Agent Skills](#agent-skills). The server itself is hosted; there is nothing to install or run.

## Connect

**Claude Desktop:** Customize → Connectors → Add → Add custom connector → paste `https://app.seosauna.com/mcp` and approve the SEO Sauna sign-in.

**Claude Code:**

```bash
claude mcp add --transport http --scope user seosauna https://app.seosauna.com/mcp
```

**Codex:**

```bash
codex mcp add seosauna --url https://app.seosauna.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "seosauna": {
      "url": "https://app.seosauna.com/mcp"
    }
  }
}
```

**ChatGPT and other clients:** add a remote MCP server named `seosauna` with the URL above and complete the sign-in. Full guide: [seosauna.com/docs/mcp](https://seosauna.com/docs/mcp).

## What you can ask

- "Find keywords my site can realistically rank for in Finland and group them into pages."
- "Audit example.com and tell me the three fixes that matter most."
- "Which queries in Search Console are stuck on page two?"
- "Does ChatGPT mention our brand when people ask for the best project management tool?"
- "Write this month's client report and save it with our branding."

## Tools

| Area | Tools |
|---|---|
| Projects and context | `list_projects`, `create_project`, `get_project_context`, `update_project_context`, `research_project_website`, `save_project_website_setup` |
| Keyword research | `research_keywords`, `get_keyword_metrics`, `get_domain_keyword_suggestions`, `save_keywords`, `list_saved_keywords`, `remove_saved_keywords` |
| SERPs and competitors | `get_serp_results`, `search_serp_locations`, `find_serp_competitors`, `get_domain_overview`, `get_ranked_keywords` |
| Rank tracking | `create_rank_tracker`, `estimate_rank_tracker_cost`, `run_rank_tracker`, `get_rank_tracker`, `add_rank_tracking_keywords`, `remove_rank_tracking_keywords`, `pin_rank_tracking_keywords` |
| Site audits | `run_site_audit`, `get_audit_status`, `get_audit_issues`, `get_audit_pages`, `list_site_audits`, `delete_site_audit` |
| Backlinks | `get_backlinks_overview`, `get_backlinks_profile` |
| Google Search Console | `get_search_console_performance`, `get_search_opportunities`, `inspect_urls` |
| Google Analytics 4 | organic overview, landing pages, page performance, traffic acquisition, key events, ecommerce, audience, site search, measurement health |
| Local SEO | `search_local_businesses`, `get_business_profile`, `get_business_reviews`, `get_local_serp_results`, `get_local_rank_grid` |
| AI visibility | `generate_ai_visibility_prompts`, `research_ai_visibility_prompts`, `run_ai_visibility_check`, `get_ai_visibility_results`, `get_ai_visibility_trend`, `get_ai_visibility_sources`, `set_ai_visibility_schedule` |
| Reports | `save_report`, `get_report`, `list_reports`, `set_report_sharing`, `save_report_template`, `list_report_templates` |

Reports can carry your agency's logo, name and color, and be shared as a PDF or a link without SEO Sauna branding.

## Agent Skills

The [`skills/`](skills) folder contains 12 free Agent Skills that turn the tools into repeatable workflows: SEO Project Setup, SEO Coach, SEO Audit, Keyword Research, Keyword Clustering, Competitive Landscape, Competitor Analysis, Local SEO, AI Visibility Audit, AI Prompt Research, Link Prospecting and SEO Report.

Install them in Claude Code by copying the folders into `~/.claude/skills/`, or download the bundle: [seo-sauna-skills.zip](https://seosauna.com/skills/seo-sauna-skills.zip). Guide: [seosauna.com/docs/skills](https://seosauna.com/docs/skills).

## Pricing

59 € a month (excl. VAT) with 17,000 credits included. Credits are used only when fetching new data; reading your own Search Console data and saving or sharing reports uses none. New accounts start with 1,000 free credits, no card needed. Details: [seosauna.com](https://seosauna.com).

## Links

- Website: [seosauna.com](https://seosauna.com) · [in Finnish](https://seosauna.com/fi)
- Docs: [seosauna.com/docs](https://seosauna.com/docs)
- Built on [OpenSEO](https://github.com/every-app/open-seo) (MIT)

## License

MIT. See [LICENSE](LICENSE).
