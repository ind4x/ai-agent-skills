# Knowledge Analysis & Reverse Engineering

Skills for deep codebase knowledge graph generation, binary/web reverse engineering, and lifecycle artifact reporting.

---

## Category Principles & Scope

- Knowledge graph extraction: AST parsing, god node discovery, community clustering, and graph query traversal.
- Forensic artifact analysis: static disassembly, JavaScript runtime unpacking, and network protocol inspection.
- Comprehensive reporting: persistent session documentation, task receipt logging, and structured deliverables.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`create-canvas`](./create-canvas/SKILL.md) | **create-canvas** | Create a Copilot extension canvas at user, workspace, or plugin scope. |
| [`graphify`](./graphify/SKILL.md) | **graphify** | Use for any question about a codebase, its architecture, file relationships, or project content — especially when graphify-out/ exists, where the question should be treated as a graphify query first. Turns any input (code, docs, papers, images, videos) into a persistent knowledge graph with god nodes, community detection, and query/path/explain tools. |
| [`playground`](./playground/SKILL.md) | **playground** | Creates interactive HTML playgrounds — self-contained single-file explorers that let users configure something visually through controls, see a live preview, and copy out a prompt. Use when the user asks to make a playground, explorer, or interactive tool for a topic. |
| [`project-artifact`](./project-artifact/SKILL.md) | **project-artifact** | Generate and publish a project status artifact — an opinionated, tabbed status page for a project too big for one update (overview & success criteria, the workstream sequence, next steps, plus background, plan, risks & open questions, and decisions/FAQ when they earn a tab) — published with the built-in Artifact tool to a default-private claude.ai page the user can share with teammates. Use when a piece of work spans several workstreams and you want a shareable overview kept current. Each artifact is backed by a small per-project config in the plugin data dir, so refreshing it re-gathers live state, redeploys the same URL, and reports only the delta. For software projects whose workstreams are PRs, also read swe.md (the X.Y PR-numbering convention; pulling PR state with gh/git; a per-PR detail block). Needs the built-in Artifact tool (claude.ai login). Not for single-PR changes or public docs. |
| [`receipts`](./receipts/SKILL.md) | **receipts** | Generate a personal Claude Code usage & impact report ("receipts") from this machine's local session transcripts — for justifying Claude Code usage/spend to a manager, self-review, or "what have I been using this for" check-ins. Mines ~/.claude/projects locally (no extra API calls beyond one final write-up), cross-references local git history, and writes a markdown report plus a self-contained HTML receipt to your home directory. Use when the user asks for "receipts", an "impact report", "usage report", wants to "show my Claude Code activity", "prove the value of Claude Code", or runs `/receipts`. |
| [`reverse-engineer-anything`](./reverse-engineer-anything/SKILL.md) | **reverse-engineer-anything** | Reverse engineer native, managed, Electron/JavaScript, packaged, firmware, and browser targets with REA. Use shipped-artifact or requested runtime evidence to explain features, compare versions, decompile code, or guide a reconstruction. Skip REA for ordinary source-repository architecture analysis. |
| [`session-report`](./session-report/SKILL.md) | **session-report** | Generate an explorable HTML report of Claude Code session usage (tokens, cache, subagents, skills, expensive prompts) from ~/.claude/projects transcripts. |

---

## Detailed Skill Overviews

### [`create-canvas`](./create-canvas/SKILL.md)

- **Skill Identifier:** `create-canvas`
- **Path:** [`analysis-reverse-engineering/create-canvas/`](./create-canvas/)
- **Operational Summary:**
  Create a Copilot extension canvas at user, workspace, or plugin scope.

### [`graphify`](./graphify/SKILL.md)

- **Skill Identifier:** `graphify`
- **Path:** [`analysis-reverse-engineering/graphify/`](./graphify/)
- **Operational Summary:**
  Use for any question about a codebase, its architecture, file relationships, or project content — especially when graphify-out/ exists, where the question should be treated as a graphify query first. Turns any input (code, docs, papers, images, videos) into a persistent knowledge graph with god nodes, community detection, and query/path/explain tools.

### [`playground`](./playground/SKILL.md)

- **Skill Identifier:** `playground`
- **Path:** [`analysis-reverse-engineering/playground/`](./playground/)
- **Operational Summary:**
  Creates interactive HTML playgrounds — self-contained single-file explorers that let users configure something visually through controls, see a live preview, and copy out a prompt. Use when the user asks to make a playground, explorer, or interactive tool for a topic.

### [`project-artifact`](./project-artifact/SKILL.md)

- **Skill Identifier:** `project-artifact`
- **Path:** [`analysis-reverse-engineering/project-artifact/`](./project-artifact/)
- **Operational Summary:**
  Generate and publish a project status artifact — an opinionated, tabbed status page for a project too big for one update (overview & success criteria, the workstream sequence, next steps, plus background, plan, risks & open questions, and decisions/FAQ when they earn a tab) — published with the built-in Artifact tool to a default-private claude.ai page the user can share with teammates. Use when a piece of work spans several workstreams and you want a shareable overview kept current. Each artifact is backed by a small per-project config in the plugin data dir, so refreshing it re-gathers live state, redeploys the same URL, and reports only the delta. For software projects whose workstreams are PRs, also read swe.md (the X.Y PR-numbering convention; pulling PR state with gh/git; a per-PR detail block). Needs the built-in Artifact tool (claude.ai login). Not for single-PR changes or public docs.

### [`receipts`](./receipts/SKILL.md)

- **Skill Identifier:** `receipts`
- **Path:** [`analysis-reverse-engineering/receipts/`](./receipts/)
- **Operational Summary:**
  Generate a personal Claude Code usage & impact report ("receipts") from this machine's local session transcripts — for justifying Claude Code usage/spend to a manager, self-review, or "what have I been using this for" check-ins. Mines ~/.claude/projects locally (no extra API calls beyond one final write-up), cross-references local git history, and writes a markdown report plus a self-contained HTML receipt to your home directory. Use when the user asks for "receipts", an "impact report", "usage report", wants to "show my Claude Code activity", "prove the value of Claude Code", or runs `/receipts`.

### [`reverse-engineer-anything`](./reverse-engineer-anything/SKILL.md)

- **Skill Identifier:** `reverse-engineer-anything`
- **Path:** [`analysis-reverse-engineering/reverse-engineer-anything/`](./reverse-engineer-anything/)
- **Operational Summary:**
  Reverse engineer native, managed, Electron/JavaScript, packaged, firmware, and browser targets with REA. Use shipped-artifact or requested runtime evidence to explain features, compare versions, decompile code, or guide a reconstruction. Skip REA for ordinary source-repository architecture analysis.

### [`session-report`](./session-report/SKILL.md)

- **Skill Identifier:** `session-report`
- **Path:** [`analysis-reverse-engineering/session-report/`](./session-report/)
- **Operational Summary:**
  Generate an explorable HTML report of Claude Code session usage (tokens, cache, subagents, skills, expensive prompts) from ~/.claude/projects transcripts.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s ~/ai-agent-skills/analysis-reverse-engineering/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r ~/ai-agent-skills/analysis-reverse-engineering/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
