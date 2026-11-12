# Multi-Agent Systems & Orchestration

Skills for coordinating distributed multi-agent teams, CLI Agent Orchestrator (CAO) protocols, shared board swarms, and recursive decomposition.

---

## Category Principles & Scope

- Supervisor-worker governance: strict separation of duties, role routing, and deterministic state transitions.
- Parallel swarm collaboration using shared message boards with passive reactive wakeups.
- Recursive language model decomposition for dense, repository-wide, or multi-hop analytical problems.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`automation`](./automation/SKILL.md) | **automation** | Interactive guide to design and create a scheduled background automation. Use this skill when the user wants to create an automated or recurring scheduled task (e.g. "summarize my emails every morning", "every Monday send me a to-do list"). Also triggered by the /automation slash command. |
| [`cao-agent-routing`](./cao-agent-routing/SKILL.md) | **cao-agent-routing** | Find and select the best installed CAO agent profile for a task before delegating with assign or handoff. Use when a supervisor needs to route coding, documentation, infrastructure, review, research, or other specialist work and the user has not already chosen an agent profile. |
| [`cao-learning`](./cao-learning/SKILL.md) | **cao-learning** | Report task outcomes and distill lessons so the team improves across runs — report_outcome after each unit of work, retrospector handoffs at natural boundaries, and applying injected lessons. Use in workflows that run repeatedly over similar work items. Requires memory.learning_enabled; degrade silently when the tools report disabled. |
| [`cao-mcp-apps`](./cao-mcp-apps/SKILL.md) | **cao-mcp-apps** | Enable, operate, and extend CAO's MCP Apps surface — the host-rendered fleet dashboard visible inside MCP App hosts (Claude Desktop, ChatGPT, VS Code Copilot, Goose, Postman). Use when the user says "enable MCP Apps in CAO", "the ui://cao views aren't rendering", "rebuild MCP Apps bundles", "add a new ui://cao/* view", or "configure the MCP Apps OAuth scope layer". Operates on the CAO_MCP_APPS_ENABLED surface and cao_mcp_apps/ build system. Not for the localhost:9889 browser dashboard, not for plugins, providers, or session management. |
| [`cao-memory`](./cao-memory/SKILL.md) | **cao-memory** | Store, recall, and forget durable facts with CAO memory — user preferences, project conventions, decisions, and corrections that should persist across sessions and agents. Use proactively to check memory before asking the user, and to save anything worth remembering. Distinct from any provider-native memory. |
| [`cao-plugin`](./cao-plugin/SKILL.md) | **cao-plugin** | Create a new CAO (CLI Agent Orchestrator) plugin. Use this skill whenever the user wants to add a plugin that reacts to CAO lifecycle or messaging events, scaffold a plugin package, understand plugin requirements, or integrate an external system (Discord, Slack, dashboards, logging, metrics) with CAO. Also use when the user asks what plugin events are available, how plugin discovery works, or how to install a plugin into a CAO environment. |
| [`cao-provider`](./cao-provider/SKILL.md) | **cao-provider** | Create a new CLI agent provider for CAO (CLI Agent Orchestrator). Use this skill whenever the user wants to add support for a new CLI-based AI agent (e.g., a new coding assistant CLI), integrate a new provider, or scaffold a provider implementation. Also use when the user asks about the provider architecture, what files to modify, or how providers work in CAO. |
| [`cao-session-liveness`](./cao-session-liveness/SKILL.md) | **cao-session-liveness** | Verify whether a CAO session is actually alive and what it really said, before reporting progress or completion to a user. Use alongside cao-session-management whenever you launch, poll, or report on a CAO session — especially when a session appears stalled, a send times out, or a status value looks inconsistent with the output. |
| [`cao-session-management`](./cao-session-management/SKILL.md) | **cao-session-management** | Interact with CAO (CLI Agent Orchestrator) — launch multi-agent sessions, check status, send follow-up instructions, unblock stuck terminals, or shut down sessions. Use when working with CAO sessions in any capacity. |
| [`cao-supervisor-protocols`](./cao-supervisor-protocols/SKILL.md) | **cao-supervisor-protocols** | Supervisor-side orchestration patterns for assign, handoff, and idle inbox delivery in CAO |
| [`cao-worker-protocols`](./cao-worker-protocols/SKILL.md) | **cao-worker-protocols** | Worker-side callback and completion rules for assigned and handed-off tasks in CAO |
| [`cao-workflow`](./cao-workflow/SKILL.md) | **cao-workflow** | Author and run CAO Python workflow scripts — multi-step, parameterized, fan-out orchestrations executed by `cao workflow run`. Use when the user wants a repeatable multi-step job (e.g. data analysis over many files, a review pipeline, a parameterized batch). Authoring ends at a validated script file; running it is a separate, user-approved step. |
| [`migrate-workflows`](./migrate-workflows/SKILL.md) | **migrate-workflows** | Automatically migrate legacy workflows to modern skills across global and workspace configurations. Scans for existing workflows, creates target SKILL.md files, and safely archives old workflow files. |
| [`native_swarm`](./native_swarm/SKILL.md) | **swarm** | (Preview & Quota Heavy) Run a swarm: several agents working in parallel on one task, each in its own conversation, collaborating through a shared message board. Use when the work splits into pieces that can be done at the same time, or when a second pair of eyes should check the first pair's work. |
| [`recursive-decomposition`](./recursive-decomposition/SKILL.md) | **recursive-decomposition** | Decompose dense codebase-wide, multi-document, PDF, and aggregation work even when the input fits the context window, following Recursive Language Models (Zhang, Kraska, Khattab, 2025). Use when the user asks to analyse all files, a whole repo, all docs, large PDFs, or to aggregate or multi-hop across scattered sources. Skip one file, one function, a single needle, or a one-page PDF conversion. Triggers: long context, context rot, large codebase, many files, all files, big document, multi-document, PDF, aggregate, summarize everything, codebase-wide, multi-hop, recursive, sub-agents, map-reduce. |
| [`run-workflow`](./run-workflow/SKILL.md) | **run-workflow** | How to write and run a dynamic workflow script with the `run_workflow` tool: a Python script that orchestrates many agents with `agent`, `parallel`, `pipeline`, and `phase`. Use when a task splits into many independent or staged pieces of agent work (fan out over files, modules, bugs, or review angles, then aggregate), or when the user asks for a workflow. Don't use for a single delegated task (use a subagent) or for legacy workflow files (see migrate-workflows). |
| [`spec`](./spec/SKILL.md) | **spec** | Turn vague intent into a precise, executable spec in five phases. (gstack) |
| [`swarm_monitor`](./swarm_monitor/SKILL.md) | **swarm_monitor** | ONLY for the native-swarm worker whose brief says it is the monitor. On a timer, it checks whether the whole swarm has stalled and calls on the one member who can unstick it. Coordinators and other workers: do not load this. |
| [`swarm_narrator`](./swarm_narrator/SKILL.md) | **swarm_narrator** | ONLY for the native-swarm worker whose brief says it is the narrator. It watches the board and keeps the facts behind the user's Overview (view.json) current. Coordinators and other workers: do not load this. |

