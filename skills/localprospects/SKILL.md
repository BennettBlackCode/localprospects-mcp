---
name: localprospects
description: Find local business leads from live Google Maps data with LocalProspects, enriched with owner names, business emails, phone line types and social profiles, and run multi-city campaigns and CSV exports. Use when the user wants leads, prospects or a list of businesses for a niche and location.
---

# LocalProspects

Uses the LocalProspects MCP server (`https://localprospects.ai/api/mcp`, Bearer API key from the user's LocalProspects account). 1 lead = 1 credit.

## One niche in one city
1. `find_location` to resolve the city.
2. `check_credits`; confirm large searches with the user.
3. `search_businesses` with the niche and location, poll `search_status`, then `get_results`.
4. Filter for what the user asked (for example owner name present, mobile phone) and present the leads.

## Many cities or a whole state
1. `find_campaign_locations`, then `preview_campaign` to show the lead estimate and cost.
2. After the user agrees, `create_campaign` and `start_campaign`. Use `pause_campaign`, `resume_campaign` or `stop_campaign` as needed.
3. `get_campaign_leads` to read results, `export_campaign` + `get_export` for a CSV.

## Enrich existing websites
`enrich_domains` with a list of domains returns owner names, emails, phones and socials.
