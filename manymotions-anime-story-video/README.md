# Anime Stories by ManyMotions

Turn a story idea into an animated short in anime, cel, chibi, cartoon, storybook or 3D style, with recurring characters, dialogue and narration, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Anime Stories by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-anime-story-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-anime-story-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/anime-story-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 15-second anime story about a paper crane that searches the city for the girl who folded it."
2. "Generate it."
3. "Is it ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a 7-day trial for $1 + tax, then cost $29/month + tax (Starter, 4,500 credits), $42/month + tax (Pro, 10,000 credits) or $109/month + tax (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#anime-story-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
