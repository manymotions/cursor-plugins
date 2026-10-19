# Explainer Video by ManyMotions

Turn a topic into an animated explainer video of about 30 seconds: four illustrated scenes with motion and a voiceover, no presenter on camera, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Explainer Video by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-animated-explainer-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-animated-explainer-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/animated-explainer-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare an animated explainer of why leaves change color in autumn, for beginners, hand-drawn style."
2. "Generate it."
3. "Is the video ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 3-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#animated-explainer-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
