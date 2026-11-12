---
name: unslop-ai-design
description: Strict 20-rule design rubric to eliminate AI frontend clichés, decorative clutter, and poor UI defaults. Covers removing vanity badges, redundant labels, random italics, decorative embellishments, and monospace overuse; enforcing visual hierarchy, dominant CTAs, product-first visuals, concentric border radii, optical alignment, text-wrap balance, tabular numbers, and production-ready states.
---

# Unslop AI Design

A systematic 20-rule rubric designed to identify, strip, and refactor the visual and architectural clichés common in LLM-generated frontend code.

AI-generated interfaces suffer from predictable defaults: gratuitous floating gradients, pill badges on everything, low-contrast text, missing hierarchy, broken nested border radii, and static states. This skill provides an objective checklist and code patterns to produce production-grade, human-crafted interfaces.

---

## 20-Rule Quick Reference Checklist

| # | Rule | Category | Primary Target |
|---|---|---|---|
| 1 | No filter badges | Content & Anti-Clutter | Remove vanity/decorative pill badges |
| 2 | Drop redundant labels | Content & Anti-Clutter | Remove self-evident form labels; use `sr-only` |
| 3 | Unitalicize random words | Content & Anti-Clutter | Strip `italic` / `<i>` emphasis in headings |
| 4 | Mono only where needed | Content & Anti-Clutter | Reserve `font-mono` for code, hashes, and tokens |
| 5 | Use a defined design system | Geometry & Tokens | Enforce 4px/8px grid, 5-tier type scale, tokens |
| 6 | Show the actual product | Layout & Content | Replace abstract 3D shapes with real UI/data |
| 7 | Enlarge the main feature | Hierarchy & Layout | Hero feature takes at least 55-60% visual weight |
| 8 | Group with spacing | Hierarchy & Layout | Use whitespace proximity instead of boxing everything |
| 9 | Make headlines specific | Content & Anti-Clutter | Replace generic platitudes with functional facts |
| 10 | Emphasize the CTA | Hierarchy & Layout | Single high-contrast primary action above the fold |
| 11 | Add an intentional accent color | Geometry & Tokens | 1 distinct accent against neutral base surfaces |
| 12 | Keep icons consistent | Geometry & Tokens | Single icon family, unified stroke and bounding box |
| 13 | Remove embellishments | Content & Anti-Clutter | Strip ambient glow, background meshes, decorative dots |
| 14 | Concentric border radius | Geometry & Tokens | Strict formula: `inner_radius = outer_radius - padding` |
| 15 | Improve text contrast | Typography & States | Enforce WCAG AA (>= 4.5:1 text, >= 3:1 UI elements) |
| 16 | Wrap headlines properly | Typography & States | Set `text-wrap: balance` to eliminate orphan words |
| 17 | Align by eyes, not pixels | Hierarchy & Layout | Optically offset asymmetric icons and symbols |
| 18 | Use tabular numbers | Typography & States | Set `tabular-nums` on metrics, timers, and tables |
| 19 | Add loading states | Typography & States | Dimension-preserving skeletons and disabled states |
| 20 | Animate useful feedback | Typography & States | Micro-transitions on user actions only; no entrance loops |

---

## Detailed Rules & Code Patterns

### 1. No Filter Badges
* **Slop Pattern**: Placing decorative pill badges above headings or on cards (e.g., `[AI-Powered]`, `Next Gen Platform`, `v2.0 Beta`).
* **Rule**: Badges must only exist if they represent active interactive filters or real entity states (`Active`, `Failed`, `Pending`). Delete all vanity badges.
* **Refactor**:
```tsx
// SLOP
<div className="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-violet-500/10 text-violet-400 text-xs border border-violet-500/20">
  <span>AI-Powered Database</span>
</div>

// UNSLOP: Remove the element entirely or replace with a real breadcrumb/category
<nav aria-label="Breadcrumb" className="text-xs text-neutral-400 font-medium">
  Infrastructure / Databases
</nav>
```

---

