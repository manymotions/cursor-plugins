# AI Image Generator by ManyMotions

Turn a text prompt into up to four AI images with Nano Banana, Flux, Seedream or Ideogram. Cursor sets up the prompt, ratio, resolution and model, shows the credit cost for free, generates only when you ask, and returns the image links from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Image Generator by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-image-generation` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-image-generation": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare two square images of a ceramic coffee mug on a sunny kitchen table, product photo style."
2. "Generate them."
3. "Check the job and give me the image links."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a 7-day trial for $1 + tax, then cost $29/month + tax (Starter, 4,500 credits), $42/month + tax (Pro, 10,000 credits) or $109/month + tax (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#video-image-maker
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
