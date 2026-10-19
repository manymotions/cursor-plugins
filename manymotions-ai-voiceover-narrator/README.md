# AI Voiceover by ManyMotions

Turn your text into a spoken voiceover read by a stock AI voice in the delivery style you describe (warm narrator, calm, documentary, bedtime story), delivered as an MP3 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Voiceover by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-ai-voiceover-narrator` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-ai-voiceover-narrator": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/ai-voiceover-narrator/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a voiceover of this text, read by a warm narrator: 'Meet Lumen, the desk lamp that follows the sun through your day.'"
2. "Generate it."
3. "Is the MP3 ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 3-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#ai-voiceover-narrator
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
