# Travel Videos by ManyMotions

Turn a destination or a journey into a narrated travel guide, journey diary or short documentary with generated scenes of the place, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Travel Videos by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-travel-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-travel-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/travel-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 30-second travel guide to Kyoto in autumn for first-time visitors."
2. "Generate it."
3. "Is the video ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 3-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#travel-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
