# Comedy Skits by ManyMotions

Turn a premise into a short AI comedy skit with original characters, deadpan, absurd, parody, observational or slapstick, built to land one joke for TikTok, Reels and Shorts, delivered as an MP4 from your ManyMotions account.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Comedy Skits by ManyMotions**.
3. Click **Install**, then sign in to ManyMotions when Cursor asks.

Or run `/add-plugin manymotions-comedy-skit-video` in chat.

## MCP

```json
{
  "mcpServers": {
    "manymotions-comedy-skit-video": {
      "type": "http",
      "url": "https://manymotions.com/api/grok/comedy-skit-video/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE against ManyMotions. Cursor opens the ManyMotions sign-in when the plugin connects.

## Try it

1. "Prepare a deadpan skit: an office printer that only works when you say please."
2. "Generate it."
3. "Is it ready?"

## Pricing

The plugin is free. Generations use credits from your ManyMotions account. Plans begin with a $1, 7-day trial, then cost $29/month (Starter, 4,500 credits), $42/month (Pro, 10,000 credits) or $109/month (Agency, 30,000 credits). Preparing is free and shows the exact credits before anything is spent.

## Docs and support

- Product page: https://manymotions.com/mcp#comedy-skit-video
- Support: info@manymotions.com, https://manymotions.com/support
- Privacy: https://manymotions.com/privacy
- Terms: https://manymotions.com/terms

## License

MIT
