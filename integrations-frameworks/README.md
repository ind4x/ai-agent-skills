# Integrations, Frameworks & Connectors

Skills for enterprise web frameworks (FastAPI, Typer), GitHub API automation, and external chat bridge integrations (Telegram, Discord, iMessage).

---

## Category Principles & Scope

- Production-grade API patterns: OpenAPI schemas, async route handlers, dependency injection, and Pydantic validation.
- Declarative CLI construction using type hints, rich terminal outputs, and robust argument parsing.
- Multi-channel conversational bridge management with secure authentication and bi-directional message routing.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`add-app-to-server`](./add-app-to-server/SKILL.md) | **add-app-to-server** | This skill should be used when the user asks to "add an app to my MCP server", "add UI to my MCP server", "add a view to my MCP tool", "enrich MCP tools with UI", "add interactive UI to existing server", "add MCP Apps to my server", or needs to add interactive UI capabilities to an existing MCP server that already has tools. Provides guidance for analyzing existing tools and adding MCP Apps UI resources. |
| [`convert-web-app`](./convert-web-app/SKILL.md) | **convert-web-app** | This skill should be used when the user asks to "add MCP App support to my web app", "turn my web app into a hybrid MCP App", "make my web page work as an MCP App too", "wrap my existing UI as an MCP App", "convert iframe embed to MCP App", "turn my SPA into an MCP App", or needs to add MCP App support to an existing web application while keeping it working standalone. Provides guidance for analyzing existing web apps and creating a hybrid web + MCP App with server-side tool and resource registration. |
| [`create-mcp-app`](./create-mcp-app/SKILL.md) | **create-mcp-app** | This skill should be used when the user asks to "create an MCP App", "add a UI to an MCP tool", "build an interactive MCP View", "scaffold an MCP App", or needs guidance on MCP Apps SDK patterns, UI-resource registration, MCP App lifecycle, or host integration. Provides comprehensive guidance for building MCP Apps with interactive UIs. |
| [`discord-access`](./discord-access/SKILL.md) | **access** | Manage Discord channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the Discord channel. |
| [`discord-configure`](./discord-configure/SKILL.md) | **configure** | Set up the Discord channel — save the bot token and review access policy. Use when the user pastes a Discord bot token, asks to configure Discord, asks "how do I set this up" or "who can reach me," or wants to check channel status. |
| [`fastapi`](./fastapi/SKILL.md) | **fastapi** | FastAPI best practices and conventions. Use when working with FastAPI APIs, Pydantic models, dependencies, streaming responses including Server-Sent Events (SSE), and serving frontend apps. Keeps FastAPI code clean and up to date with the latest features and patterns. |
| [`imessage-access`](./imessage-access/SKILL.md) | **access** | Manage iMessage channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the iMessage channel. |
| [`imessage-configure`](./imessage-configure/SKILL.md) | **configure** | Check iMessage channel setup and review access policy. Use when the user asks to configure iMessage, asks "how do I set this up" or "who can reach me," or wants to know why texts aren't reaching the assistant. |
| [`migrate-oai-app`](./migrate-oai-app/SKILL.md) | **migrate-oai-app** | This skill should be used when the user asks to "migrate from OpenAI Apps SDK", "convert OpenAI App to MCP", "port from window.openai", "migrate from skybridge", "convert openai/outputTemplate", or needs guidance on converting OpenAI Apps SDK applications to MCP Apps SDK. Provides step-by-step migration guidance with API mapping tables. |
| [`permissioned-github`](./permissioned-github/SKILL.md) | **permissioned-github** | Guidelines for interacting with GitHub and request permissions from the user when commands fail due to restrictions in the agent environment. |
| [`telegram-access`](./telegram-access/SKILL.md) | **access** | Manage Telegram channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the Telegram channel. |
| [`telegram-configure`](./telegram-configure/SKILL.md) | **configure** | Set up the Telegram channel — save the bot token and review access policy. Use when the user pastes a Telegram bot token, asks to configure Telegram, asks "how do I set this up" or "who can reach me," or wants to check channel status. |
| [`typer`](./typer/SKILL.md) | **typer** | Typer best practices and conventions. Use when working with Typer CLIs. Keeps Typer code clean and up to date with the latest features and patterns, updated with new versions. Write new code or refactor and update old code. |

---

## Detailed Skill Overviews

### [`add-app-to-server`](./add-app-to-server/SKILL.md)

- **Skill Identifier:** `add-app-to-server`
- **Path:** [`integrations-frameworks/add-app-to-server/`](./add-app-to-server/)
- **Operational Summary:**
  This skill should be used when the user asks to "add an app to my MCP server", "add UI to my MCP server", "add a view to my MCP tool", "enrich MCP tools with UI", "add interactive UI to existing server", "add MCP Apps to my server", or needs to add interactive UI capabilities to an existing MCP server that already has tools. Provides guidance for analyzing existing tools and adding MCP Apps UI resources.

