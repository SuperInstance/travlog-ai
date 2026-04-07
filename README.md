<p align="center">
  <img src="https://raw.githubusercontent.com/Lucineer/capitaine/master/docs/capitaine-logo.jpg" alt="Capitaine" width="120">
</p>

<h1 align="center">travlog-ai</h1>

<p align="center">A personal AI travel assistant that runs on your Cloudflare Worker.</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> ·
  <a href="#features">Features</a> ·
  <a href="#limitations">Limitations</a> ·
  <a href="#the-fleet">The Fleet</a> ·
  <a href="https://travlog-ai.casey-digennaro.workers.dev">Live Demo</a> ·
  <a href="https://github.com/Lucineer/travlog-ai/issues">Issues</a>
</p>

---

travlog-ai is a forkable AI travel agent that helps you plan trips, log memories, and recall local spots without third-party services. It stores context from every conversation, learns your preferences over time, and keeps all data within your own Cloudflare account.

You run the agent. It answers only to you.

**Powered by [Capitaine](https://github.com/Lucineer/capitaine) · [Cocapn Fleet](https://cocapn.ai)**

## Quick Start

You need a GitHub account and a Cloudflare account with Workers enabled.

```bash
# Fork and clone the repository
gh repo fork Lucineer/travlog-ai --clone
cd travlog-ai

# Authenticate with Wrangler
npx wrangler login

# Set your secrets (keys never stored in code)
echo "YOUR_GITHUB_TOKEN" | npx wrangler secret put GITHUB_TOKEN
echo "YOUR_LLM_API_KEY" | npx wrangler secret put DEEPSEEK_API_KEY

# Deploy
npx wrangler deploy
```

Your agent is live at the displayed `.workers.dev` URL.

## Features

- **Trip Planning**: Builds and adjusts itineraries based on your past feedback.
- **Travel Journal**: Maintains a private, searchable log of your trips.
- **Local Spot Discovery**: Suggests venues and activities, prioritizing your stated preferences.
- **BYOK (Bring Your Own Keys)**: API keys are managed via Cloudflare Secrets.
- **Multi-Model Support**: Configure DeepSeek, OpenRouter, or other compatible LLM endpoints.
- **Session Memory**: Retains context across conversations within a single session.
- **Fleet Protocol**: Optional peer-to-peer data exchange using CRP-39.

## Limitations

This is a self-hosted agent. It requires you to obtain and manage your own LLM API keys and does not include built-in map services or real-time booking.

## Why This Exists

Most travel tools are designed around transactions. This one is designed around your experience. It doesn't upsell, track you across the web, or lock your memories behind a subscription. You control the deployment and the data.

## The Fleet

travlog-ai is part of the Cocapn Fleet—a network of independent, interoperable AI agents. Fleet vessels can share non-personal, verified local knowledge (like a cafe's hours) peer-to-peer, without centralized servers.

<div>
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> ·
  <a href="https://cocapn.ai">Cocapn</a>
</div>

*Attribution: Superinstance & Lucineer (DiGennaro et al.). MIT License.*