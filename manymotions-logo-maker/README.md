# AI Logo Maker by ManyMotions

Describe your brand and get up to four AI logo concepts as PNG images. Cursor writes the logo brief, shows the credit cost for free, generates only when you ask, and returns the logo links from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Logo Maker by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-logo-maker` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-logo-maker": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/logomaker/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare logo concepts for "Fernwood Coffee", a small-batch roastery: warm, hand-crafted, green and cream."
2. "Generate them."
3. "Check the job and give me the logo links."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#logo-maker
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
