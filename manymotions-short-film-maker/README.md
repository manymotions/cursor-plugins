# Short Films by ManyMotions

Turn a logline into a narrative AI short film with characters, dialogue and a film look across several scenes, in drama, sci-fi, thriller, romance, mystery or fantasy, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Short Films by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-short-film-maker` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-short-film-maker": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/short-film-maker/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 30-second sci-fi short: a lighthouse keeper on Mars receives a signal from Earth that should not exist."
2. "Generate it."
3. "How is the film coming along?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#short-film-maker
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
