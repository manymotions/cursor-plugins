# Cinematic Video by ManyMotions

Describe a scene, pick one of 61 named camera moves (dolly, crane, orbit, crash zoom, dolly zoom, FPV drone, bullet time) plus shot, lighting and look, and render a cinematic text-to-video shot with Veo, Kling, Seedance or Wan in your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Cinematic Video by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-cinematic-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-cinematic-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/cinematic-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a cinematic shot of waves breaking on black sand at dusk, slow dolly-in, golden hour backlight."
2. "Generate it."
3. "Check the job and give me the video link."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#cinematic-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
