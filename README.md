# Jarvis

AI-powered Telegram assistant for research and decision-making. Evaluate GitHub repos as businesses, explore market opportunities, and prep for job applications — all from a single chat.

## Commands

| Command | Description |
|---------|-------------|
| `/review owner/repo` | Business analysis of a GitHub repo (competitors, pricing, market opportunity) |
| `/trend topic` | Niche market analysis with trends, gaps, and monetization ideas |
| `/jobprep <JD>` | Analyze a job description against your stored profile |
| `/updateprofile <update>` | Update your career profile via natural language |
| `/ping` | Health check |

You can also just send a message naturally — Jarvis detects intent and routes to the right command.

## Tech Stack

- **Runtime**: [Bun](https://bun.sh)
- **Bot Framework**: [grammY](https://grammy.dev)
- **AI**: [Claude API](https://docs.anthropic.com/en/docs/intro-to-claude) (Anthropic)
- **Search**: [Brave Search API](https://brave.com/search/api/)
- **Language**: TypeScript

## Setup

1. Clone the repo
2. Install dependencies:
   ```bash
   bun install
   ```
3. Copy `.env.example` to `.env` and fill in your keys:
   ```
   TELEGRAM_BOT_TOKEN=
   ANTHROPIC_API_KEY=
   BRAVE_API_KEY=
   GITHUB_TOKEN=
   ```
4. Run:
   ```bash
   bun start
   ```

## Project Structure

```
src/
├── bot.ts              # Bot entry point & command registration
├── config.ts           # Environment config
├── commands/
│   ├── chat.ts         # Smart intent router
│   ├── review.ts       # GitHub repo analysis
│   ├── trend.ts        # Market trend analysis
│   ├── jobprep.ts      # Job description analysis
│   └── updateprofile.ts # Profile management
├── prompts/
│   ├── review.ts       # Review system prompt
│   ├── trend.ts        # Trend system prompt
│   └── jobprep.ts      # Job prep system prompt
├── services/
│   ├── claude.ts       # Claude API wrapper
│   ├── brave.ts        # Brave Search integration
│   └── github.ts       # GitHub API integration
└── data/
    └── profile.json    # Stored user profile
```
