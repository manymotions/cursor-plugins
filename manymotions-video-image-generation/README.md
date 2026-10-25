# AI Video & Image Maker by ManyMotions

Turn a text prompt into AI images or short AI video clips, with models such as Nano Banana, Flux, Kling, Veo and Seedance. Cursor picks the format, ratio, length and model, shows the credit cost for free, generates only when you ask, and returns the files from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Video & Image Maker by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-video-image-generation` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-video-image-generation": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 9:16 video of a hot air balloon rising over misty hills at sunrise."
2. "Generate it."
3. "Now prepare a matching square image for the thumbnail."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a 7-day trial for $1 + tax, then cost $29/month + tax (Starter, 4,500 credits), $42/month + tax (Pro, 10,000 credits) or $109/month + tax (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#video-image-maker
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