---

## Detailed Skill Overviews

### [`automation`](./automation/SKILL.md)

- **Skill Identifier:** `automation`
- **Path:** [`multi-agent-orchestration/automation/`](./automation/)
- **Operational Summary:**
  Interactive guide to design and create a scheduled background automation. Use this skill when the user wants to create an automated or recurring scheduled task (e.g. "summarize my emails every morning", "every Monday send me a to-do list"). Also triggered by the /automation slash command.

### [`cao-agent-routing`](./cao-agent-routing/SKILL.md)

- **Skill Identifier:** `cao-agent-routing`
- **Path:** [`multi-agent-orchestration/cao-agent-routing/`](./cao-agent-routing/)
- **Operational Summary:**
  Find and select the best installed CAO agent profile for a task before delegating with assign or handoff. Use when a supervisor needs to route coding, documentation, infrastructure, review, research, or other specialist work and the user has not already chosen an agent profile.

### [`cao-learning`](./cao-learning/SKILL.md)

- **Skill Identifier:** `cao-learning`
- **Path:** [`multi-agent-orchestration/cao-learning/`](./cao-learning/)
- **Operational Summary:**
  Report task outcomes and distill lessons so the team improves across runs — report_outcome after each unit of work, retrospector handoffs at natural boundaries, and applying injected lessons. Use in workflows that run repeatedly over similar work items. Requires memory.learning_enabled; degrade silently when the tools report disabled.

