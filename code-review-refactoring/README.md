# Code Review, Refactoring & Typings

Skills for rigorous static analysis, diff reviews, minimal surgical changes (Ponytail philosophy), Pylance profiling, and strict type enforcement.

---

## Category Principles & Scope

- Surgical diffs and boy scout rule: localized cleanups without gratuitous rewrites or expanded blast radiuses.
- Strict typing and static contract enforcement for both modern TypeScript and Python ecosystems.
- Pragmatic complexity control: eliminating boilerplate, deferring premature optimizations, and maintaining high testability.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`add-python-version-support`](./add-python-version-support/SKILL.md) | **add-python-version-support** | Guide changes required when a project adds a newer Python version above its current tested ceiling while preserving its existing minimum. Use when asked to support, test, certify, or prepare for a newer Python release at the upper end of the support range without dropping existing runtimes. |
| [`code-reviewer`](./code-reviewer/SKILL.md) | **code-reviewer** | Use this skill to review code. It supports both local changes (staged or working tree) and remote Pull Requests (by ID or URL). It focuses on correctness, maintainability, and adherence to project standards. |
| [`docs-writer`](./docs-writer/SKILL.md) | **docs-writer** | Always use this skill when the task involves writing, reviewing, or editing files in the `/docs` directory or any `.md` files in the repository. |
| [`drop-python-version-support`](./drop-python-version-support/SKILL.md) | **drop-python-version-support** | Guide changes required when a project drops one or more oldest supported Python versions and raises its minimum supported version. Use when asked to remove the oldest supported runtimes, raise the minimum Python requirement, modernize code after raising the Python floor, or upgrade/migrate by replacing older runtimes. |
| [`ponytail`](./ponytail/SKILL.md) | **ponytail** | > Lazy senior dev mode: the smallest change that fully solves the task, and a reply a busy human understands in one read. Use on any coding task (writing, fixing, refactoring, reviewing, choosing dependencies) and when the user says "ponytail", "be lazy", "simplest solution", "yagni", or complains about over-engineering or bloat. Levels: lite, full (default), ultra. |
| [`ponytail-audit`](./ponytail-audit/SKILL.md) | **ponytail-audit** | > Quality audit of a whole repo: bugs, security holes, what breaks under real load, risky code without tests, slow paths, and what to delete, merge or split. Ranked, each finding explained in plain English. One-shot report, changes nothing. Use for "audit this codebase", "review the whole repo", "find bloat", "what can I delete", /ponytail-audit. |
| [`ponytail-debt`](./ponytail-debt/SKILL.md) | **ponytail-debt** | > List every `shortcut:` comment (and older `ponytail:` ones) as a debt ledger. One-shot report, changes nothing. Use for "ponytail debt", "what did ponytail defer", "list the shortcuts", /ponytail-debt. |
| [`ponytail-gain`](./ponytail-gain/SKILL.md) | **ponytail-gain** | > Show ponytail's measured savings (code, cost, speed) from the benchmark. One-shot display. Use for /ponytail-gain, "what does ponytail save", "ponytail impact". |
| [`ponytail-help`](./ponytail-help/SKILL.md) | **ponytail-help** | > Quick reference for ponytail levels, skills and commands. One-shot display. Use for /ponytail-help, "ponytail help", "how do I use ponytail". |
| [`ponytail-review`](./ponytail-review/SKILL.md) | **ponytail-review** | > Quality review of a change: is the logic right, is it safe, does it hold under real load, is risky code tested, is it fast enough, and is every line needed. Reads the connected code, not only the diff. Each finding is explained in plain English. Use for "review this", "code review", "review the last commit", "review my PR", "is this over-engineered", /ponytail-review. |
| [`pylance-docs`](./pylance-docs/SKILL.md) | **pylance-docs** | Use when the user explicitly asks for the Pylance docs skill, or when an answer depends on current official Pylance documentation for settings, diagnostics, configuration, troubleshooting, feature behavior, or supported workflows. |
| [`pylance-python-profiling`](./pylance-python-profiling/SKILL.md) | **pylance-python-profiling** | Use when the user wants to profile Python code with Pylance: capture CPU time (Tachyon), trace calls (sys.monitoring), or memory (Memray); profile a whole run or a specific region between two source locations; add sub-region markers; and explore the resulting profile (hot functions, call trees, time slices). Also use for the 3.15+ interpreter requirement and related error guidance. |
| [`pylance-refactoring`](./pylance-refactoring/SKILL.md) | **pylance-refactoring** | Use when the user explicitly asks for the Pylance refactoring skill, or when they want named automated Python refactorings applied to one file, many files, a workspace, a folder subset, or a composed cleanup workflow such as workspace-wide unused-import cleanup, wildcard-import conversion followed by unused-import cleanup, inferred type annotations, or Pylance fix-all. |
| [`python-add-type-annotations`](./python-add-type-annotations/SKILL.md) | **python-add-type-annotations** | Use when the user explicitly asks for the Python type annotation skill, or when they want to make their own Python source type-safe by adding inline type annotations to one file, a set of files, or a package/workspace in bulk — annotating function return types, parameters, module-level and class-level variables/constants (including dataclass and similar fields), validating diagnostics against a baseline, and reporting newly surfaced type errors. |
| [`python-fact-grounded-coding`](./python-fact-grounded-coding/SKILL.md) | **python-fact-grounded-coding** | Use when the user explicitly asks for the Python fact-grounded coding skill, or when a Python coding, debugging, explanation, or bug-fix task should be grounded in verified Pylance facts, runtime values, diagnostics, selected interpreter state, tests, or debugger evidence before changing code or reporting a conclusion. |
| [`python-type-inference`](./python-type-inference/SKILL.md) | **python-type-inference** | Use when the user explicitly asks for the Python type inference skill, or when a task needs the single correct type for a specific Python symbol — a function return, parameter, module-level value, or class/instance field — and that type must be verified against real code rather than guessed. This is the shared core used by the type-annotation and stub-writing skills. |
| [`python-write-stubs`](./python-write-stubs/SKILL.md) | **python-write-stubs** | Use when the user explicitly asks for the Python stub-writing skill, wants to create or improve `.pyi` type stubs for a third-party Python package, or needs partial stubs under a workspace `typings/` directory without modifying installed package source. Generates stubs through Pylance, resolves uncertain types with the Python type-inference skill, and validates public API, diagnostics, runtime compatibility, and type completeness. |
| [`troubleshoot`](./troubleshoot/SKILL.md) | **troubleshoot** | Investigate unexpected chat agent behavior by analyzing direct debug logs in JSONL files. Use when users ask why something happened, why a request was slow, why tools or subagents were used or skipped, or why instructions/skills/agents did not load. |
| [`typescript-setup`](./typescript-setup/SKILL.md) | **typescript-setup** | How to set up a new TypeScript project |
| [`typescript-update`](./typescript-update/SKILL.md) | **typescript-update** | Guidance for updating to the newer versions of TypeScript. Use this when you need to upgrade TypeScript or as part of a larger dependency update process. |

