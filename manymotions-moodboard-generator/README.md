# Moodboards by ManyMotions

Turn a creative brief into a moodboard of five distinct visual directions, each rendered as square images by two image models, delivered from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Moodboards by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-moodboard-generator` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-moodboard-generator": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/moodboard-generator/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a moodboard for a seaside cafe in Lisbon: sun-bleached, ceramic tiles, soft blues and sand."
2. "Generate it."
3. "Is the moodboard ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 3-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#moodboard-generator
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