### 2. Drop Redundant Labels
* **Slop Pattern**: Adding labels that repeat what the placeholder, button, or context already makes 100% obvious (e.g. `Search:` before a search input).
* **Rule**: When context is unambiguous, visually hide the label using accessible utility classes (`sr-only`), keeping the UI clean while preserving screen-reader accessibility.
* **Refactor**:
```tsx
// SLOP
<label htmlFor="search" className="block text-sm font-medium text-neutral-700 mb-1">
  Search Query
</label>
<input id="search" type="search" placeholder="Search query..." />

// UNSLOP
<label htmlFor="search" className="sr-only">Search index</label>
<div className="relative">
  <SearchIcon className="absolute left-3 top-1/2 -translate-y-1/2 size-4 text-neutral-400" aria-hidden="true" />
  <input id="search" type="search" placeholder="Filter repositories or commands..." className="pl-9 pr-4 py-2" />
</div>
```

---

### 3. Unitalicize Random Words
* **Slop Pattern**: Styling a single arbitrary word inside a heading with italics (e.g., "Build *faster* with autonomous agents").
* **Rule**: Ban decorative italics in display titles and section headings. Emphasize concepts through typographic hierarchy, position, or subtle color distinction.
* **Refactor**:
```tsx
// SLOP
<h1 className="text-4xl font-bold">
  Experience <span className="italic font-serif text-violet-400">effortless</span> infrastructure scaling.
</h1>

// UNSLOP
<h1 className="text-4xl font-bold tracking-tight text-neutral-900 dark:text-neutral-50 text-balance">
  Infrastructure that scales without manual configuration.
</h1>
```

---

### 4. Monospace Only Where Needed
* **Slop Pattern**: Using `font-mono` for standard metrics, dates, card tags, or body copy to give a false "developer vibe".
* **Rule**: Restrict `font-mono` to functional technical data: code blocks, git hashes, terminal output, API endpoints, and cryptographic keys. Standard numbers use regular sans-serif with `tabular-nums`.
* **Refactor**:
```tsx
// SLOP
<p className="font-mono text-sm text-neutral-400">Created: 2026-11-08</p>
<div className="font-mono text-2xl font-bold">$124,500.00</div>

// UNSLOP
<p className="text-sm text-neutral-500">Created Nov 8, 2026</p>
<div className="text-2xl font-semibold tracking-tight tabular-nums text-neutral-900 dark:text-neutral-50">
  $124,500.00
</div>
```

---

### 5. Use a Defined Design System
* **Slop Pattern**: Random ad-hoc pixel values (`p-[13px]`, `gap-[7px]`, mixing `zinc-800`, `gray-900`, `slate-950`).
* **Rule**: Strictly adhere to fixed token scales:
  * **Spatial Grid**: Base-4 / Base-8 (`4px (1)`, `8px (2)`, `12px (3)`, `16px (4)`, `24px (6)`, `32px (8)`, `48px (12)`, `64px (16)`).
  * **Typographic Scale**: Strict 5 tiers (`text-xs: 12px`, `text-sm: 14px`, `text-base: 16px`, `text-xl: 20px`, `text-3xl: 30px`).
  * **Palette System**: High-contrast neutral base surfaces (Slate, Zinc, or Neutral) paired with an intentional accent palette (reference Sanzō Wada color combinations from `~/.gemini/sanzo_wada_colors.json`).

---

### 6. Show the Actual Product
* **Slop Pattern**: Decorative 3D floating glass cubes, abstract purple spheres, or generic cartoon isometric scenes in hero sections.
* **Rule**: Render the real interface, actual data tables, terminal command execution, or interactive diff viewers. The product UI is the visual hero.
* **Refactor**:
```tsx
// SLOP
<div className="relative h-96 flex items-center justify-center">
  <div className="size-64 rounded-full bg-gradient-to-tr from-purple-500 to-indigo-500 blur-2xl opacity-40 animate-pulse" />
  <img src="/assets/abstract-3d-cube.png" alt="Hero art" />
</div>

// UNSLOP: Real product surface with actual data
<div className="rounded-xl border border-neutral-200 dark:border-neutral-800 bg-neutral-900 shadow-2xl overflow-hidden">
  <div className="flex items-center gap-2 px-4 py-3 border-b border-neutral-800 bg-neutral-950 text-xs text-neutral-400">
    <span className="size-2 rounded-full bg-emerald-500" />
    <span>cluster-production-01 / logs</span>
  </div>
  <pre className="p-4 text-xs font-mono text-neutral-200 overflow-x-auto">
    <code>{`[2026-11-08T13:12:00Z] Worker initialized (id: wrk_890a)\n[2026-11-08T13:12:01Z] Synchronized 14,200 entities in 48ms`}</code>
  </pre>
</div>
```

---