---

## Detailed Skill Overviews

### [`add-python-version-support`](./add-python-version-support/SKILL.md)

- **Skill Identifier:** `add-python-version-support`
- **Path:** [`code-review-refactoring/add-python-version-support/`](./add-python-version-support/)
- **Operational Summary:**
  Guide changes required when a project adds a newer Python version above its current tested ceiling while preserving its existing minimum. Use when asked to support, test, certify, or prepare for a newer Python release at the upper end of the support range without dropping existing runtimes.

### [`code-reviewer`](./code-reviewer/SKILL.md)

- **Skill Identifier:** `code-reviewer`
- **Path:** [`code-review-refactoring/code-reviewer/`](./code-reviewer/)
- **Operational Summary:**
  Use this skill to review code. It supports both local changes (staged or working tree) and remote Pull Requests (by ID or URL). It focuses on correctness, maintainability, and adherence to project standards.

### [`docs-writer`](./docs-writer/SKILL.md)

- **Skill Identifier:** `docs-writer`
- **Path:** [`code-review-refactoring/docs-writer/`](./docs-writer/)
- **Operational Summary:**
  Always use this skill when the task involves writing, reviewing, or editing files in the `/docs` directory or any `.md` files in the repository.

### [`drop-python-version-support`](./drop-python-version-support/SKILL.md)

