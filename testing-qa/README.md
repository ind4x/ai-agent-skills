# Testing, Quality Assurance & Debugging

Skills for end-to-end browser automation with Playwright, systematic root-cause investigation, and destructive action safety guards.

---

## Category Principles & Scope

- Root-cause isolation: systematic bug recreation, log inspection, and reproducible diagnostic verifications.
- Automated headless browser validation across desktop and mobile viewports with screenshot assertions.
- Safety-first operation: guard mechanisms preventing accidental execution of destructive shell commands or unverified migrations.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`guard`](./guard/SKILL.md) | **guard** | Full safety mode: destructive command warnings + directory-scoped edits. (gstack) |
| [`investigate`](./investigate/SKILL.md) | **investigate** | Systematic debugging with root cause investigation. (gstack) |
| [`playwright-cli`](./playwright-cli/SKILL.md) | **playwright-cli** | Automate browser interactions, test web pages and work with Playwright tests. |
| [`playwright-component-testing`](./playwright-component-testing/SKILL.md) | **playwright-component-testing** | Set up component testing with Playwright using a story gallery — scaffold stories and a gallery dev page driven by the built-in mount fixture, no dedicated component-testing runtime. Use when asked to test React or Vue components in isolation with Playwright, or to migrate off @playwright/experimental-ct-react / -vue. |
| [`playwright-trace`](./playwright-trace/SKILL.md) | **playwright-trace** | Inspect Playwright trace files from the command line — list actions, view requests, console, errors, snapshots and screenshots. |
| [`qa`](./qa/SKILL.md) | **qa** | Systematically QA test a web application and fix bugs found. (gstack) |

---

## Detailed Skill Overviews

### [`guard`](./guard/SKILL.md)

- **Skill Identifier:** `guard`
- **Path:** [`testing-qa/guard/`](./guard/)
- **Allowed Tools:** `- Bash`
- **Operational Summary:**
  Full safety mode: destructive command warnings + directory-scoped edits. (gstack)

### [`investigate`](./investigate/SKILL.md)

- **Skill Identifier:** `investigate`
- **Path:** [`testing-qa/investigate/`](./investigate/)
- **Allowed Tools:** `- Bash`
- **Operational Summary:**
  Systematic debugging with root cause investigation. (gstack)

### [`playwright-cli`](./playwright-cli/SKILL.md)

- **Skill Identifier:** `playwright-cli`
- **Path:** [`testing-qa/playwright-cli/`](./playwright-cli/)
- **Allowed Tools:** `Bash(playwright-cli:*) Bash(npx playwright:*) Bash(npx --no-install playwright:*)`
- **Operational Summary:**
  Automate browser interactions, test web pages and work with Playwright tests.

### [`playwright-component-testing`](./playwright-component-testing/SKILL.md)

- **Skill Identifier:** `playwright-component-testing`
- **Path:** [`testing-qa/playwright-component-testing/`](./playwright-component-testing/)
- **Operational Summary:**
  Set up component testing with Playwright using a story gallery — scaffold stories and a gallery dev page driven by the built-in mount fixture, no dedicated component-testing runtime. Use when asked to test React or Vue components in isolation with Playwright, or to migrate off @playwright/experimental-ct-react / -vue.

### [`playwright-trace`](./playwright-trace/SKILL.md)

- **Skill Identifier:** `playwright-trace`
- **Path:** [`testing-qa/playwright-trace/`](./playwright-trace/)
- **Allowed Tools:** `Bash(npx playwright trace:*)`
- **Operational Summary:**
  Inspect Playwright trace files from the command line — list actions, view requests, console, errors, snapshots and screenshots.

### [`qa`](./qa/SKILL.md)

- **Skill Identifier:** `qa`
- **Path:** [`testing-qa/qa/`](./qa/)
- **Allowed Tools:** `- Bash`
- **Operational Summary:**
  Systematically QA test a web application and fix bugs found. (gstack)

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s ~/skills/testing-qa/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r ~/skills/testing-qa/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
