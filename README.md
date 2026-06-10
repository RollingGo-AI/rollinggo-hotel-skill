# RollingGo Hotel Skill

This is an open agent skill for AI coding assistants (like Cursor, Claude Code, Windsurf, Copilot, Antigravity) that teaches the agent how to natively use the RollingGo Hotel CLI (`@rollinggo/hotel`) to perform end-to-end hotel searches, price confirmations, and bookings.

## Installation

You can install this skill globally into your preferred AI agent using the [npx skills](https://github.com/vercel-labs/skills) CLI:

```bash
npx skills add https://github.com/RollingGo-AI/hotel-skill
```

If you have multiple agents installed, you can target a specific one (e.g. Cursor):
```bash
npx skills add https://github.com/RollingGo-AI/hotel-skill --agent cursor
```

## What it does

Once installed, your AI Agent will understand how to:
1. Trigger an OAuth 2.1 PKCE login flow via `rgh login`.
2. Convert your natural language requests into strict CLI commands for `rgh search-hotels`.
3. Fetch real-time hotel room pricing via `rgh hotel-detail`.
4. Securely lock the price using `rgh price-confirm`.
5. Guide you through the final order creation via `rgh book` to generate an Alipay payment link.

## Security & Privacy
- **No API Keys**: Uses secure OAuth 2.1 PKCE stored strictly on your local machine.
- **Two-Step Confirmation**: The AI is instructed to NEVER place an order without explicit price confirmation from the user.
- **No Leaked IDs**: Internal variables like `hotelId` and `referenceNo` are kept within the CLI toolchain and are presented cleanly as Markdown cards.

---
Maintained by the RollingGo Team.
