# Content Genius Skill v2.0

AI-powered content creation and proposal generation system for [ContentGenius](https://app.cgenius.app). Generate blogs, social posts, emails, proposals, presentations, videos, and more — all from your AI coding agent.

This repository holds the `contentgenius` agent skill (in [`skills/contentgenius/`](skills/contentgenius/SKILL.md)). The skill was formerly named `cgenius` (repository `cgenius-skill`). It is maintained by Epsimo AI.

## Installation

```bash
npx skills add epsimoai/contentgenius
```

The `skills` CLI needs Node.js 22.20 or later.

Supported agent tools:

| Agent tool | Command | Project path | Global path (with `-g`) |
| --- | --- | --- | --- |
| Claude Code | `npx skills add epsimoai/contentgenius -a claude-code` | `.claude/skills/contentgenius/` | `~/.claude/skills/contentgenius/` |
| OpenAI Codex CLI | `npx skills add epsimoai/contentgenius -a codex` | `.agents/skills/contentgenius/` | `~/.agents/skills/contentgenius/` |
| Cursor | `npx skills add epsimoai/contentgenius -a cursor` | `.agents/skills/contentgenius/` | `~/.cursor/skills/contentgenius/` |
| Kiro (IDE and CLI) | `npx skills add epsimoai/contentgenius -a kiro-cli` | `.kiro/skills/contentgenius/` | `~/.kiro/skills/contentgenius/` |
| Other tools | `npx skills add epsimoai/contentgenius`, then pick the tool | per tool | per tool |

In the Kiro IDE you can also import the skill from GitHub with the URL `https://github.com/epsimoai/contentgenius/tree/main/skills/contentgenius`. See the [skills CLI agent list](https://github.com/vercel-labs/skills/blob/main/docs/agents.md) for other tools.

## Credentials

| Variable | Status | Where to get it |
| --- | --- | --- |
| `CGENIUS_EPSIMO_TOKEN` | Required | In the ContentGenius app, open https://app.cgenius.app/settings/api-tokens and create or copy your token |
| `CGENIUS_ASSISTANT_ID` | Required | Your ContentGenius AI assistant identifier |
| `CGENIUS_API_BASE_URL` | Optional | Defaults to `https://app.cgenius.app` |
| `CGENIUS_APPSYNC_URL` | Optional | GraphQL endpoint, for publish features |
| `CGENIUS_APPSYNC_API_KEY` | Optional | GraphQL API key, for publish features |

You need a ContentGenius account. Keep tokens out of chats, prompts and commits.

## Sample prompt

> Use ContentGenius to write a medium-length, professional blog post about how AI is changing B2B sales.

## Configuration

```bash
export CGENIUS_API_BASE_URL="https://app.cgenius.app"
export CGENIUS_EPSIMO_TOKEN="your_token"
export CGENIUS_ASSISTANT_ID="your_assistant_id"

# Optional (for GraphQL/publish features)
export CGENIUS_APPSYNC_URL="your_appsync_endpoint"
export CGENIUS_APPSYNC_API_KEY="your_api_key"
```

Get your token from: https://app.cgenius.app/settings/api-tokens

## Available Commands

| Command | Description |
|---------|-------------|
| `/contentgenius blog generate <topic>` | Async blog pipeline (research → outline → write) |
| `/contentgenius blog list\|status\|resume\|regenerate` | Blog lifecycle management |
| `/contentgenius social <message>` | Generate social post |
| `/contentgenius email <topic>` | Generate professional email |
| `/contentgenius proposal <client>` | Generate commercial proposal |
| `/contentgenius proposal-pipeline <client>` | Full 3-stage async pipeline |
| `/contentgenius ideate create\|list\|analyze\|generate` | Content ideation workflow |
| `/contentgenius brand-voice create\|list` | Manage brand voice profiles |
| `/contentgenius offer create\|research <client>` | Automated offer generation |
| `/contentgenius questionnaire create\|list\|status` | Shareable client intake forms |
| `/contentgenius publish schedule\|list` | Content calendar & publishing |
| `/contentgenius pptx <topic>` | PowerPoint generation |
| `/contentgenius video render\|list` | Video rendering via Remotion |
| `/contentgenius document <topic>` | Reports, briefs, memos |
| `/contentgenius analytics seo\|social` | Performance analytics |

## Quick Start

```bash
# Generate a blog post
/contentgenius blog generate "How AI is changing sales" --size medium --tone professional

# Create a social post
/contentgenius social "Announce our new product launch"

# Generate a proposal
/contentgenius proposal "Acme Corp" --services "SEO, Content" --budget "50k"

# Create shareable questionnaire
/contentgenius questionnaire create "Acme Corp" --email "client@acme.com" --expires 14

# Schedule content
/contentgenius publish schedule content-123 --platform blog --date 2026-06-01
```

## Documentation

- [SKILL.md](./skills/contentgenius/SKILL.md) — Full command reference with options and API endpoints
- [examples/](./skills/contentgenius/examples/) — Usage examples

## Links

- **ContentGenius homepage:** https://app.cgenius.app
- **GitHub:** https://github.com/epsimoai/contentgenius
- **skills.sh:** https://skills.sh/epsimoai/contentgenius

## License

MIT, see [LICENSE](./LICENSE).
