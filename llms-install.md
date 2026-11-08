# Installing the LocalProspects MCP server

This is a remote server. Nothing needs to be installed or built locally.

1. Ask the user for their LocalProspects API key, from their account at https://localprospects.ai (free plan available).
2. Add this entry to the MCP settings file:

```json
{
  "mcpServers": {
    "localprospects": {
      "url": "https://localprospects.ai/api/mcp",
      "headers": { "Authorization": "Bearer <API_KEY>" }
    }
  }
}
```

3. Verify the connection by calling the `check_credits` tool. It is free and returns the account's credit balance.

Searches use the account's credits (1 lead = 1 credit). Confirm large searches with the user first.
