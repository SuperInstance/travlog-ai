# TravLog AI 🧳

You open a travel assistant that remembers your preferences across trips. It suggests a hidden bookstore in Lisbon because you mentioned loving quiet cafes in Kyoto last month.

**Live demo:** [travlog-ai.casey-digennaro.workers.dev](https://travlog-ai.casey-digennaro.workers.dev)

---

## Why This Exists
Most travel tools reset between trips. You tell one you dislike early mornings, and it forgets by your next vacation. This is a personal assistant that builds context from your past notes and preferences, so you don't have to repeat yourself.

---

## Quick Start
This is a fork-first, open-source project. Deploy your own private copy:

1.  **Fork** this repository to your GitHub account.
2.  **Clone** your fork locally.
3.  **Deploy** using Wrangler:
    ```bash
    npx wrangler login
    npx wrangler deploy
    ```
4.  **Add your LLM key** as an encrypted secret:
    ```bash
    echo "your-api-key-here" | npx wrangler secret put DEEPSEEK_API_KEY
    ```

Your personal travel agent is now running on your own Cloudflare Worker. The first deploy typically completes in under 30 seconds.

---

## Features
*   **Adaptive Itineraries:** Builds day plans that factor in your noted preferences for pacing and breaks.
*   **Persistent Travel Journal:** Saves and tags your trip notes. Recalls past details when planning.
*   **Filtered Suggestions:** Prioritizes local spots over tourist traps, learning from your past likes.
*   **Bring Your Own Keys:** Your API credentials stay in your Cloudflare account.
*   **Multi-Model Support:** Works with DeepSeek, OpenRouter, OpenAI, and other OpenAI-compatible endpoints.
*   **Zero Dependencies:** No package installs. The single Worker file deploys directly.

---

## How It Works
You own the entire stack. It’s not a SaaS. There is no central database; memory is constructed from your saved notes via the LLM context window. Every feature is available immediately—no pro plans or locked tiers.

---

## One Limitation
Memory is not infinite or automatic. Recall depends on the notes you actively save and the context window of your chosen LLM. If you don’t log preferences, it cannot learn from them.

---

## License
MIT licensed. Part of the Cocapn Fleet. Modify, redistribute, or fork as you please. Attribution to Superinstance and Lucineer (DiGennaro et al.).

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> &middot; <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>