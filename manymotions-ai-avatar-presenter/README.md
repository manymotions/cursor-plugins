# AI Avatar Video by ManyMotions

Turn a topic into an explainer, lesson or self-introduction video spoken to camera by an AI presenter with an AI voice, scripted scene by scene and delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **AI Avatar Video by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-ai-avatar-presenter` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-ai-avatar-presenter": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/ai-avatar-presenter/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a 30-second explainer on how compound interest works, for high-school students, presented by a friendly teacher."
2. "Generate it."
3. "How is the video coming along?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#ai-avatar-presenter
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
