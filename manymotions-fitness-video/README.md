# Fitness Videos by ManyMotions

Turn an exercise, routine or training goal into a workout short with an AI athlete training in a gym, outdoors or at home and a short narration, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Fitness Videos by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-fitness-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-fitness-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/fitness-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 15-second kettlebell finisher video in a gym, with cues on keeping the back straight."
2. "Generate it."
3. "How is the video coming along?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a 7-day trial for $1 + tax, then cost $29/month + tax (Starter, 4,500 credits), $42/month + tax (Pro, 10,000 credits) or $109/month + tax (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#fitness-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
