<p align="center"><img src="assets/logo-400.png" width="96" alt="LocalProspects logo"></p>

# LocalProspects MCP Server

Official remote MCP server for [LocalProspects](https://localprospects.ai). Let Claude, ChatGPT, Cursor, Cline or any MCP client find local businesses on live Google Maps data, enriched with owner names, business emails, phone line types (mobile, landline, VoIP) and social profiles, then export the leads.

- **Endpoint:** `https://localprospects.ai/api/mcp` (Streamable HTTP)
- **Auth:** OAuth sign-in, or a LocalProspects API key as a Bearer header
- **Docs:** https://localprospects.ai/docs
- **MCP Registry:** `ai.localprospects/mcp`

Nothing runs locally. This repo holds the setup docs and registry listing.

## What it can do

- Search any niche in any city ("dentists in Denver") and get every matching business from Google Maps
- Every lead enriched at no extra cost: owner name, ranked emails, phone line type with carrier, Facebook, Instagram, LinkedIn, YouTube, Yelp and TikTok
- Run campaigns across many cities or a whole state, then pause, resume or export them
- Enrich a list of domains you already have
- Export leads to CSV

## Tools

| Tool | What it does |
|------|--------------|
| `check_credits` | See your credit balance (free) |
| `find_location`, `search_businesses`, `search_status`, `get_results` | Run a niche + city search and read the leads |
| `enrich_domains` | Enrich websites you already have |
| `find_campaign_locations`, `preview_campaign`, `create_campaign`, `start_campaign`, `pause_campaign`, `resume_campaign`, `stop_campaign`, `update_campaign`, `add_search_to_campaign` | Multi-city campaigns |
| `list_campaigns`, `get_campaign`, `get_campaign_leads` | Read campaigns and leads |
| `export_campaign`, `get_export` | Export leads to CSV |

## Setup

### Claude Code
```bash
claude mcp add --transport http localprospects https://localprospects.ai/api/mcp \
  --header "Authorization: Bearer YOUR_LP_API_KEY"
```

### Claude.ai / ChatGPT
Add a custom connector with the URL `https://localprospects.ai/api/mcp` and sign in with your LocalProspects account.

### Cursor, Cline, Windsurf and other clients
```json
{
  "mcpServers": {
    "localprospects": {
      "url": "https://localprospects.ai/api/mcp",
      "headers": { "Authorization": "Bearer YOUR_LP_API_KEY" }
    }
  }
}
```

## Example prompts

- "Find roofers in Tampa with a mobile number and an owner name."
- "Run a campaign for med spas across Texas and export it to CSV."
- "Enrich these 50 domains with owner names and emails."

## Pricing

1 lead = 1 credit. Free plan with 100 leads, paid plans from $39/mo. See [pricing](https://localprospects.ai/#pricing).

## Support

https://localprospects.ai or contact@boldslate.com.
