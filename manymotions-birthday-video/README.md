# Birthday Videos by ManyMotions

Turn the memories you describe into a personal birthday, anniversary or milestone tribute video with voice-over and a closing wish spoken to camera, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Birthday Videos by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-birthday-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-birthday-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/birthday-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a birthday video for my grandmother Rosa, turning 80: she grows tomatoes and always sings while cooking. From Marco and the kids."
2. "Generate it."
3. "Is the video ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a 7-day trial for $1 + tax, then cost $29/month + tax (Starter, 4,500 credits), $42/month + tax (Pro, 10,000 credits) or $109/month + tax (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#birthday-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
