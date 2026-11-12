# unslop-ai-design

A strict 20-rule design rubric and agent skill to eliminate AI frontend clichés, decorative clutter, and poor UI defaults from LLM-generated code.

Modern language models generate recognizable visual tells: gratuitous badges, low-contrast text on dark backgrounds, random italicized words in hero headers, monospaced fonts on ordinary numbers, broken nested border radii, and static states lacking feedback.

`unslop-ai-design` provides a concise, enforceable checklist and reference implementation to audit and refactor AI-generated interfaces into production-ready, human-crafted design systems.

---

## The 20 Rules

| # | Rule | Category | Core Fix |
|---|---|---|---|
| 1 | **No filter badges** | Content & Anti-Clutter | Remove vanity pill tags (`[AI-Powered]`, `v2.0 Beta`); keep only interactive filters and actual entity statuses. |
| 2 | **Drop redundant labels** | Content & Anti-Clutter | Remove self-evident form labels; use `sr-only` to preserve accessibility without visual clutter. |
| 3 | **Unitalicize random words** | Content & Anti-Clutter | Strip arbitrary `italic` spans in headings; use weight or color contrast for emphasis. |
| 4 | **Mono only where needed** | Content & Anti-Clutter | Reserve `font-mono` for code, hashes, and endpoints; use standard sans-serif with `tabular-nums` for metrics. |
| 5 | **Use a defined design system** | Geometry & Tokens | Enforce a strict 4px/8px spatial rhythm, a 5-tier type scale, and standardized token primitives. |
| 6 | **Show the actual product** | Layout & Content | Replace abstract 3D cubes, floating spheres, and generic illustrations with real UI screens, logs, and data. |
| 7 | **Enlarge the main feature** | Hierarchy & Layout | Allocate at least 55-60% of above-the-fold visual weight to the primary product workflow. |
| 8 | **Group with spacing** | Hierarchy & Layout | Rely on whitespace proximity (`gap-8` to `gap-16`) instead of boxing every element in separate bordered cards. |
| 9 | **Make headlines specific** | Content & Anti-Clutter | Replace generic marketing platitudes (*"Supercharge your workflow"*) with concrete functional facts. |
| 10 | **Emphasize the CTA** | Hierarchy & Layout | Exactly one high-contrast primary call-to-action per viewport; demote secondary actions to outline or ghost. |
| 11 | **Add an intentional accent color** | Geometry & Tokens | Anchor interfaces in high-contrast neutrals, with one deliberate accent for interactive states and focus rings. |
| 12 | **Keep icons consistent** | Geometry & Tokens | Use a single icon family with uniform stroke width (`1.75px` or `2px`) and consistent container bounding boxes. |
| 13 | **Remove embellishments** | Content & Anti-Clutter | Strip floating ambient glow blobs (`blur-3xl`), background dot meshes, decorative squiggles, and card borders. |
| 14 | **Concentric border radius** | Geometry & Tokens | Enforce `inner_radius = outer_radius - padding`. Set inner radius to `0` when padding exceeds outer radius. |
| 15 | **Improve text contrast** | Typography & States | Enforce WCAG AA (>= 4.5:1 for body and meta text, >= 3:1 for UI elements); ban low-opacity washed-out grays. |
| 16 | **Wrap headlines properly** | Typography & States | Set `text-wrap: balance` on headings and subheadings to prevent single-word orphan line wraps. |
| 17 | **Align by eyes, not pixels** | Hierarchy & Layout | Optically compensate asymmetric icons (e.g., play triangle margin offsets, baseline currency alignments). |
| 18 | **Use tabular numbers** | Typography & States | Apply `tabular-nums` / `font-variant-numeric: tabular-nums` to timers, metrics, financial numbers, and tables. |
| 19 | **Add loading states** | Typography & States | Provide dimension-preserving skeleton screens and submit button loading spinners during async calls. |
| 20 | **Animate useful feedback** | Typography & States | Restrict animations to functional user feedback (hover/active micro-transitions, state mutation confirmations). |

---

## Installation

### Antigravity / Gemini CLI

To install globally:

```bash
git clone https://github.com/ind4x/unslop-ai-design.git ~/.gemini/skills/unslop-ai-design
```

Or copy `SKILL.md` directly into your workspace:

```bash
mkdir -p .agents/skills/unslop-ai-design
cp path/to/unslop-ai-design/SKILL.md .agents/skills/unslop-ai-design/
```

### Claude Code

Add to your custom instructions or copy `SKILL.md` into your `.claude/skills` directory:

```bash
mkdir -p ~/.claude/skills/unslop-ai-design
cp SKILL.md ~/.claude/skills/unslop-ai-design/
```

### Cursor / Windsurf / Copilot

Add the rules to your project rules file (`.cursorrules`, `.windsurfrules`, or `.github/copilot-instructions.md`):

```markdown
# UI/UX Quality Standard: Unslop AI Design
Refer to SKILL.md for the 20-rule design rubric:
- Remove vanity badges, redundant labels, random italics, decorative meshes, and inappropriate monospace.
- Enforce concentric border radius: inner_radius = outer_radius - padding.
- Emphasize single primary CTA; use text-wrap: balance; use tabular-nums on all metrics.
- Group with spacing rather than boxing every item in bordered cards.
```

---

## 4-Stage Audit Workflow

When auditing or generating code, evaluate in four linear passes:

1. **Anti-Clutter (Pass 1)**: Strip decorative pill tags, redundant labels, random italics, ambient glow blurs, and unnecessary `font-mono`.
2. **Layout & Geometry (Pass 2)**: Feature actual product UI, enlarge the primary workflow, group by whitespace, verify `inner_radius = outer_radius - padding`, and establish one dominant CTA.
3. **Typography & Colors (Pass 3)**: Verify 4.5:1 text contrast, balance headline wraps with `text-wrap: balance`, set `tabular-nums` on metrics, and consolidate accent colors.
4. **State Hardening (Pass 4)**: Unify icon family and strokes, optically compensate centered elements, implement dimension-preserving loading skeletons, and ensure micro-transitions on interactive states.

---

## License

MIT (c) 2026 Youssef Fellah
