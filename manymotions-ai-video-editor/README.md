# AI Video Editor by ManyMotions

Edit your ManyMotions video projects from Cursor: place clips from the project's library on the timeline, remove and reorder them, set transitions, burn in subtitles from SRT or VTT text and export the finished MP4.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Video Editor by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-ai-video-editor` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-ai-video-editor": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/ai-video-editor/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "List my ManyMotions video projects."
2. "In 'Weekend trip', move the last clip to the start and add a fade between every clip."
3. "Export it and give me the MP4 link."

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 3-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/ai/ai-video-editor
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