- **Skill Identifier:** `drop-python-version-support`
- **Path:** [`code-review-refactoring/drop-python-version-support/`](./drop-python-version-support/)
- **Operational Summary:**
  Guide changes required when a project drops one or more oldest supported Python versions and raises its minimum supported version. Use when asked to remove the oldest supported runtimes, raise the minimum Python requirement, modernize code after raising the Python floor, or upgrade/migrate by replacing older runtimes.

### [`ponytail`](./ponytail/SKILL.md)

- **Skill Identifier:** `ponytail`
- **Path:** [`code-review-refactoring/ponytail/`](./ponytail/)
- **Operational Summary:**
  > Lazy senior dev mode: the smallest change that fully solves the task, and a reply a busy human understands in one read. Use on any coding task (writing, fixing, refactoring, reviewing, choosing dependencies) and when the user says "ponytail", "be lazy", "simplest solution", "yagni", or complains about over-engineering or bloat. Levels: lite, full (default), ultra.

### [`ponytail-audit`](./ponytail-audit/SKILL.md)

- **Skill Identifier:** `ponytail-audit`
- **Path:** [`code-review-refactoring/ponytail-audit/`](./ponytail-audit/)
- **Operational Summary:**
  > Quality audit of a whole repo: bugs, security holes, what breaks under real load, risky code without tests, slow paths, and what to delete, merge or split. Ranked, each finding explained in plain English. One-shot report, changes nothing. Use for "audit this codebase", "review the whole repo", "find bloat", "what can I delete", /ponytail-audit.

### [`ponytail-debt`](./ponytail-debt/SKILL.md)

- **Skill Identifier:** `ponytail-debt`
- **Path:** [`code-review-refactoring/ponytail-debt/`](./ponytail-debt/)
- **Operational Summary:**
  > List every `shortcut:` comment (and older `ponytail:` ones) as a debt ledger. One-shot report, changes nothing. Use for "ponytail debt", "what did ponytail defer", "list the shortcuts", /ponytail-debt.

### [`ponytail-gain`](./ponytail-gain/SKILL.md)

- **Skill Identifier:** `ponytail-gain`
- **Path:** [`code-review-refactoring/ponytail-gain/`](./ponytail-gain/)
- **Operational Summary:**
  > Show ponytail's measured savings (code, cost, speed) from the benchmark. One-shot display. Use for /ponytail-gain, "what does ponytail save", "ponytail impact".

### [`ponytail-help`](./ponytail-help/SKILL.md)

- **Skill Identifier:** `ponytail-help`
- **Path:** [`code-review-refactoring/ponytail-help/`](./ponytail-help/)
- **Operational Summary:**
  > Quick reference for ponytail levels, skills and commands. One-shot display. Use for /ponytail-help, "ponytail help", "how do I use ponytail".

### [`ponytail-review`](./ponytail-review/SKILL.md)

- **Skill Identifier:** `ponytail-review`
- **Path:** [`code-review-refactoring/ponytail-review/`](./ponytail-review/)
- **Operational Summary:**
  > Quality review of a change: is the logic right, is it safe, does it hold under real load, is risky code tested, is it fast enough, and is every line needed. Reads the connected code, not only the diff. Each finding is explained in plain English. Use for "review this", "code review", "review the last commit", "review my PR", "is this over-engineered", /ponytail-review.

### [`pylance-docs`](./pylance-docs/SKILL.md)

- **Skill Identifier:** `pylance-docs`
- **Path:** [`code-review-refactoring/pylance-docs/`](./pylance-docs/)
- **Operational Summary:**
  Use when the user explicitly asks for the Pylance docs skill, or when an answer depends on current official Pylance documentation for settings, diagnostics, configuration, troubleshooting, feature behavior, or supported workflows.

### [`pylance-python-profiling`](./pylance-python-profiling/SKILL.md)

- **Skill Identifier:** `pylance-python-profiling`
- **Path:** [`code-review-refactoring/pylance-python-profiling/`](./pylance-python-profiling/)
- **Operational Summary:**
  Use when the user wants to profile Python code with Pylance: capture CPU time (Tachyon), trace calls (sys.monitoring), or memory (Memray); profile a whole run or a specific region between two source locations; add sub-region markers; and explore the resulting profile (hot functions, call trees, time slices). Also use for the 3.15+ interpreter requirement and related error guidance.

