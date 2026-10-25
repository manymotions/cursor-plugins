# AI UGC Video Ads by ManyMotions

Turn a product brief into a short UGC-style video ad for TikTok, Reels and Shorts, with an AI presenter and voice, script and final cut. Cursor prepares the plan and the credit cost for free, produces the ad only when you ask, and returns the MP4 link from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI UGC Video Ads by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-ugc-video-ads` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-ugc-video-ads": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/ugc/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 15-second UGC ad for a reusable glass water bottle that keeps drinks cold for 24 hours, for active women 25-40."
2. "Generate it."
3. "How is the ad coming along?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#ugc-video-ads
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
