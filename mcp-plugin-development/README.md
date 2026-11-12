# MCP & Plugin Development

Skills for building, testing, and packaging Model Context Protocol (MCP) servers, plugins, hooks, tools, and agent customization rules.

---

## Category Principles & Scope

- Standardized MCP architecture: JSON-RPC server development, tool definitions, resource schemas, and prompt templates.
- Plugin lifecycle management: configuration schemas, lifecycle hooks, permission manifests, and marketplace integration.
- Extensible agent customization: defining robust custom skills, sidecars, and system instructions.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`agent-customization`](./agent-customization/SKILL.md) | **agent-customization** | **WORKFLOW SKILL** — Create, update, review, fix, or debug VS Code agent customization files (.instructions.md, .prompt.md, .agent.md, SKILL.md, copilot-instructions.md, AGENTS.md). USE FOR: saving coding preferences; troubleshooting why instructions/skills/agents are ignored or not invoked; configuring applyTo patterns; defining tool restrictions; creating custom agent modes or specialized workflows; packaging domain knowledge; fixing YAML frontmatter syntax. DO NOT USE FOR: general coding questions (use default agent); runtime debugging or error diagnosis; MCP server configuration (use MCP docs directly); VS Code extension development. INVOKES: file system tools (read/write customization files), ask-questions tool (interview user for requirements), subagents for codebase exploration. FOR SINGLE OPERATIONS: For quick YAML frontmatter fixes or creating a single file from a known pattern, edit the file directly — no skill needed. |
| [`agent-development`](./agent-development/SKILL.md) | **agent-development** | This skill should be used when the user asks to "create an agent", "add an agent", "write a subagent", "agent frontmatter", "when to use description", "agent examples", "agent tools", "agent colors", "autonomous agent", or needs guidance on agent structure, system prompts, triggering conditions, or agent development best practices for Claude Code plugins. |
| [`agy-customizations`](./agy-customizations/SKILL.md) | **agy-customizations** | Comprehensive guide and reference for the Antigravity Customization System. Use to explain how customizations work, their loading priority, discovery mechanisms, and to guide the creation of skills, rules, plugins, hooks, and MCP servers. |
| [`antigravity_guide`](./antigravity_guide/SKILL.md) | **antigravity-guide** | Provides a comprehensive guide, quick reference, and sitemap for Google Antigravity (AGY), including the Antigravity CLI (agy), Antigravity 2.0, Antigravity IDE, Python SDK, slash commands, keybindings, and customizations (skills, rules, MCP, sidecars). Activate this skill when the user asks questions about how to use, configure, or customize Antigravity, AGY, the agy CLI, the Antigravity IDE, or Antigravity 2.0. |
| [`build-mcp-app`](./build-mcp-app/SKILL.md) | **build-mcp-app** | This skill should be used when the user wants to build an "MCP app", add "interactive UI" or "widgets" to an MCP server, "render components in chat", build "MCP UI resources", make a tool that shows a "form", "picker", "dashboard" or "confirmation dialog" inline in the conversation, or mentions "apps SDK" in the context of MCP. Use AFTER the build-mcp-server skill has settled the deployment model, or when the user already knows they want UI widgets. |
| [`build-mcp-server`](./build-mcp-server/SKILL.md) | **build-mcp-server** | This skill should be used when the user asks to "build an MCP server", "create an MCP", "make an MCP integration", "wrap an API for Claude", "expose tools to Claude", "make an MCP app", or discusses building something with the Model Context Protocol. It is the entry point for MCP server development — it interrogates the user about their use case, determines the right deployment model (remote HTTP, MCPB, local stdio), picks a tool-design pattern, and hands off to specialized skills. |
| [`build-mcpb`](./build-mcpb/SKILL.md) | **build-mcpb** | This skill should be used when the user wants to "package an MCP server", "bundle an MCP", "make an MCPB", "ship a local MCP server", "distribute a local MCP", discusses ".mcpb files", mentions bundling a Node or Python runtime with their MCP server, or needs an MCP server that interacts with the local filesystem, desktop apps, or OS and must be installable without the user having Node/Python set up. |
| [`claude-automation-recommender`](./claude-automation-recommender/SKILL.md) | **claude-automation-recommender** | Analyze a codebase and recommend Claude Code automations (hooks, subagents, skills, plugins, MCP servers). Use when user asks for automation recommendations, wants to optimize their Claude Code setup, mentions improving Claude Code workflows, asks how to first set up Claude Code for a project, or wants to know what Claude Code features they should use. |
| [`claude-md-improver`](./claude-md-improver/SKILL.md) | **claude-md-improver** | Audit and improve CLAUDE.md files in repositories. Use when user asks to check, audit, update, improve, or fix CLAUDE.md files. Scans for all CLAUDE.md files, evaluates quality against templates, outputs quality report, then makes targeted updates. Also use when the user mentions "CLAUDE.md maintenance" or "project memory optimization". |
| [`claude-security`](./claude-security/SKILL.md) | **claude-security** | Claude Security: scan the codebase (the whole repository or a scoped part of it), scan changes (this branch's or a pull request's diff, or one commit), or suggest patches (findings turned into targeted patch files, each verified by a panel of agents, that you apply when you choose). Use when the user asks to scan, audit or check code with Claude Security, to scan their changes with Claude Security, or to fix or patch Claude Security findings. |
| [`command-development`](./command-development/SKILL.md) | **command-development** | This skill should be used when the user asks to "create a slash command", "add a command", "write a custom command", "define command arguments", "use command frontmatter", "organize commands", "create command with file references", "interactive command", "use AskUserQuestion in command", or needs guidance on slash command structure, YAML frontmatter fields, dynamic arguments, bash execution in commands, user interaction patterns, or command development best practices for Claude Code. |
| [`example-command`](./example-command/SKILL.md) | **example-command** | An example user-invoked skill that demonstrates frontmatter options and the skills/<name>/SKILL.md layout |
| [`example-skill`](./example-skill/SKILL.md) | **example-skill** | This skill should be used when the user asks to "demonstrate skills", "show skill format", "create a skill template", or discusses skill development patterns. Provides a reference template for creating Claude Code plugin skills. |
| [`hook-development`](./hook-development/SKILL.md) | **hook-development** | This skill should be used when the user asks to "create a hook", "add a PreToolUse/PostToolUse/Stop hook", "validate tool use", "implement prompt-based hooks", "use ${CLAUDE_PLUGIN_ROOT}", "set up event-driven automation", "block dangerous commands", or mentions hook events (PreToolUse, PostToolUse, Stop, SubagentStop, SessionStart, SessionEnd, UserPromptSubmit, PreCompact, Notification). Provides comprehensive guidance for creating and implementing Claude Code plugin hooks with focus on advanced prompt-based hooks API. |
| [`hookify-writing-rules`](./hookify-writing-rules/SKILL.md) | **writing-hookify-rules** | This skill should be used when the user asks to "create a hookify rule", "write a hook rule", "configure hookify", "add a hookify rule", or needs guidance on hookify rule syntax and patterns. |
| [`mcp-apps-builder`](./mcp-apps-builder/SKILL.md) | **mcp-apps-builder** | Load the official MCP Apps builder skills (create-mcp-app, migrate-oai-app, add-app-to-server, convert-web-app) from github.com/modelcontextprotocol/ext-apps. Use when the user says "build an MCP App", "add a ui:// view to my MCP server", "create an interactive MCP App from scratch", "migrate from OpenAI Apps SDK to MCP", or "turn my web app into a hybrid MCP App". Targets the MCP Apps SDK (SEP-1865 ui:// resources) specifically. Not for regular web frontends, REST APIs, CAO provider adapters, SKILL.md authoring, or plugins. |
| [`mcp-integration`](./mcp-integration/SKILL.md) | **mcp-integration** | This skill should be used when the user asks to "add MCP server", "integrate MCP", "configure MCP in plugin", "use .mcp.json", "set up Model Context Protocol", "connect external service", mentions "${CLAUDE_PLUGIN_ROOT} with MCP", or discusses MCP server types (SSE, stdio, HTTP, WebSocket). Provides comprehensive guidance for integrating Model Context Protocol servers into Claude Code plugins for external tool and service integration. |
| [`migrate-agent-settings`](./migrate-agent-settings/SKILL.md) | **migrate-agent-settings** | Migrates the user's MCP servers, skills, slash commands, subagents, and instruction files from other coding agents (Claude Code, Codex, Cursor, Gemini CLI) into one new Antigravity plugin. Use when the user wants to bring over, import, or migrate their setup or config from another agent or tool. Don't use for installing Marketplace plugins or authoring a new plugin from scratch (use the plugin skill). |
| [`migrate-customizations`](./migrate-customizations/SKILL.md) | **migrate-customizations** | Guide a safe, reversible migration of VS Code agent customizations when launched from the Agent Customizations Migrations page with VS Code-generated migration context. |
| [`plugin`](./plugin/SKILL.md) | **plugin** | How to manage and create plugins — namespaced bundles of skills, agents, rules, MCP servers and hooks that install, enable and disable as a single unit. Use this skill when the user wants to enable, disable, install or uninstall a plugin, when they want to create a new plugin, or when a new customization should be packaged into a plugin rather than left loose. Also triggered by the /plugin slash command. Don't use for the underlying customization system itself — discovery roots, loading priority, or authoring a standalone skill, agent, rule, hook or MCP server outside a plugin; see the customizations guide skill for those. |
| [`plugin-settings`](./plugin-settings/SKILL.md) | **plugin-settings** | This skill should be used when the user asks about "plugin settings", "store plugin configuration", "user-configurable plugin", ".local.md files", "plugin state files", "read YAML frontmatter", "per-project plugin settings", or wants to make plugin behavior configurable. Documents the .claude/plugin-name.local.md pattern for storing plugin-specific configuration with YAML frontmatter and markdown content. |
| [`plugin-structure`](./plugin-structure/SKILL.md) | **plugin-structure** | This skill should be used when the user asks to "create a plugin", "scaffold a plugin", "understand plugin structure", "organize plugin components", "set up plugin.json", "use ${CLAUDE_PLUGIN_ROOT}", "add commands/agents/skills/hooks", "configure auto-discovery", or needs guidance on plugin directory layout, manifest configuration, component organization, file naming conventions, or Claude Code plugin architecture best practices. |
| [`skill-creator`](./skill-creator/SKILL.md) | **skill-creator** | Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to create a skill from scratch, edit, or optimize an existing skill, run evals to test a skill, benchmark skill performance with variance analysis, or optimize a skill's description for better triggering accuracy. |
| [`skill-development`](./skill-development/SKILL.md) | **skill-development** | This skill should be used when the user wants to "create a skill", "add a skill to plugin", "write a new skill", "improve skill description", "organize skill content", or needs guidance on skill structure, progressive disclosure, or skill development best practices for Claude Code plugins. |
| [`ui-plugin-navigation`](./ui-plugin-navigation/SKILL.md) | **ui-plugin-navigation** | Discover UI plugin panels relevant to the current task and surface a one-click pill in chat to open (toggle) them in the side pane. Use when a running UI plugin's panel would help with what the user is doing, or right after the user enables a new UI plugin pane and a shortcut to open it is handy. |

---

## Detailed Skill Overviews

### [`agent-customization`](./agent-customization/SKILL.md)

- **Skill Identifier:** `agent-customization`
- **Path:** [`mcp-plugin-development/agent-customization/`](./agent-customization/)
- **Operational Summary:**
  **WORKFLOW SKILL** — Create, update, review, fix, or debug VS Code agent customization files (.instructions.md, .prompt.md, .agent.md, SKILL.md, copilot-instructions.md, AGENTS.md). USE FOR: saving coding preferences; troubleshooting why instructions/skills/agents are ignored or not invoked; configuring applyTo patterns; defining tool restrictions; creating custom agent modes or specialized workflows; packaging domain knowledge; fixing YAML frontmatter syntax. DO NOT USE FOR: general coding questions (use default agent); runtime debugging or error diagnosis; MCP server configuration (use MCP docs directly); VS Code extension development. INVOKES: file system tools (read/write customization files), ask-questions tool (interview user for requirements), subagents for codebase exploration. FOR SINGLE OPERATIONS: For quick YAML frontmatter fixes or creating a single file from a known pattern, edit the file directly — no skill needed.

### [`agent-development`](./agent-development/SKILL.md)

- **Skill Identifier:** `agent-development`
- **Path:** [`mcp-plugin-development/agent-development/`](./agent-development/)
- **Operational Summary:**
  This skill should be used when the user asks to "create an agent", "add an agent", "write a subagent", "agent frontmatter", "when to use description", "agent examples", "agent tools", "agent colors", "autonomous agent", or needs guidance on agent structure, system prompts, triggering conditions, or agent development best practices for Claude Code plugins.

### [`agy-customizations`](./agy-customizations/SKILL.md)

- **Skill Identifier:** `agy-customizations`
- **Path:** [`mcp-plugin-development/agy-customizations/`](./agy-customizations/)
- **Operational Summary:**
  Comprehensive guide and reference for the Antigravity Customization System. Use to explain how customizations work, their loading priority, discovery mechanisms, and to guide the creation of skills, rules, plugins, hooks, and MCP servers.

### [`antigravity_guide`](./antigravity_guide/SKILL.md)

- **Skill Identifier:** `antigravity-guide`
- **Path:** [`mcp-plugin-development/antigravity_guide/`](./antigravity_guide/)
- **Operational Summary:**
  Provides a comprehensive guide, quick reference, and sitemap for Google Antigravity (AGY), including the Antigravity CLI (agy), Antigravity 2.0, Antigravity IDE, Python SDK, slash commands, keybindings, and customizations (skills, rules, MCP, sidecars). Activate this skill when the user asks questions about how to use, configure, or customize Antigravity, AGY, the agy CLI, the Antigravity IDE, or Antigravity 2.0.

### [`build-mcp-app`](./build-mcp-app/SKILL.md)

- **Skill Identifier:** `build-mcp-app`
- **Path:** [`mcp-plugin-development/build-mcp-app/`](./build-mcp-app/)
- **Operational Summary:**
  This skill should be used when the user wants to build an "MCP app", add "interactive UI" or "widgets" to an MCP server, "render components in chat", build "MCP UI resources", make a tool that shows a "form", "picker", "dashboard" or "confirmation dialog" inline in the conversation, or mentions "apps SDK" in the context of MCP. Use AFTER the build-mcp-server skill has settled the deployment model, or when the user already knows they want UI widgets.

### [`build-mcp-server`](./build-mcp-server/SKILL.md)

- **Skill Identifier:** `build-mcp-server`
- **Path:** [`mcp-plugin-development/build-mcp-server/`](./build-mcp-server/)
- **Operational Summary:**
  This skill should be used when the user asks to "build an MCP server", "create an MCP", "make an MCP integration", "wrap an API for Claude", "expose tools to Claude", "make an MCP app", or discusses building something with the Model Context Protocol. It is the entry point for MCP server development — it interrogates the user about their use case, determines the right deployment model (remote HTTP, MCPB, local stdio), picks a tool-design pattern, and hands off to specialized skills.

### [`build-mcpb`](./build-mcpb/SKILL.md)

- **Skill Identifier:** `build-mcpb`
- **Path:** [`mcp-plugin-development/build-mcpb/`](./build-mcpb/)
- **Operational Summary:**
  This skill should be used when the user wants to "package an MCP server", "bundle an MCP", "make an MCPB", "ship a local MCP server", "distribute a local MCP", discusses ".mcpb files", mentions bundling a Node or Python runtime with their MCP server, or needs an MCP server that interacts with the local filesystem, desktop apps, or OS and must be installable without the user having Node/Python set up.

### [`claude-automation-recommender`](./claude-automation-recommender/SKILL.md)

- **Skill Identifier:** `claude-automation-recommender`
- **Path:** [`mcp-plugin-development/claude-automation-recommender/`](./claude-automation-recommender/)
- **Operational Summary:**
  Analyze a codebase and recommend Claude Code automations (hooks, subagents, skills, plugins, MCP servers). Use when user asks for automation recommendations, wants to optimize their Claude Code setup, mentions improving Claude Code workflows, asks how to first set up Claude Code for a project, or wants to know what Claude Code features they should use.

### [`claude-md-improver`](./claude-md-improver/SKILL.md)

- **Skill Identifier:** `claude-md-improver`
- **Path:** [`mcp-plugin-development/claude-md-improver/`](./claude-md-improver/)
- **Operational Summary:**
  Audit and improve CLAUDE.md files in repositories. Use when user asks to check, audit, update, improve, or fix CLAUDE.md files. Scans for all CLAUDE.md files, evaluates quality against templates, outputs quality report, then makes targeted updates. Also use when the user mentions "CLAUDE.md maintenance" or "project memory optimization".

### [`claude-security`](./claude-security/SKILL.md)

- **Skill Identifier:** `claude-security`
- **Path:** [`mcp-plugin-development/claude-security/`](./claude-security/)
- **Allowed Tools:** `- Read`
- **Operational Summary:**
  Claude Security: scan the codebase (the whole repository or a scoped part of it), scan changes (this branch's or a pull request's diff, or one commit), or suggest patches (findings turned into targeted patch files, each verified by a panel of agents, that you apply when you choose). Use when the user asks to scan, audit or check code with Claude Security, to scan their changes with Claude Security, or to fix or patch Claude Security findings.

### [`command-development`](./command-development/SKILL.md)

- **Skill Identifier:** `command-development`
- **Path:** [`mcp-plugin-development/command-development/`](./command-development/)
- **Operational Summary:**
  This skill should be used when the user asks to "create a slash command", "add a command", "write a custom command", "define command arguments", "use command frontmatter", "organize commands", "create command with file references", "interactive command", "use AskUserQuestion in command", or needs guidance on slash command structure, YAML frontmatter fields, dynamic arguments, bash execution in commands, user interaction patterns, or command development best practices for Claude Code.

### [`example-command`](./example-command/SKILL.md)

- **Skill Identifier:** `example-command`
- **Path:** [`mcp-plugin-development/example-command/`](./example-command/)
- **Allowed Tools:** `[Read, Glob, Grep, Bash]`
- **Operational Summary:**
  An example user-invoked skill that demonstrates frontmatter options and the skills/<name>/SKILL.md layout

### [`example-skill`](./example-skill/SKILL.md)

- **Skill Identifier:** `example-skill`
- **Path:** [`mcp-plugin-development/example-skill/`](./example-skill/)
- **Operational Summary:**
  This skill should be used when the user asks to "demonstrate skills", "show skill format", "create a skill template", or discusses skill development patterns. Provides a reference template for creating Claude Code plugin skills.

### [`hook-development`](./hook-development/SKILL.md)

- **Skill Identifier:** `hook-development`
- **Path:** [`mcp-plugin-development/hook-development/`](./hook-development/)
- **Operational Summary:**
  This skill should be used when the user asks to "create a hook", "add a PreToolUse/PostToolUse/Stop hook", "validate tool use", "implement prompt-based hooks", "use ${CLAUDE_PLUGIN_ROOT}", "set up event-driven automation", "block dangerous commands", or mentions hook events (PreToolUse, PostToolUse, Stop, SubagentStop, SessionStart, SessionEnd, UserPromptSubmit, PreCompact, Notification). Provides comprehensive guidance for creating and implementing Claude Code plugin hooks with focus on advanced prompt-based hooks API.

### [`hookify-writing-rules`](./hookify-writing-rules/SKILL.md)

- **Skill Identifier:** `writing-hookify-rules`
- **Path:** [`mcp-plugin-development/hookify-writing-rules/`](./hookify-writing-rules/)
- **Operational Summary:**
  This skill should be used when the user asks to "create a hookify rule", "write a hook rule", "configure hookify", "add a hookify rule", or needs guidance on hookify rule syntax and patterns.

### [`mcp-apps-builder`](./mcp-apps-builder/SKILL.md)

- **Skill Identifier:** `mcp-apps-builder`
- **Path:** [`mcp-plugin-development/mcp-apps-builder/`](./mcp-apps-builder/)
- **Operational Summary:**
  Load the official MCP Apps builder skills (create-mcp-app, migrate-oai-app, add-app-to-server, convert-web-app) from github.com/modelcontextprotocol/ext-apps. Use when the user says "build an MCP App", "add a ui:// view to my MCP server", "create an interactive MCP App from scratch", "migrate from OpenAI Apps SDK to MCP", or "turn my web app into a hybrid MCP App". Targets the MCP Apps SDK (SEP-1865 ui:// resources) specifically. Not for regular web frontends, REST APIs, CAO provider adapters, SKILL.md authoring, or plugins.

### [`mcp-integration`](./mcp-integration/SKILL.md)

- **Skill Identifier:** `mcp-integration`
- **Path:** [`mcp-plugin-development/mcp-integration/`](./mcp-integration/)
- **Operational Summary:**
  This skill should be used when the user asks to "add MCP server", "integrate MCP", "configure MCP in plugin", "use .mcp.json", "set up Model Context Protocol", "connect external service", mentions "${CLAUDE_PLUGIN_ROOT} with MCP", or discusses MCP server types (SSE, stdio, HTTP, WebSocket). Provides comprehensive guidance for integrating Model Context Protocol servers into Claude Code plugins for external tool and service integration.

### [`migrate-agent-settings`](./migrate-agent-settings/SKILL.md)

- **Skill Identifier:** `migrate-agent-settings`
- **Path:** [`mcp-plugin-development/migrate-agent-settings/`](./migrate-agent-settings/)
- **Operational Summary:**
  Migrates the user's MCP servers, skills, slash commands, subagents, and instruction files from other coding agents (Claude Code, Codex, Cursor, Gemini CLI) into one new Antigravity plugin. Use when the user wants to bring over, import, or migrate their setup or config from another agent or tool. Don't use for installing Marketplace plugins or authoring a new plugin from scratch (use the plugin skill).

### [`migrate-customizations`](./migrate-customizations/SKILL.md)

- **Skill Identifier:** `migrate-customizations`
- **Path:** [`mcp-plugin-development/migrate-customizations/`](./migrate-customizations/)
- **Operational Summary:**
  Guide a safe, reversible migration of VS Code agent customizations when launched from the Agent Customizations Migrations page with VS Code-generated migration context.

### [`plugin`](./plugin/SKILL.md)

- **Skill Identifier:** `plugin`
- **Path:** [`mcp-plugin-development/plugin/`](./plugin/)
- **Operational Summary:**
  How to manage and create plugins — namespaced bundles of skills, agents, rules, MCP servers and hooks that install, enable and disable as a single unit. Use this skill when the user wants to enable, disable, install or uninstall a plugin, when they want to create a new plugin, or when a new customization should be packaged into a plugin rather than left loose. Also triggered by the /plugin slash command. Don't use for the underlying customization system itself — discovery roots, loading priority, or authoring a standalone skill, agent, rule, hook or MCP server outside a plugin; see the customizations guide skill for those.

### [`plugin-settings`](./plugin-settings/SKILL.md)

- **Skill Identifier:** `plugin-settings`
- **Path:** [`mcp-plugin-development/plugin-settings/`](./plugin-settings/)
- **Operational Summary:**
  This skill should be used when the user asks about "plugin settings", "store plugin configuration", "user-configurable plugin", ".local.md files", "plugin state files", "read YAML frontmatter", "per-project plugin settings", or wants to make plugin behavior configurable. Documents the .claude/plugin-name.local.md pattern for storing plugin-specific configuration with YAML frontmatter and markdown content.

### [`plugin-structure`](./plugin-structure/SKILL.md)

- **Skill Identifier:** `plugin-structure`
- **Path:** [`mcp-plugin-development/plugin-structure/`](./plugin-structure/)
- **Operational Summary:**
  This skill should be used when the user asks to "create a plugin", "scaffold a plugin", "understand plugin structure", "organize plugin components", "set up plugin.json", "use ${CLAUDE_PLUGIN_ROOT}", "add commands/agents/skills/hooks", "configure auto-discovery", or needs guidance on plugin directory layout, manifest configuration, component organization, file naming conventions, or Claude Code plugin architecture best practices.

### [`skill-creator`](./skill-creator/SKILL.md)

- **Skill Identifier:** `skill-creator`
- **Path:** [`mcp-plugin-development/skill-creator/`](./skill-creator/)
- **Operational Summary:**
  Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to create a skill from scratch, edit, or optimize an existing skill, run evals to test a skill, benchmark skill performance with variance analysis, or optimize a skill's description for better triggering accuracy.

### [`skill-development`](./skill-development/SKILL.md)

- **Skill Identifier:** `skill-development`
- **Path:** [`mcp-plugin-development/skill-development/`](./skill-development/)
- **Operational Summary:**
  This skill should be used when the user wants to "create a skill", "add a skill to plugin", "write a new skill", "improve skill description", "organize skill content", or needs guidance on skill structure, progressive disclosure, or skill development best practices for Claude Code plugins.

### [`ui-plugin-navigation`](./ui-plugin-navigation/SKILL.md)

- **Skill Identifier:** `ui-plugin-navigation`
- **Path:** [`mcp-plugin-development/ui-plugin-navigation/`](./ui-plugin-navigation/)
- **Operational Summary:**
  Discover UI plugin panels relevant to the current task and surface a one-click pill in chat to open (toggle) them in the side pane. Use when a running UI plugin's panel would help with what the user is doing, or right after the user enables a new UI plugin pane and a shortcut to open it is handy.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s /home/youssef/skills/mcp-plugin-development/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r /home/youssef/skills/mcp-plugin-development/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
