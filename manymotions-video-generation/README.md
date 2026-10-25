# AI Video Generator by ManyMotions

Turn a text prompt into a short AI video clip with Kling, Veo, Seedance or Wan. Cursor sets up the prompt, ratio, length and model, shows the credit cost for free, generates only when you ask, and returns the MP4 link from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Video Generator by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-video-generation` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-video-generation": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 5-second 16:9 video of a paper boat sailing down a rainy street at night."
2. "Generate it."
3. "Check the job and give me the MP4 link."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/ai/text-to-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