### 7. Enlarge the Main Feature
* **Slop Pattern**: Splitting the viewport into 6 identical cards, giving equal visual importance to minor settings and core features.
* **Rule**: Identify the primary value driver of the screen and allocate at least 55-60% of the visual space to it. Secondary features are grouped into compact sidebars or nested trays.

---

### 8. Group with Spacing
* **Slop Pattern**: Surrounding every single headline, input, metric, or paragraph in a bordered card container with horizontal divider lines (`<hr className="border-neutral-800" />`).
* **Rule**: Rely on whitespace proximity to establish grouping before adding visual containers or dividers. Elements in the same group use `gap-2` to `gap-4`. Distinct groups use `gap-8` to `gap-16`.

---

### 9. Make Headlines Specific
* **Slop Pattern**: Generic marketing fluff: "Supercharge your productivity with modern intelligence."
* **Rule**: Write functional, verifiable copy explaining what the tool does, for whom, and the concrete outcome.
* **Refactor**:
```tsx
// SLOP
<h2>Supercharge your engineering workflow with next-gen insights</h2>

// UNSLOP
<h2>Identify slow database queries and unindexed foreign keys in pull requests</h2>
```

---

### 10. Emphasize the CTA
* **Slop Pattern**: Three identical filled buttons placed side-by-side, or a primary button that blends into surrounding borders.
* **Rule**: Exactly one primary action per screen context. The primary CTA has the highest contrast (solid dark on light, or solid light on dark). Secondary actions must use outline or ghost variants.
* **Refactor**:
```tsx
// SLOP
<div className="flex gap-4">
  <button className="bg-indigo-600 px-4 py-2 text-white rounded">Get Started</button>
  <button className="bg-purple-600 px-4 py-2 text-white rounded">Live Demo</button>
  <button className="bg-blue-600 px-4 py-2 text-white rounded">Documentation</button>
</div>

// UNSLOP
<div className="flex items-center gap-3">
  <button className="px-4 py-2 rounded-lg bg-neutral-900 text-white dark:bg-white dark:text-neutral-900 font-medium text-sm hover:opacity-90 active:scale-[0.98] transition-all">
    Deploy cluster
  </button>
  <button className="px-4 py-2 rounded-lg border border-neutral-300 dark:border-neutral-700 text-neutral-700 dark:text-neutral-300 font-medium text-sm hover:bg-neutral-100 dark:hover:bg-neutral-800 transition-colors">
    View documentation
  </button>
</div>
```

---

### 11. Add an Intentional Accent Color
* **Slop Pattern**: Either a 100% grayscale interface with zero visual focal points, or a chaotic mix of purple, teal, pink, and yellow badges.
* **Rule**: Ground surfaces in calm neutrals, then apply one deliberate accent color reserved exclusively for interactive focus, selection states, and primary status indicators.

---

### 12. Keep Icons Consistent
* **Slop Pattern**: Mixing 1px stroke icons, 2.5px filled icons, and different icon libraries across the same page.
* **Rule**: Use a single icon library (e.g. Lucide). Stick to one stroke width (`stroke-[1.75px]` or `stroke-2`) and fixed container sizes (`size-4` for inline text, `size-5` for inputs/buttons).
* **Refactor**:
```tsx
// Standardized Icon Component Wrapper
export function Icon({ component: Component, className = "" }: { component: React.ElementType, className?: string }) {
  return <Component className={`size-4 shrink-0 stroke-[1.75px] ${className}`} aria-hidden="true" />;
}
```

---

### 13. Remove Embellishments
* **Slop Pattern**: Adding decorative SVG zigzags, floating blurred circles (`blur-3xl`), dotted background canvases, or glowing card borders.
* **Rule**: Remove all purely decorative background artifacts. Visual elegance comes from typographic hierarchy, layout proportion, and clean content presentation.

---

### 14. Concentric Border Radius
* **Slop Pattern**: Nested containers sharing identical radius classes (e.g., outer card has `rounded-2xl` with `p-4`, and inner child button has `rounded-2xl`), causing warped, pinched corners.
* **Rule**: Apply the concentric radius formula:
  $$\text{inner\_radius} = \text{outer\_radius} - \text{padding}$$
  If $\text{padding} \ge \text{outer\_radius}$, inner elements must have $\text{radius} = 0$ (`rounded-none`).