### [`cao-mcp-apps`](./cao-mcp-apps/SKILL.md)

- **Skill Identifier:** `cao-mcp-apps`
- **Path:** [`multi-agent-orchestration/cao-mcp-apps/`](./cao-mcp-apps/)
- **Operational Summary:**
  Enable, operate, and extend CAO's MCP Apps surface — the host-rendered fleet dashboard visible inside MCP App hosts (Claude Desktop, ChatGPT, VS Code Copilot, Goose, Postman). Use when the user says "enable MCP Apps in CAO", "the ui://cao views aren't rendering", "rebuild MCP Apps bundles", "add a new ui://cao/* view", or "configure the MCP Apps OAuth scope layer". Operates on the CAO_MCP_APPS_ENABLED surface and cao_mcp_apps/ build system. Not for the localhost:9889 browser dashboard, not for plugins, providers, or session management.

### [`cao-memory`](./cao-memory/SKILL.md)

- **Skill Identifier:** `cao-memory`
- **Path:** [`multi-agent-orchestration/cao-memory/`](./cao-memory/)
- **Operational Summary:**
  Store, recall, and forget durable facts with CAO memory — user preferences, project conventions, decisions, and corrections that should persist across sessions and agents. Use proactively to check memory before asking the user, and to save anything worth remembering. Distinct from any provider-native memory.

### [`cao-plugin`](./cao-plugin/SKILL.md)

- **Skill Identifier:** `cao-plugin`
- **Path:** [`multi-agent-orchestration/cao-plugin/`](./cao-plugin/)
- **Operational Summary:**
  Create a new CAO (CLI Agent Orchestrator) plugin. Use this skill whenever the user wants to add a plugin that reacts to CAO lifecycle or messaging events, scaffold a plugin package, understand plugin requirements, or integrate an external system (Discord, Slack, dashboards, logging, metrics) with CAO. Also use when the user asks what plugin events are available, how plugin discovery works, or how to install a plugin into a CAO environment.

### [`cao-provider`](./cao-provider/SKILL.md)

- **Skill Identifier:** `cao-provider`
- **Path:** [`multi-agent-orchestration/cao-provider/`](./cao-provider/)
- **Operational Summary:**
  Create a new CLI agent provider for CAO (CLI Agent Orchestrator). Use this skill whenever the user wants to add support for a new CLI-based AI agent (e.g., a new coding assistant CLI), integrate a new provider, or scaffold a provider implementation. Also use when the user asks about the provider architecture, what files to modify, or how providers work in CAO.

### [`cao-session-liveness`](./cao-session-liveness/SKILL.md)

- **Skill Identifier:** `cao-session-liveness`
- **Path:** [`multi-agent-orchestration/cao-session-liveness/`](./cao-session-liveness/)
- **Operational Summary:**
  Verify whether a CAO session is actually alive and what it really said, before reporting progress or completion to a user. Use alongside cao-session-management whenever you launch, poll, or report on a CAO session — especially when a session appears stalled, a send times out, or a status value looks inconsistent with the output.

### [`cao-session-management`](./cao-session-management/SKILL.md)

- **Skill Identifier:** `cao-session-management`
- **Path:** [`multi-agent-orchestration/cao-session-management/`](./cao-session-management/)
- **Operational Summary:**
  Interact with CAO (CLI Agent Orchestrator) — launch multi-agent sessions, check status, send follow-up instructions, unblock stuck terminals, or shut down sessions. Use when working with CAO sessions in any capacity.

### [`cao-supervisor-protocols`](./cao-supervisor-protocols/SKILL.md)

- **Skill Identifier:** `cao-supervisor-protocols`
- **Path:** [`multi-agent-orchestration/cao-supervisor-protocols/`](./cao-supervisor-protocols/)
- **Operational Summary:**
  Supervisor-side orchestration patterns for assign, handoff, and idle inbox delivery in CAO

### [`cao-worker-protocols`](./cao-worker-protocols/SKILL.md)

- **Skill Identifier:** `cao-worker-protocols`
- **Path:** [`multi-agent-orchestration/cao-worker-protocols/`](./cao-worker-protocols/)
- **Operational Summary:**
  Worker-side callback and completion rules for assigned and handed-off tasks in CAO