### [`convert-web-app`](./convert-web-app/SKILL.md)

- **Skill Identifier:** `convert-web-app`
- **Path:** [`integrations-frameworks/convert-web-app/`](./convert-web-app/)
- **Operational Summary:**
  This skill should be used when the user asks to "add MCP App support to my web app", "turn my web app into a hybrid MCP App", "make my web page work as an MCP App too", "wrap my existing UI as an MCP App", "convert iframe embed to MCP App", "turn my SPA into an MCP App", or needs to add MCP App support to an existing web application while keeping it working standalone. Provides guidance for analyzing existing web apps and creating a hybrid web + MCP App with server-side tool and resource registration.

### [`create-mcp-app`](./create-mcp-app/SKILL.md)

- **Skill Identifier:** `create-mcp-app`
- **Path:** [`integrations-frameworks/create-mcp-app/`](./create-mcp-app/)
- **Operational Summary:**
  This skill should be used when the user asks to "create an MCP App", "add a UI to an MCP tool", "build an interactive MCP View", "scaffold an MCP App", or needs guidance on MCP Apps SDK patterns, UI-resource registration, MCP App lifecycle, or host integration. Provides comprehensive guidance for building MCP Apps with interactive UIs.

### [`discord-access`](./discord-access/SKILL.md)

- **Skill Identifier:** `access`
- **Path:** [`integrations-frameworks/discord-access/`](./discord-access/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Manage Discord channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the Discord channel.

### [`discord-configure`](./discord-configure/SKILL.md)

- **Skill Identifier:** `configure`
- **Path:** [`integrations-frameworks/discord-configure/`](./discord-configure/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Set up the Discord channel — save the bot token and review access policy. Use when the user pastes a Discord bot token, asks to configure Discord, asks "how do I set this up" or "who can reach me," or wants to check channel status.

### [`fastapi`](./fastapi/SKILL.md)

- **Skill Identifier:** `fastapi`
- **Path:** [`integrations-frameworks/fastapi/`](./fastapi/)
- **Operational Summary:**
  FastAPI best practices and conventions. Use when working with FastAPI APIs, Pydantic models, dependencies, streaming responses including Server-Sent Events (SSE), and serving frontend apps. Keeps FastAPI code clean and up to date with the latest features and patterns.

### [`imessage-access`](./imessage-access/SKILL.md)

- **Skill Identifier:** `access`
- **Path:** [`integrations-frameworks/imessage-access/`](./imessage-access/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Manage iMessage channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the iMessage channel.

### [`imessage-configure`](./imessage-configure/SKILL.md)

- **Skill Identifier:** `configure`
- **Path:** [`integrations-frameworks/imessage-configure/`](./imessage-configure/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Check iMessage channel setup and review access policy. Use when the user asks to configure iMessage, asks "how do I set this up" or "who can reach me," or wants to know why texts aren't reaching the assistant.

### [`migrate-oai-app`](./migrate-oai-app/SKILL.md)

- **Skill Identifier:** `migrate-oai-app`
- **Path:** [`integrations-frameworks/migrate-oai-app/`](./migrate-oai-app/)
- **Operational Summary:**
  This skill should be used when the user asks to "migrate from OpenAI Apps SDK", "convert OpenAI App to MCP", "port from window.openai", "migrate from skybridge", "convert openai/outputTemplate", or needs guidance on converting OpenAI Apps SDK applications to MCP Apps SDK. Provides step-by-step migration guidance with API mapping tables.

### [`permissioned-github`](./permissioned-github/SKILL.md)

- **Skill Identifier:** `permissioned-github`
- **Path:** [`integrations-frameworks/permissioned-github/`](./permissioned-github/)
- **Operational Summary:**
  Guidelines for interacting with GitHub and request permissions from the user when commands fail due to restrictions in the agent environment.

### [`telegram-access`](./telegram-access/SKILL.md)

- **Skill Identifier:** `access`
- **Path:** [`integrations-frameworks/telegram-access/`](./telegram-access/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Manage Telegram channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks to pair, approve someone, check who's allowed, or change policy for the Telegram channel.

### [`telegram-configure`](./telegram-configure/SKILL.md)

- **Skill Identifier:** `configure`
- **Path:** [`integrations-frameworks/telegram-configure/`](./telegram-configure/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Set up the Telegram channel — save the bot token and review access policy. Use when the user pastes a Telegram bot token, asks to configure Telegram, asks "how do I set this up" or "who can reach me," or wants to check channel status.

### [`typer`](./typer/SKILL.md)

- **Skill Identifier:** `typer`
- **Path:** [`integrations-frameworks/typer/`](./typer/)
- **Operational Summary:**
  Typer best practices and conventions. Use when working with Typer CLIs. Keeps Typer code clean and up to date with the latest features and patterns, updated with new versions. Write new code or refactor and update old code.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s /home/youssef/skills/integrations-frameworks/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r /home/youssef/skills/integrations-frameworks/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