* **Refactor**:
```tsx
// SLOP (Outer: 16px radius, Padding: 12px, Inner: 16px radius -> Awkward gap)
<div className="rounded-2xl p-3 bg-neutral-100">
  <div className="rounded-2xl bg-white p-4">Content</div>
</div>

// UNSLOP: 16px outer - 12px padding = 4px inner radius
<div className="rounded-[16px] p-3 bg-neutral-100 dark:bg-neutral-900">
  <div className="rounded-[4px] bg-white dark:bg-neutral-950 p-4">Content</div>
</div>
```

---

### 15. Improve Text Contrast
* **Slop Pattern**: Subtitles styled in faint `text-slate-400` on dark backgrounds (`#09090b`), failing WCAG accessibility standards.
* **Rule**:
  * Body text: minimum 7:1 contrast.
  * Secondary / meta text: minimum 4.5:1 contrast (WCAG AA).
  * Never use text opacity lower than `text-neutral-400` on dark or `text-neutral-600` on light backgrounds.

---

### 16. Wrap Headlines Properly
* **Slop Pattern**: Multi-line headers wrapping with a single orphan word on the last line.
* **Rule**: Apply `text-wrap: balance` to all headers (`h1` through `h4`) and short intro paragraphs. Use `text-wrap: pretty` on multi-line body copy to prevent widows.
* **Refactor**:
```tsx
<h1 className="text-3xl sm:text-4xl font-semibold tracking-tight [text-wrap:balance]">
  Continuous delivery pipelines configured directly in your repository
</h1>
```

---

### 17. Align by Eyes, Not Pixels
* **Slop Pattern**: Relying strictly on geometric centering for asymmetrical icons (e.g., a play button triangle centered inside a circle looks pushed to the left).
* **Rule**: Optically adjust asymmetric elements with micro-offsets (`translate-x-0.5`, `ml-0.5`) so they appear centered to the human eye. Align currency symbols and units to the typographic baseline, not the center box.

---

### 18. Use Tabular Numbers
* **Slop Pattern**: Monospace numbers that look clumsy, or proportional numbers that jitter and shift the layout as digits increment.
* **Rule**: Use standard font with `tabular-nums` (`font-variant-numeric: tabular-nums`) on counters, timestamps, price tags, and table columns.
* **Refactor**:
```tsx
<span className="font-sans font-medium text-lg tabular-nums tracking-tight">
  {formatCurrency(balance)}
</span>
```

---

### 19. Add Loading States
* **Slop Pattern**: Empty screens during data fetching that suddenly pop in, causing severe Cumulative Layout Shift (CLS), or submit buttons that don't indicate network activity.
* **Rule**:
  * Always render skeletons with exact dimensions matching the loaded content.
  * Form buttons must show an inline spinner and set `aria-busy="true"` and `disabled` during submission.
* **Refactor**:
```tsx
// Skeleton matching actual card dimensions
export function MetricCardSkeleton() {
  return (
    <div className="p-4 rounded-xl border border-neutral-200 dark:border-neutral-800 animate-pulse">
      <div className="h-4 w-24 bg-neutral-200 dark:bg-neutral-800 rounded" />
      <div className="h-8 w-32 bg-neutral-300 dark:bg-neutral-700 rounded mt-3" />
    </div>
  );
}
```

---

### 20. Animate Useful Feedback
* **Slop Pattern**: Infinite looping floating animations or bouncing entrance transitions on every component on scroll.
* **Rule**: Confine animations strictly to functional state feedback:
  * Interactive transitions: hover, active, and focus (`duration-150 ease-out`).
  * State mutations: toast notification sliding in, checkmark morphing on save, inline expansion/accordion disclosure.
  * Exit animations must be faster than entrance animations (e.g., 100ms exit vs 150ms enter).

---

## Audit & Refactoring Workflow

When asked to review, build, or unslop a UI component:

1. **Scan for Anti-Patterns**: Run through rules 1, 2, 3, 4, 13 (strip vanity badges, redundant labels, random italics, decorative meshes, and inappropriate monospace).
2. **Fix Geometry & Layout**: Run through rules 6, 7, 8, 10, 14 (show real product, enlarge hero feature, group with spacing, establish 1 primary CTA, verify `inner = outer - padding`).
3. **Verify Typography & Palette**: Run through rules 5, 9, 11, 15, 16, 18 (enforce token scale, concrete copy, 1 accent color, WCAG AA contrast, `text-wrap: balance`, `tabular-nums`).
4. **Harden States**: Run through rules 12, 17, 19, 20 (consistent icon family, optical alignment, dimension-preserving loading skeletons, tactile feedback).