### [`cao-workflow`](./cao-workflow/SKILL.md)

- **Skill Identifier:** `cao-workflow`
- **Path:** [`multi-agent-orchestration/cao-workflow/`](./cao-workflow/)
- **Operational Summary:**
  Author and run CAO Python workflow scripts — multi-step, parameterized, fan-out orchestrations executed by `cao workflow run`. Use when the user wants a repeatable multi-step job (e.g. data analysis over many files, a review pipeline, a parameterized batch). Authoring ends at a validated script file; running it is a separate, user-approved step.

### [`migrate-workflows`](./migrate-workflows/SKILL.md)

- **Skill Identifier:** `migrate-workflows`
- **Path:** [`multi-agent-orchestration/migrate-workflows/`](./migrate-workflows/)
- **Operational Summary:**
  Automatically migrate legacy workflows to modern skills across global and workspace configurations. Scans for existing workflows, creates target SKILL.md files, and safely archives old workflow files.

### [`native_swarm`](./native_swarm/SKILL.md)

- **Skill Identifier:** `swarm`
- **Path:** [`multi-agent-orchestration/native_swarm/`](./native_swarm/)
- **Operational Summary:**
  (Preview & Quota Heavy) Run a swarm: several agents working in parallel on one task, each in its own conversation, collaborating through a shared message board. Use when the work splits into pieces that can be done at the same time, or when a second pair of eyes should check the first pair's work.

### [`recursive-decomposition`](./recursive-decomposition/SKILL.md)

- **Skill Identifier:** `recursive-decomposition`
- **Path:** [`multi-agent-orchestration/recursive-decomposition/`](./recursive-decomposition/)
- **Operational Summary:**
  Decompose dense codebase-wide, multi-document, PDF, and aggregation work even when the input fits the context window, following Recursive Language Models (Zhang, Kraska, Khattab, 2025). Use when the user asks to analyse all files, a whole repo, all docs, large PDFs, or to aggregate or multi-hop across scattered sources. Skip one file, one function, a single needle, or a one-page PDF conversion. Triggers: long context, context rot, large codebase, many files, all files, big document, multi-document, PDF, aggregate, summarize everything, codebase-wide, multi-hop, recursive, sub-agents, map-reduce.

### [`run-workflow`](./run-workflow/SKILL.md)

- **Skill Identifier:** `run-workflow`
- **Path:** [`multi-agent-orchestration/run-workflow/`](./run-workflow/)
- **Operational Summary:**
  How to write and run a dynamic workflow script with the `run_workflow` tool: a Python script that orchestrates many agents with `agent`, `parallel`, `pipeline`, and `phase`. Use when a task splits into many independent or staged pieces of agent work (fan out over files, modules, bugs, or review angles, then aggregate), or when the user asks for a workflow. Don't use for a single delegated task (use a subagent) or for legacy workflow files (see migrate-workflows).

### [`spec`](./spec/SKILL.md)

- **Skill Identifier:** `spec`
- **Path:** [`multi-agent-orchestration/spec/`](./spec/)
- **Allowed Tools:** `- Bash`
- **Operational Summary:**
  Turn vague intent into a precise, executable spec in five phases. (gstack)

### [`swarm_monitor`](./swarm_monitor/SKILL.md)

- **Skill Identifier:** `swarm_monitor`
- **Path:** [`multi-agent-orchestration/swarm_monitor/`](./swarm_monitor/)
- **Operational Summary:**
  ONLY for the native-swarm worker whose brief says it is the monitor. On a timer, it checks whether the whole swarm has stalled and calls on the one member who can unstick it. Coordinators and other workers: do not load this.

### [`swarm_narrator`](./swarm_narrator/SKILL.md)

- **Skill Identifier:** `swarm_narrator`
- **Path:** [`multi-agent-orchestration/swarm_narrator/`](./swarm_narrator/)
- **Operational Summary:**
  ONLY for the native-swarm worker whose brief says it is the narrator. It watches the board and keeps the facts behind the user's Overview (view.json) current. Coordinators and other workers: do not load this.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s /home/youssef/skills/multi-agent-orchestration/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r /home/youssef/skills/multi-agent-orchestration/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