### [`pylance-refactoring`](./pylance-refactoring/SKILL.md)

- **Skill Identifier:** `pylance-refactoring`
- **Path:** [`code-review-refactoring/pylance-refactoring/`](./pylance-refactoring/)
- **Operational Summary:**
  Use when the user explicitly asks for the Pylance refactoring skill, or when they want named automated Python refactorings applied to one file, many files, a workspace, a folder subset, or a composed cleanup workflow such as workspace-wide unused-import cleanup, wildcard-import conversion followed by unused-import cleanup, inferred type annotations, or Pylance fix-all.

### [`python-add-type-annotations`](./python-add-type-annotations/SKILL.md)

- **Skill Identifier:** `python-add-type-annotations`
- **Path:** [`code-review-refactoring/python-add-type-annotations/`](./python-add-type-annotations/)
- **Operational Summary:**
  Use when the user explicitly asks for the Python type annotation skill, or when they want to make their own Python source type-safe by adding inline type annotations to one file, a set of files, or a package/workspace in bulk — annotating function return types, parameters, module-level and class-level variables/constants (including dataclass and similar fields), validating diagnostics against a baseline, and reporting newly surfaced type errors.

### [`python-fact-grounded-coding`](./python-fact-grounded-coding/SKILL.md)

- **Skill Identifier:** `python-fact-grounded-coding`
- **Path:** [`code-review-refactoring/python-fact-grounded-coding/`](./python-fact-grounded-coding/)
- **Operational Summary:**
  Use when the user explicitly asks for the Python fact-grounded coding skill, or when a Python coding, debugging, explanation, or bug-fix task should be grounded in verified Pylance facts, runtime values, diagnostics, selected interpreter state, tests, or debugger evidence before changing code or reporting a conclusion.

### [`python-type-inference`](./python-type-inference/SKILL.md)

- **Skill Identifier:** `python-type-inference`
- **Path:** [`code-review-refactoring/python-type-inference/`](./python-type-inference/)
- **Operational Summary:**
  Use when the user explicitly asks for the Python type inference skill, or when a task needs the single correct type for a specific Python symbol — a function return, parameter, module-level value, or class/instance field — and that type must be verified against real code rather than guessed. This is the shared core used by the type-annotation and stub-writing skills.

### [`python-write-stubs`](./python-write-stubs/SKILL.md)

- **Skill Identifier:** `python-write-stubs`
- **Path:** [`code-review-refactoring/python-write-stubs/`](./python-write-stubs/)
- **Operational Summary:**
  Use when the user explicitly asks for the Python stub-writing skill, wants to create or improve `.pyi` type stubs for a third-party Python package, or needs partial stubs under a workspace `typings/` directory without modifying installed package source. Generates stubs through Pylance, resolves uncertain types with the Python type-inference skill, and validates public API, diagnostics, runtime compatibility, and type completeness.

### [`troubleshoot`](./troubleshoot/SKILL.md)

- **Skill Identifier:** `troubleshoot`
- **Path:** [`code-review-refactoring/troubleshoot/`](./troubleshoot/)
- **Operational Summary:**
  Investigate unexpected chat agent behavior by analyzing direct debug logs in JSONL files. Use when users ask why something happened, why a request was slow, why tools or subagents were used or skipped, or why instructions/skills/agents did not load.

### [`typescript-setup`](./typescript-setup/SKILL.md)

- **Skill Identifier:** `typescript-setup`
- **Path:** [`code-review-refactoring/typescript-setup/`](./typescript-setup/)
- **Operational Summary:**
  How to set up a new TypeScript project

### [`typescript-update`](./typescript-update/SKILL.md)

- **Skill Identifier:** `typescript-update`
- **Path:** [`code-review-refactoring/typescript-update/`](./typescript-update/)
- **Operational Summary:**
  Guidance for updating to the newer versions of TypeScript. Use this when you need to upgrade TypeScript or as part of a larger dependency update process.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s /home/youssef/skills/code-review-refactoring/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r /home/youssef/skills/code-review-refactoring/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
