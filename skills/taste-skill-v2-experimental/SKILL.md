---
name: design-taste-frontend-v2-experimental
description: "Architect, style, and validate frontend landing pages, portfolios, editorial layouts, and redesigns using dial-driven parameters, design-system mapping, and anti-slop engineering constraints when explicitly invoked by name, excluding dashboards, dense product UIs, data tables, multi-step wizards, code editors, native mobile apps, and realtime collaborative interfaces."
disable-model-invocation: true
---

# FRONTEND DESIGN TASTE & ANTI-SLOP SPECIFICATION

## BRIEF INFERENCE, SCOPE BOUNDARIES & CONFLICT HIERARCHY

### Scope Boundaries & Out-of-Scope Routing
* Apply this specification exclusively to landing pages, portfolios, editorial/blog layouts, marketing surfaces, and frontend redesigns, pulling only rules that match the inferred project context.
* Route out-of-scope interface classes to their dedicated domain frameworks, declare the scope boundary explicitly to the user, and restrict application of this specification to accompanying marketing, about, or landing surfaces:
  * **Dashboards / dense product UI / admin panels** ➔ Use `@fluentui/react-components`, `@carbon/react`, `@atlaskit/*`, or Shopify Polaris.
  * **Data tables** ➔ Use TanStack Table or AG Grid.
  * **Multi-step forms / wizards** ➔ Use dedicated form-state and wizard architecture patterns.
  * **Code editors** ➔ Use Monaco or CodeMirror with official skinning tokens.
  * **Native mobile applications** ➔ Use Apple Human Interface Guidelines (HIG) or Material Design native SDKs directly.
  * **Realtime collaborative UIs (presence, cursors, OT-aware surfaces)** ➔ Use dedicated multiplayer synchronization UI patterns.

### Input Signal Extraction
1. **Identify the page kind**: Categorize the target surface as landing page (SaaS / consumer / agency / event), portfolio (developer / designer / creative studio), redesign (preserve vs. overhaul), or editorial / blog.
2. **Extract lexical vibe signals**: Parse explicit aesthetic descriptors from the prompt (`"minimalist"`, `"calm"`, `"Linear-style"`, `"Awwwards"`, `"brutalist"`, `"premium consumer"`, `"Apple-y"`, `"playful"`, `"serious B2B"`, `"editorial"`, `"agency-y"`, `"glassy"`, `"dark tech"`).
3. **Parse reference signals**: Analyze linked URLs, pasted screenshots, named benchmark products, and competing brands.
4. **Determine the target audience**: Match the visual language to the evaluator profile (B2B procurement panel, design-conscious consumer, or recruiter scanning a portfolio) rather than generic aesthetic preferences.
5. **Inventory existing brand assets**: Extract existing logos, color tokens, typography stacks, and photography as foundational starting material for redesigns.
6. **Enforce quiet constraints**: Prioritize accessibility-first audiences, public-sector mandates, regulated industries, trust-first commerce, and kids' products over stylistic experimentation.

### Pre-Generation Design Read & Disambiguation Protocol
* Output a single-line declaration before generating any code using the exact template:
  **"Reading this as: \<page kind> for \<audience>, with a \<vibe> language, leaning toward \<design system or aesthetic family>."**
  * *Reference Benchmark 1:* *"Reading this as: B2B SaaS landing for technical buyers, with a Linear-style minimalist language, leaning toward Tailwind utilities + Geist + restrained motion."*
  * *Reference Benchmark 2:* *"Reading this as: solo designer portfolio for hiring managers, with an editorial / kinetic-type language, leaning toward native CSS + scroll-driven animation + custom typography."*
  * *Reference Benchmark 3:* *"Reading this as: redesign of a public-sector service site, with a trust-first language, leaning toward GOV.UK Frontend or USWDS."*
* Proceed directly with the declared design read when context supports confident inference; if the brief genuinely diverges between incompatible directions, pause and ask exactly **one** clarifying question (e.g., *"Should this feel closer to Linear-clean or Awwwards-experimental?"*), excluding multi-question prompts.
* Select deliberate aesthetic configurations anchored to the design read, excluding unprompted LLM default patterns: AI-purple gradients, centered hero copy over dark mesh backgrounds, three equal horizontal feature cards, ubiquitous glassmorphism, continuous infinite-loop micro-animations across static sections, and default `Inter` + `slate-900` pairings.

### Conflict Resolution Hierarchy
* Resolve competing directives across the specification in the following strictly descending priority order:
  1. **Scope Boundary Exclusions**: Route dashboards, data tables, wizards, code editors, native mobile, and realtime collab UIs to their dedicated frameworks.
  2. **Quiet Constraints & Redesign Preservation Locks**: Enforce public-sector/regulatory compliance, WCAG AA/AAA accessibility, and existing URL slugs, navigation labels, form field names, brand marks, and legal copy in redesigns.
  3. **Explicit Brand & User Brief Overrides**: Honor explicitly requested fonts (e.g., `Inter` or a named serif), brand colors (e.g., purple/violet or heritage craft palettes), or single-mode theme mandates.
  4. **Performance, Accessibility & Viewport Guardrails**: Enforce `prefers-reduced-motion`, `prefers-reduced-transparency`, Core Web Vitals (`LCP < 2.5s`, `INP < 200ms`, `CLS < 0.1`), and single-viewport hero fit.
  5. **Contextual Dial Inference & Bias-Correction Directives**: Apply brief-derived dial settings and anti-slop rules over baseline defaults.
  6. **Baseline Configuration**: Apply the default `8 / 6 / 4` dial configuration when no higher-priority signal overrides it.

## DIAL CONFIGURATION & TECHNICAL SCALE MATRIX

### Global Dial Variables
* Set three global configuration variables immediately after the design read to gate layout, motion, and density decisions, using the baseline `8 / 6 / 4` unless overridden by brief inference or conversational user instruction:
  * **`DESIGN_VARIANCE: 8`** - Scale `1` (Perfect Symmetry) to `10` (Artsy Chaos).
  * **`MOTION_INTENSITY: 6`** - Scale `1` (Static) to `10` (Cinematic / Physics).
  * **`VISUAL_DENSITY: 4`** - Scale `1` (Art Gallery / Airy) to `10` (Cockpit / Packed Data).
* Reference the exact variable identifiers `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY` throughout all architectural decisions, excluding invented aliases such as `LAYOUT_VARIANCE` or `ANIM_LEVEL`.

### Dial Inference Matrix
| Signal | DESIGN_VARIANCE | MOTION_INTENSITY | VISUAL_DENSITY |
|---|---|---|---|
| "minimalist / clean / calm / editorial / Linear-style" | 5-6 | 3-4 | 2-3 |
| "premium consumer / Apple-y / luxury / brand" | 7-8 | 5-7 | 3-4 |
| "playful / wild / Dribbble / Awwwards / experimental / agency" | 9-10 | 8-10 | 3-4 |
| "landing page / portfolio / marketing site (default)" | 7-9 | 6-8 | 3-5 |
| "trust-first / public-sector / regulated / accessibility-critical" | 3-4 | 2-3 | 4-5 |
| "redesign - preserve" | match existing | +1 | match existing |
| "redesign - overhaul" | +2 | +2 | match existing |

### Use-Case Presets Matrix
| Use Case | DESIGN_VARIANCE | MOTION_INTENSITY | VISUAL_DENSITY |
|---|---|---|---|
| Landing (SaaS, mainstream) | 7 | 6 | 4 |
| Landing (Agency / creative) | 9 | 8 | 3 |
| Landing (Premium consumer) | 7 | 6 | 3 |
| Portfolio (Designer / studio) | 8 | 7 | 3 |
| Portfolio (Developer) | 6 | 5 | 4 |
| Editorial / Blog | 6 | 4 | 3 |
| Public-sector service | 3 | 2 | 5 |
| Redesign - preserve | match | match+1 | match |
| Redesign - overhaul | +2 | +2 | match |

### Technical Scale Definitions
| Dial Variable | Level 1-3 | Level 4-7 | Level 8-10 | Viewport & Hardware Rules |
|---|---|---|---|---|
| **DESIGN_VARIANCE** | **Predictable:** Symmetrical 12-col CSS Grid with equal `fr` units, uniform padding, centered alignment. | **Offset:** `margin-top: -2rem` overlaps, mixed image aspect ratios (`4:3` adjacent to `16:9`), left-aligned headers above center-aligned data. | **Asymmetric:** Masonry layouts, fractional CSS Grid (`grid-template-columns: 2fr 1fr 1fr`), expansive negative space (`padding-left: 20vw`). | **Mobile Override:** Collapse all asymmetric layouts (`DESIGN_VARIANCE` 4-10) above `md:` to strict single-column (`w-full`, `px-4`, `py-8`) on viewports `< 768px`. |
| **MOTION_INTENSITY** | **Static:** CSS `:hover` and `:active` states only; zero automatic animations; `prefers-reduced-motion` behavior by default. | **Fluid CSS:** Explicit property transitions `transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.3s cubic-bezier(0.16, 1, 0.3, 1)` and `animation-delay` load-in cascades. | **Advanced Choreography:** Scroll-triggered reveals, parallax, CSS `animation-timeline`, GSAP `ScrollTrigger`, and Motion hooks. | **Execution Constraint:** Map `transition: all` ➔ explicit `transform` and `opacity` transitions; exclude `window.addEventListener('scroll')` across all levels. |
| **VISUAL_DENSITY** | **Art Gallery:** Generous whitespace with wide section gaps (`py-32` to `py-48`). | **Daily App:** Standard web application vertical spacing (`py-16` to `py-24`). | **Cockpit:** Compact paddings, `1px` structural dividing lines without card boxes, and mandatory `font-mono` for all numeric values. | **Container Rule:** Omit generic card containers when `VISUAL_DENSITY > 7`. |

## DESIGN SYSTEM MAPPING & ARCHITECTURE CONVENTIONS

### Official Design System Selection Matrix
* Install and use the official package when the brief aligns with an established design system, preserving at least 90% of its native token architecture and locking **one design system per project** (excluding cross-system mixing such as Fluent React with Carbon or shadcn/ui inside Material 3):

| Brief Reads As | Official Package / Foundation | Architectural Rationale |
|---|---|---|
| Microsoft / enterprise SaaS / dashboards | `@fluentui/react-components` or `@fluentui/web-components` | Official Fluent UI, Microsoft tokens, built-in accessibility |
| Google-ish UI, Material-flavored product | `@material/web` + Material 3 tokens | Official Material 3 web components, themeable via Material Theming |
| IBM-style B2B / enterprise analytics | `@carbon/react` + `@carbon/styles` | Official Carbon system, mature high-density data patterns |
| Shopify app surfaces | `polaris.js` web components / Polaris React | Required standard for Shopify admin interfaces |
| Atlassian / Jira-style product | `@atlaskit/*` + `@atlaskit/tokens` | Official Atlassian Design System |
| GitHub-style devtool / community page | `@primer/css` or `@primer/react-brand` | Official Primer; Brand variant tailored for marketing surfaces |
| Public-sector UK service | `govuk-frontend` | Legally and regulatorily mandated service standard |
| US public-sector / trust-first | `uswds` | Official US Web Design System for federal/public trust |
| Fast local-business / agency MVP | Bootstrap 5.3 | Rapid, predictable standard grid and component baseline |
| Modern accessible React foundation | `@radix-ui/themes` | Accessible primitives paired with a cohesive theme layer |
| Modern SaaS where you own the components | shadcn/ui (`npx shadcn@latest add ...`) | Owned component source; customize radii, colors, shadows, and type beyond default state |
| Tailwind-based modern SaaS / AI marketing | Tailwind v4 utilities + `dark:` variant | Default utility foundation for independent and small-team builds |

### Aesthetic-to-Implementation Mapping Matrix
* Construct aesthetic-driven briefs using native CSS, Tailwind utilities, and maintained component primitives, labeling approximations honestly in code comments rather than fabricating non-existent official packages:

| Aesthetic Direction | Technical Implementation Strategy |
|---|---|
| Glassmorphism / "frosted glass" | Layer `backdrop-filter`, `1px` translucent borders, and highlight overlays with a solid-fill fallback under `@media (prefers-reduced-transparency: reduce)`. |
| Bento (Apple-style tile grids) | Compose with native CSS Grid using mixed fractional/span cell sizes. |
| Brutalism | Style with native CSS, monospace typography, and exposed raw borders. |
| Editorial / magazine | Combine justified serif display typography, asymmetric column grids, and generous whitespace. |
| Dark tech / hacker | Pair monospace typography with high-contrast neon accents and terminal motifs. |
| Aurora / mesh gradients | Render via SVG filters or layered CSS radial gradients. |
| Kinetic typography | Drive with native CSS animations, CSS scroll-driven animations (`animation-timeline: view()`), or isolated GSAP `ScrollTrigger` leaves. |
| **Apple Liquid Glass** | Implement as a labeled web frosted-glass approximation using `backdrop-filter`, layered borders, and specular highlights, noting that Apple documents native Liquid Glass exclusively for Apple platform APIs (no official `liquid-glass.css` exists). |

### Default Framework, Styling, State & Asset Stack
* **Framework & Component Isolation**:
  * Build with React or Next.js defaulting to React Server Components (RSC) for static layouts.
  * Wrap global state providers in a dedicated `"use client"` component.
  * Isolate any component using Motion, scroll listeners, or pointer physics into a memoized leaf component with `'use client'` at the top of the file.
* **Styling Engine**:
  * Use **Tailwind v4** by default via `@tailwindcss/postcss` or the Vite plugin, excluding the legacy `tailwindcss` plugin in `postcss.config.js` (use Tailwind v3 only when required by an existing repository).
* **Animation Import & Continuous State**:
  * Import Motion primitives from `motion/react` (`import { motion } from "motion/react"`), treating `framer-motion` solely as a legacy alias.
  * Manage isolated local UI state with `useState` or `useReducer` and deep prop-drilling state with Zustand, Jotai, or React Context.
  * Drive continuous user-input values (mouse coordinates, scroll progress, pointer physics, magnetic hover) exclusively via Motion's `useMotionValue`, `useTransform`, and `useScroll` hooks outside the React render cycle, excluding `useState` to prevent per-frame React tree re-renders and mobile frame drops.
* **Font Loading**:
  * Load fonts via `next/font` (Next.js) or self-hosted `@font-face` declarations with `font-display: swap`, excluding external Google Fonts `<link>` tags in production markup.
* **Dependency Verification**:
  * Inspect `package.json` prior to importing any third-party package and output the required installation command first if the dependency is absent.
* **Icons & Emoji Policy**:
  * Select icons from `@phosphor-icons/react`, `hugeicons-react`, `@radix-ui/react-icons`, or `@tabler/icons-react` (permitting `lucide-react` only when explicitly requested by the user or pre-installed in the project).
  * Lock **one icon family per project** with a globally standardized `strokeWidth` (e.g., `1.5` or `2.0`), and compose missing glyphs from library primitives rather than hand-rolling raw SVG path data.
  * Replace symbolic text markers with icon-library glyphs, permitting emojis sparingly only when the brief explicitly specifies a playful, chat-style, or social-native interface.

## DESIGN ENGINEERING DIRECTIVES & BIAS CALIBRATION

### Typography & Font Pairing Calibration
* **Scale & Measure Defaults**:
  * Configure display and headline elements at `text-4xl md:text-6xl tracking-tighter leading-none` (adjusting hero scale per viewport rules below), controlling hierarchy through font weight and color contrast rather than oversized raw scale.
  * Configure body copy at `text-base text-gray-600 leading-relaxed max-w-[65ch]`.
* **Sans-Serif Default & Pairings**:
  * Select `Geist`, `Outfit`, `Cabinet Grotesk`, `Satoshi`, `Geist Display`, `ABC Diatype`, `Söhne Breit`, `Cabinet Grotesk Display`, `Migra Sans`, `GT Walsheim`, `Inter Display`, or `PP Neue Montreal` as default sans-serif families, reserving `Inter` exclusively for explicit Linear-style, neutral-standard, public-sector, or accessibility-first briefs:
    * `Inter` (unprompted default) ➔ `Geist` / `Outfit` / `Cabinet Grotesk` / `Satoshi`
  * Apply proven technical pairings: `Geist` + `Geist Mono`, `Satoshi` + `JetBrains Mono`, `Cabinet Grotesk` + `Inter Tight`, or `GT America` + `IBM Plex Mono`.
* **Serif Discipline & Rotation Pool**:
  * Default to sans-serif display typography across creative agency, design studio, modern brand, premium consumer, portfolio, and lifestyle briefs.
  * Restrict serif typography to briefs that explicitly name a serif font OR belong to an authentic editorial, luxury, publication, manuscript, heritage, or vintage family with an articulable brand rationale (excluding dashboards and generic "creative" assumptions).
  * Rotate justified serif selections across consecutive projects from the approved pool, excluding LLM-default display serifs `Fraunces` and `Instrument_Serif`:
    * `Fraunces` / `Instrument_Serif` ➔ `PP Editorial New`, `GT Sectra Display`, `Cardinal Grotesque`, `Reckless Neue`, `Tiempos Headline`, `Recoleta`, `Cormorant Garamond`, `Playfair Display`, `EB Garamond`, `IvyPresto`, `Migra`, `Editorial Old`, `Saol Display`, `Söhne Breit Kursiv`, `Domaine Display`, `Canela`, `Schnyder`, `Tobias`, `NB Architekt`, `ITC Galliard`
* **Single-Family Headline Emphasis & Italic Descender Clearance**:
  * Emphasize target words within a headline using italic or bold weights of the **same font family**, excluding mixed-family serif-into-sans (or sans-into-serif) word injections.
  * Apply a minimum line-height of `leading-[1.1]` and bottom padding/margin reserve (`pb-1` or `mb-1`) on the wrapping element whenever an italic display word contains a descender character (`y`, `g`, `j`, `p`, `q`), replacing `leading-[1]` or `leading-none` to prevent descender clipping.

### Color Calibration & Palette Locks
* **Accent Cap & Neutral Foundation**:
  * Restrict each project to a maximum of **1 accent color** with default saturation `< 80%` over a unified neutral base (Zinc, Slate, or Stone, maintaining a single warm or cool gray family across the entire project) paired with a high-contrast singular accent (Emerald, Electric Blue, Deep Rose, Burnt Orange).
  * Lock the chosen accent color across every section of the page (nav, hero, interactive states, badges, footer), excluding mid-page accent shifts.
  * Use off-black (`zinc-950` or near-black warm gray) and off-white surfaces, excluding pure black (`#000000`), pure white (`#ffffff`), oversaturated accents, excessive gradient header text, and unprompted neon outer glows (**The Lila Rule**; embrace purple/violet/lila with harmonized neutrals and restrained gradients only when explicitly requested by the brand or brief).
* **Premium-Consumer Palette Rotation**:
  * Select distinct color families for premium-consumer briefs (cookware, wellness, artisan, luxury, heritage craft, DTC home goods) and rotate families across consecutive projects, excluding the default warm beige/cream + brass/clay/oxblood/ochre + espresso palette unless explicitly named in the brand brief:
    * Default Warm-Craft Backgrounds (`#f5f1ea`, `#f7f5f1`, `#fbf8f1`, `#efeae0`, `#ece6db`, `#faf7f1`, `#e8dfcb`), Accents (`#b08947`, `#b6553a`, `#9a2436`, `#9c6e2a`, `#bc7c3a`, `#7d5621`), and Espresso Text (`#1a1714`, `#1a1814`, `#1b1814`) ➔
      1. **Cold Luxury**: Silver-grey + chrome + smoke.
      2. **Forest**: Deep green + bone + amber accent.
      3. **Black and Tan**: True off-black + warm tan with sharp contrast.
      4. **Cobalt + Cream**: Saturated blue against a single neutral without brass.
      5. **Terracotta + Slate**: Warm rust against cool grey without brass.
      6. **Olive + Brick + Paper**: Muted olive paired with brick-red accent.
      7. **Pure Monochrome + Single Saturated Pop**: Off-white + off-black + one bright accent (electric blue, emerald, or hot pink).

### Theme Lock & Dual-Mode Token Protocol
* **Page-Level Theme Lock**:
  * Lock a single theme mode (light, dark, or system `prefers-color-scheme`) at the page root (`layout.tsx` or root wrapper), keeping all sections within the same theme family (e.g., `bg-zinc-950` adjacent to `bg-zinc-900`) and excluding mid-page inversions (such as a light warm-paper section sandwiched between dark sections), unless the brief explicitly specifies a single deliberate "Color Block Story" or "Theme Switch on Scroll" transition.
* **Dual-Mode Token Strategy**:
  * Design consumer-facing pages for both light and dark modes from the start (unless the brief explicitly mandates a single mode or print-emulating editorial sheet), selecting and locking one token strategy per project:
    1. **Tailwind `dark:` Variant**: Pair every surface and text utility with its dark counterpart (`bg-white dark:bg-zinc-950`, `text-gray-900 dark:text-gray-100`).
    2. **CSS Custom Properties**: Define semantic tokens (`--surface`, `--surface-elevated`, `--text-primary`, `--accent`) and swap values under `[data-theme="dark"]` or `@media (prefers-color-scheme: dark)`.
  * Preserve brand color recognition, visual hierarchy parity, and WCAG AA contrast (4.5:1 minimum for body text, AAA target for hero copy) across both modes, verifying the rendered page in both light and dark modes before completion.

### Materiality, Shadows, Cards & Interactive States
* **Elevation & Shape Consistency Lock**:
  * Group related content using `border-t`, `divide-y`, or negative space, reserving card containers strictly for components where elevation communicates structural hierarchy (and omitting cards entirely when `VISUAL_DENSITY > 7`).
  * Tint drop shadows to match the underlying background hue rather than using pure-black shadows on light surfaces.
  * Lock **one corner-radius system** across the entire page: all-sharp (`0px`), all-soft (`12px-16px`), all-pill (`9999px` for interactive elements), or an explicitly documented mixed hierarchy (e.g., full-pill buttons, `16px` cards, `8px` inputs) applied uniformly.
* **Interactive UI Cycles, Contrast & Form Ergonomics**:
  * Implement complete UI state cycles: layout-matched skeletal loaders (excluding generic circular spinners), instructional empty states, and inline form error states (reserving toasts for transient events).
  * Apply physical push feedback on `:active` states using `-translate-y-[1px]` or `scale-[0.98]` while preserving default system cursors (excluding custom mouse cursors).
  * Enforce WCAG AA contrast (`4.5:1` for normal text, `3:1` for large text `18px+`) on all buttons (adding a backdrop, scrim, or border stroke to ghost buttons over photography, excluding low-contrast combinations such as `bg-white` + `text-white`).
  * Render primary CTA labels in 1-3 words (ideally 1-2 words) without artificial `max-width` constraints so button text fits on a **single line at desktop**, excluding multi-line wrapped CTAs.
  * Unify CTA labels by intent across the entire page (nav, hero, sections, footer) so each intent maps to **one exact string**:
    * **Contact intent** (`"Get in touch"`, `"Contact us"`, `"Let's talk"`, `"Start a project"`, `"Start something"`, `"Reach out"`) ➔ Select and lock 1 label page-wide.
    * **Signup intent** (`"Try free"`, `"Get started"`, `"Sign up free"`) ➔ Select and lock 1 label page-wide.
    * **Portfolio intent** (`"View work"`, `"See selected work"`, `"Browse projects"`) ➔ Select and lock 1 label page-wide.
  * Structure form input blocks with `gap-2`, placing the `<label>` above the input, optional helper text in markup, and error text below the input, ensuring all inputs, placeholders, focus rings, labels, and errors pass WCAG AA (`4.5:1`) contrast against the section background (excluding placeholder-as-label patterns).

### Layout Mechanics, Viewport & Grid Discipline
* **Viewport & Grid Foundations**:
  * Standardize responsive breakpoints (`sm: 640px`, `md: 768px`, `lg: 1024px`, `xl: 1280px`, `2xl: 1536px`) and constrain page containers with `max-w-[1400px] mx-auto` or `max-w-7xl`.
  * Declare explicit `< 768px` mobile collapse rules inside every multi-column component.
  * Size full-height hero containers with `min-h-[100dvh]` and construct multi-column layouts with CSS Grid:
    * `h-screen` ➔ `min-h-[100dvh]`
    * `w-[calc(33%-1rem)]` ➔ `grid grid-cols-1 md:grid-cols-3 gap-6`
* **Hero Composition & Stack Cap**:
  * Use split-screen (`50/50`), left-aligned copy with right-aligned asset, asymmetric whitespace, or scroll-pinned structures when `DESIGN_VARIANCE > 4`, reserving centered hero layouts strictly for editorial, manifesto, or launch-announcement briefs.
  * Fit the entire hero within the initial desktop viewport without scrolling: cap top padding at `pt-24` (`≈ 6rem`), cap the headline at **2 lines max** (using `text-4xl md:text-5xl lg:text-6xl` by default, or `text-6xl md:text-7xl` only when the headline is 3-5 words, excluding `text-7xl`/`text-8xl` on headlines > 6 words), cap subtext at **20 words max AND 3-4 lines max**, and keep CTAs visible above the fold.
  * Restrict the hero stack to a **maximum of 4 text elements**:
    1. Eyebrow (small uppercase label) OR brand strip OR neither (select 0 or 1).
    2. Headline (max 2 lines).
    3. Subtext (max 20 words, max 4 lines).
    4. CTAs (1 primary + max 1 secondary).
  * Place trust logo walls, compatibility notes, pricing teasers, feature bullet lists, and social-proof avatar rows in dedicated sections below the hero, excluding tiny taglines below hero CTAs or inline hero logo strips.
* **Navigation Bar Constraints**:
  * Render desktop navigation on a **single line** at `lg` (`1024px`) with a height cap of **80px maximum** (defaulting to `64px-72px`), condensing labels or moving secondary items to a menu trigger when horizontal space is constrained.
* **Section Rhythm, Bento Diversity & Eyebrow Cap**:
  * Use each section layout family (e.g., 3-column image cards, full-width quote, split text-image) **at most once per page**, incorporating at least **4 distinct layout families across an 8-section page** and replacing generic 3-equal-column feature rows with 2-column zig-zags, asymmetric grids, sticky stacks, or horizontal scroll tracks.
  * Cap consecutive image+text split sections (left-image/right-text alternating with left-text/right-image) at **2 sections in a row maximum**, breaking the sequence before a 3rd split section with a full-width block, vertical stack, bento grid, or marquee.
  * Match bento grid cell counts exactly to the item count ($N$ content items ➔ $N$ grid cells: 3 items as `1+2`, `2+1`, or asymmetric trio; 5 items as `2+3`, `3+2`, or `hero+4`, excluding empty filler tiles), vary row compositions, and apply visual background variation (real photography, brand-appropriate non-purple gradient, pattern, or surface tint) to at least **2-3 cells** in any multi-cell grid.
  * Stack section headers vertically (headline on top, optional body paragraph below constrained to `max-w-[65ch]`), excluding default split-headers (left `col-span-7`/`8` headline paired with a floating right `col-span-4`/`5` explainer paragraph) unless the right column houses an interactive or visual asset.
  * Ration section eyebrows (`text-[11px] uppercase tracking-[0.18em]` or `font-mono text-[10.5px] uppercase tracking-[0.22em]`) to a **maximum of 1 eyebrow per 3 sections** (`eyebrowCount <= ceil(sectionCount / 3)`, counting the hero as 1 section); omit eyebrows on the 2 sections immediately following any section with an eyebrow.

### Visual Asset, Icon & Logo Architecture
* **Visual Asset Priority Cascade**:
  * Populate every landing page and portfolio—including restrained minimalist or editorial builds—with at least **2-3 real visual assets** (hero visual, product/lifestyle shot, supporting visual) following this strict priority order:
    1. **Environment Image-Generation Tool**: Invoke available image generation tools (`generate_image`, MCP image tool, IDE-integrated generator, or OpenAI image tool) at the target container aspect ratio to synthesize custom hero photography, product shots, texture backgrounds, and mood imagery (generating B&W photography for minimalist briefs).
    2. **Real Web Photography**: Reference real brand assets, licensed stock URLs (Unsplash direct URLs, Pexels), or seeded placeholder photography via `https://picsum.photos/seed/{descriptive-seed}/{w}/{h}` (e.g., `https://picsum.photos/seed/marrow-cookware-kitchen/1600/1200`).
    3. **Explicit Placeholder Slots**: When image generation and external image URLs are unavailable, insert HTML comment slots (`<!-- TODO: hero product photo, 1600x1200 -->`) and append the exact notice at the end of the response: *"This page needs real images at: [list of placements]. Please generate or provide them."*
  * Showcase product interfaces using real screenshot URLs, generated imagery, or live interactive mini-components, excluding div-based fake screenshots (simulated task lists, fake terminals, or `<div>` rectangle dashboards) and unprompted hand-rolled decorative SVG illustrations.
* **Social-Proof Logo Wall Protocol**:
  * Place the "Trusted by / Used at / Customers include" logo wall in a dedicated section directly **below the hero**.
  * Render real SVG brand marks via **Simple Icons** (`https://cdn.simpleicons.org/{slug}/ffffff` or `simple-icons` npm package), **devicon** (`@svgr/cli` or CDN), or custom inline `<svg>` geometric monograms/ligatures for invented brands, ensuring visibility across light and dark modes.
  * Display **logos only** inside the logo wall (with accessible `alt` text and optional brand links), excluding plain-text wordmark `<span>` rows and excluding industry/category sub-labels beneath logos (such as `Vercel` + `hosting`, `Stripe` + `payments`, or `Cloudflare` + `infra`).

## CONTENT DENSITY, COPY HYGIENE & TYPOGRAPHIC SANITIZATION

### Section Density & Long-List Component Routing
* **Section Copy Budget**:
  * Structure standard sections around a short headline (**≤ 8 words**), a concise sub-paragraph (**≤ 25 words**), and either **1 visual asset OR 1 CTA**.
  * Condense large datasets (such as 20-row publication tables, 30-row award lists, or exhaustive pricing matrices) into the **top 3-5 highlights** paired with a `"View full list"` link, a horizontal carousel/marquee, or a dedicated secondary route.
* **List & Specification Table Component Alternatives**:
  * Route any collection exceeding **5 items** or any product specification sheet (for cookware, hardware, apparel, or artisan goods) away from plain `<ul>` bullet lists and multi-row hairline tables (`border-t` + `border-b` on every row) into one of four structured UI patterns:
    1. **2-Column Spec Card Grid**: Render each specification in an individual card (2 columns on desktop, 1 column on mobile) containing the spec label, a large display value, and a 1-line functional explanation.
    2. **Horizontal Scroll-Snap Pills**: Place each item or specification inside a horizontally flickable scroll-snap pill track.
    3. **Grouped Logical Clusters**: Partition 10+ specifications into 3 logical clusters (e.g., `"Materials"`, `"Cooking"`, `"Warranty"`), separating clusters with a single soft divider per group rather than per-row hairlines.
    4. **Featured Tiles + Disclosure**: Visualize 3-4 hero specifications as large display tiles and collapse remaining specifications inside a `"View full specifications"` disclosure/accordion or tabbed container.
  * Represent quantitative comparisons ("X out of Y") using numeric typography paired with an icon or an un-tracked inline bar, excluding dashboard-style progress bars with filled background tracks (`bg-zinc-200`).

### Quotes & Testimonials Formatting
* **Quote Constraints**:
  * Trim testimonial and quote bodies to a **maximum of 3 lines** so the quote reads in a single glance.
  * Format attribution with `Name + Role + (optional) Company` separated by a line break or a spaced regular hyphen (` - `), excluding first-name-only attributions (`"- Sarah"`).
  * Wrap quotes in true typographic quotation marks (`“` and `”`) or omit quotation marks entirely, excluding straight ASCII quotes (`"`).

### Copy Self-Audit, Data Realism & Em-Dash Elimination
* **Mandatory Pre-Ship Copy Audit**:
  * Audit every visible text string across headlines, subheads, eyebrows, buttons, body copy, captions, `alt` attributes, footers, and error messages prior to delivery; rewrite any string exhibiting grammatical defects (e.g., `"free on its past"`, `"two plans but one is honest"`, `"to put it on the table"`), ambiguous referents (`"we plan to stay that way"`), forced metaphors, or performative mock-humility (`"We respect the French ones"`) into direct, functional prose.
  * Maintain **one consistent copy register** across the entire page, excluding mixtures of technical telemetry mono (`"47 tasks · 0.6 ctx-switches/day"`), poetic editorial prose, and promotional punchlines unless mandated by brand guidelines.
* **Data Realism & Metric Grounding**:
  * Populate mock interfaces and examples with contextually realistic, locale-appropriate names, photographic avatars, contextual brand names, concrete action verbs, and organic numbers, while grounding any specific product performance metrics (`92%`, `4.1×`, `48k`, `5.8 mm`, `13.4 lb`) strictly in brief data or labeling them explicitly as mock (`<!-- mock -->`, `"example"`, `"sample data"`):
    * Generic Names (`"John Doe"`, `"Sarah Chan"`, `"Jack Su"`) ➔ Contextually realistic, locale-appropriate full names
    * Generic Avatars (SVG `"egg"` or Lucide user icons) ➔ Seeded photographic placeholders or styled monogram marks
    * Fake-Perfect Numbers (`99.99%`, `50%`, `1234567`) ➔ Organic, realistic data (`47.2%`, `+1 (312) 847-1928`)
    * Startup-Slop Brand Names (`"Acme"`, `"Nexus"`, `"SmartFlow"`, `"Cloudly"`) ➔ Context-specific, domain-credible brand names
    * Filler Marketing Verbs (`"Elevate"`, `"Seamless"`, `"Unleash"`, `"Next-Gen"`, `"Revolutionize"`) ➔ Concrete operational verbs
* **Complete Em-Dash & En-Dash Elimination**:
  * Eliminate the em-dash (`—`) and separator en-dash (`–`) across **100% of visible strings** (headlines, eyebrows, pills, body copy, quotes, attributions, captions, buttons, navigation, and `alt` text), using only the standard ASCII hyphen (`-`) for compound words, date/number ranges (`2018-2026`, `€40-80k`), and spaced attribution separators (` - `), or the mathematical minus sign (`-5°C`):
    * `—` (em-dash) / `–` (en-dash in ranges/separators) ➔ `.` (period) / `,` (comma) / `:` (colon) / `()` (parentheses) / `-` (standard hyphen)

### Production-Test AI Tell Replacements
* Replace recurring LLM decorative clichés with clean, functional structural patterns across all sections:

| Category | Excluded AI-Tell Pattern (Source) | Standardized Target Pattern (Target) |
|---|---|---|
| **Hero Eyebrows & Sub-Meta** | Unprompted version badges (`V0.6`, `v2.0`, `BETA`, `INVITE-ONLY PREVIEW`, `EARLY ACCESS`, `ALPHA`) or catalog sub-eyebrows (`"Marrow · No. 01 · The 6-quart"`) | Plain topical eyebrow (only on launch briefs for version tags) or direct headline without sub-meta |
| **Hero Bottom & Scroll Cues** | Bottom mono-caps strips (`BRAND. MOTION. SPATIAL.`, `TYPE / FORM / MOTION`, `DESIGN · BUILD · SHIP`, `ESTD. 2018 · LISBON · BRAND. MOTION. SPATIAL.`) and scroll prompts (`Scroll`, `↓ scroll`, `Scroll to explore`, `Scroll to walk through it`, mouse-wheel icons) | Clean hero bottom edge (unless housing real sticky nav links or legal/cookie notices) without scroll labels |
| **Section Eyebrows & Pagination** | Enumerated eyebrows (`00 / INDEX`, `001 · Capabilities`, `002 · Featured commission`, `06 · how it works`, `05 · The honest table`), date-range eyebrows (`"Index of Work, 2018 - 2026"`), and tile counters (`01 / 4`, `Scroll · 001 Capabilities`) | Plain-language topical heading (or zero eyebrow per the `ceil(sectionCount / 3)` cap) without tile pagination counters |
| **Separators & Status Dots** | Chained middle-dots (`"foo · bar · baz · qux · quux"`) and decorative colored status dots before nav links, list rows, or badges (`"ONE Q4 SLOT OPEN"`) | Line breaks, structural columns, or hairlines (rationing `·` to **max 1 per metadata line**), reserving status dots strictly for live semantic state (max 1 per section) |
| **Typographic & Grid Flourishes** | Default `<br>`-broken-and-italicized headlines (`"for thirty<br><i>years.</i>"`), `90°` vertical rotated text (`"INDEX OF WORK, 2018 - 2026"`), and decorative crosshair/hairline grids | Natural-flow headlines (using rotated text only on experimental/agency briefs with compositional purpose) and functional content dividers |
| **Social-Proof & Section Labels** | Performative headers (`"Quietly in use at"`, `"Quietly trusted by"`, `"From the field"`, `"Field notes"`, `"Currently on the bench"`, `"On our desks"`, `"Loose plates"`) and micro-meta disclaimers under headings (*"Each of these is a feature we ship today..."*) | Direct functional labels (`"Trusted by"`, `"Used at"`, `"Customers include"`, `"Testimonials"`, `"Latest writing"`, `"Now working on"`) or unlabelled self-evident sections |
| **Process Step Labels** | Generic numbered prefixes (`"Stage 1 / Stage 2 / Stage 3"`, `"Step 1 / Step 2 / Step 3"`, `"Phase 01 / Phase 02 / Phase 03"`, `"Pass One / Pass Two / Pass Three"`) | Direct verb-noun action labels (`"Install"`, `"Configure"`, `"Ship"`) |
| **Image Overlays & Captions** | Overlaid photo tags (`<span>` pills with `Brand · 02`, `PLATE · BRAND`, `Field notes - journal`) and fictional archive credits (`Field study no. 12 · Ines Caetano`, `Plate 03 · House archive`, `Frame XII · 35mm`) | Unobstructed imagery with optional plain functional captions placed outside and below the image (`"The 6-quart, in Sage."`), crediting only real photographers with permission |
| **Footers, Counters & Locale Strips** | Devtool version footers (`v1.4.2`, `Build 0048`, `last sync 4s ago · main`), fake stock counters (`"Reservation 412 of 800"`), and atmospheric locale/weather strips (`"Lisbon, working with founders"`, `"1200-690 Lisbon, Portugal"`, `"LIS 14:23 · 18°C"`) | Standard marketing footer links (reserving stock counters for real waitlist briefs and time/locale strips for globally distributed studios, travel brands, or physical venues) |

## MOTION CHOREOGRAPHY, INTERACTION PHYSICS & CANONICAL SKELETONS

### Context-Gated Motion & Physics Directives
* **Motion Integrity & Motivation Rule**:
  * Justify every animation in one sentence based on **hierarchy** (directing focus), **storytelling** (sequential narrative reveal), **feedback** (acknowledging user input), or **state transition** (communicating UI state change), omitting unmotivated animations.
  * Implement real entry transitions on the hero, scroll-reveals on key sections, and hover physics on CTAs whenever `MOTION_INTENSITY > 4`; if scope constraints prevent full motion implementation, lower `MOTION_INTENSITY` to `3` and deliver a clean static interface rather than shipping broken or uncleaned scroll triggers.
* **Proactive Interaction Patterns (Gated by Brief & Dials)**:
  * **Liquid Glass / Glassmorphism**: Apply on premium consumer, Apple-adjacent, luxury brand, or media-overlay briefs (excluding dashboards, public-sector, and standard B2B) by layering `backdrop-blur` with a `1px` inner border (`border-white/10`), a subtle inner shadow (`shadow-[inset_0_1px_0_rgba(255,255,255,0.1)]`), and a solid-fill fallback under `prefers-reduced-transparency`.
  * **Magnetic Micro-Physics**: Activate when `MOTION_INTENSITY > 5` on premium, playful, or agency briefs using Motion's `useMotionValue` and `useTransform` outside the React render cycle.
  * **Perpetual Micro-Interactions**: Apply pulse, typewriter, float, shimmer, or carousel loops only when `MOTION_INTENSITY > 5` AND the target component conveys live status, active feeds, or AI state (leaving informational cards static), driving motion with spring physics (`type: "spring", stiffness: 100, damping: 20`) rather than linear easing.
  * **Horizontal Marquee Cap**: Limit horizontal scrolling text or logo marquees to a **maximum of 1 marquee per page**.
* **Animation Library Isolation & Execution Rules**:
  * Use **Motion (`motion/react`)** for UI state transitions, bento grids, `layout` / `layoutId` shared-element transitions (applied only to elements undergoing visible state/list/modal layout changes), and `staggerChildren` cascades (keeping parent `variants` and children inside the same Client Component tree, or using CSS `animation-delay: calc(var(--index) * 100ms)`).
  * Use **GSAP + `ScrollTrigger`** for full-page scrolltelling, pinned sticky-stacks, and horizontal scroll hijacks, and **Three.js / WebGL** for 3D/canvas scenes—isolating each in a dedicated leaf component with strict `useEffect` / `gsap.context` cleanup and **never mixing GSAP or Three.js with Motion in the same component tree**.
  * Drive all scroll-linked effects via Motion `useScroll()`, GSAP `ScrollTrigger`, `IntersectionObserver`, or CSS `scroll-driven animations` (`animation-timeline: view()`), excluding `window.addEventListener("scroll", ...)`, `window.scrollY` inside React state, and `requestAnimationFrame` loops that mutate React state.

### Canonical Sticky-Stack Skeleton
* Implement scroll-stacked cards using `start: "top top"` (rather than `"top center"` or `"top 80%"`), pinning the outer card without CSS `position: sticky`, animating an inner wrapper driven by the next card's scroll trigger, scoping classes with `useId`, and degrading to a static vertical list under `prefers-reduced-motion`:

```tsx
"use client";
import { useRef, useEffect, useId, type ReactNode } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { useReducedMotion } from "motion/react";

gsap.registerPlugin(ScrollTrigger);

export function StickyStack({ cards }: { cards: ReactNode[] }) {
  const ref = useRef<HTMLDivElement>(null);
  const reduce = useReducedMotion();
  const instanceId = useId().replace(/:/g, "");
  const cardClass = `stack-card-${instanceId}`;
  const innerClass = `stack-card-inner-${instanceId}`;

  useEffect(() => {
    if (reduce || !ref.current || cards.length <= 1) return;
    const ctx = gsap.context(() => {
      const cardEls = gsap.utils.toArray<HTMLElement>(`.${cardClass}`);
      cardEls.forEach((card, i) => {
        if (i === cardEls.length - 1) return;
        ScrollTrigger.create({
          trigger: card,
          start: "top top",                              // pin at viewport top
          endTrigger: cardEls[cardEls.length - 1],
          end: "top top",
          pin: true,
          pinSpacing: false,
          anticipatePin: 1,
          invalidateOnRefresh: true,
        });
        const inner = card.querySelector(`.${innerClass}`);
        if (!inner) return;
        gsap.to(inner, {
          scale: 0.92,
          opacity: 0.55,
          ease: "none",
          scrollTrigger: {
            trigger: cardEls[i + 1],
            start: "top bottom",
            end: "top top",
            scrub: true,
            invalidateOnRefresh: true,
          },
        });
      });
    }, ref);
    return () => ctx.revert();
  }, [reduce, cards.length, cardClass, innerClass]);

  return (
    <div ref={ref} className="relative">
      {cards.map((card, i) => (
        <div
          key={i}
          style={{ zIndex: i + 1 }}
          className={`${cardClass} relative min-h-[100dvh] flex items-center justify-center`}
        >
          <div className={`${innerClass} w-full flex items-center justify-center will-change-transform`}>
            {card}
          </div>
        </div>
      ))}
    </div>
  );
}
```

### Canonical Horizontal-Pan Skeleton
* Implement vertical-to-horizontal scroll hijacks using `start: "top top"`, `pin: true` on the outer wrapper, function-based `x` and `end: () => "+=" + getDistance()` with `invalidateOnRefresh: true`, `w-max` on the inner track with non-shrinking child panels (`shrink-0`), and an accessible `overflow-x-auto snap-x snap-mandatory` fallback under `prefers-reduced-motion`:

```tsx
"use client";
import { useRef, useEffect, type ReactNode } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { useReducedMotion } from "motion/react";

gsap.registerPlugin(ScrollTrigger);

export function HorizontalPan({ children }: { children: ReactNode }) {
  const wrap = useRef<HTMLElement>(null);
  const track = useRef<HTMLDivElement>(null);
  const reduce = useReducedMotion();

  useEffect(() => {
    if (reduce || !wrap.current || !track.current) return;
    const ctx = gsap.context(() => {
      const getDistance = () =>
        Math.max(0, track.current!.scrollWidth - wrap.current!.clientWidth);
      gsap.to(track.current, {
        x: () => -getDistance(),
        ease: "none",
        scrollTrigger: {
          trigger: wrap.current,
          start: "top top",                              // pin starts when section top hits viewport top
          end: () => `+=${getDistance()}`,               // scroll distance = track width minus viewport, recomputed on refresh
          pin: true,
          scrub: 1,
          anticipatePin: 1,
          invalidateOnRefresh: true,
        },
      });
    }, wrap);
    return () => ctx.revert();
  }, [reduce]);

  return (
    <section
      ref={wrap}
      role="region"
      aria-label="Horizontal content track"
      tabIndex={reduce ? 0 : undefined}
      className={`relative w-full ${reduce ? "overflow-x-auto scroll-smooth" : "overflow-hidden"}`}
    >
      <div
        ref={track}
        className={`flex h-[100dvh] w-max items-center ${reduce ? "snap-x snap-mandatory" : ""}`}
      >
        {children}
      </div>
    </section>
  );
}
```

### Canonical Scroll-Reveal Stagger Skeleton
* Implement non-pinned viewport entry reveals using Motion's `whileInView` and `useReducedMotion` rather than GSAP `ScrollTrigger`:

```tsx
"use client";
import { motion, useReducedMotion } from "motion/react";

export function RevealStagger({ items }: { items: string[] }) {
  const reduce = useReducedMotion();
  return (
    <ul className="grid gap-6">
      {items.map((item, i) => (
        <motion.li
          key={item}
          initial={reduce ? false : { opacity: 0, y: 24 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true, amount: 0.3 }}
          transition={{
            duration: 0.6,
            delay: i * 0.06,
            ease: [0.16, 1, 0.3, 1],
          }}
        >
          {item}
        </motion.li>
      ))}
    </ul>
  );
}
```

### Performance, Hardware Acceleration & Accessibility Guardrails
* **GPU Compositing**: Animate exclusively `transform` and `opacity` properties, applying `will-change: transform` sparingly only on actively animating elements and excluding layout-triggering properties (`top`, `left`, `width`, `height`).
* **Reduced Motion Compliance**: Gate every animation where `MOTION_INTENSITY > 3` (including infinite loops, parallax, scroll-hijacks, and magnetic physics) behind `useReducedMotion()` in React or `@media (prefers-reduced-motion: no-preference)` / `@media (prefers-reduced-motion: reduce)` in CSS so motion collapses cleanly to static/instant states.
* **Core Web Vitals Targets**:
  * **LCP < 2.5s**: Preload the hero image or mark it with `next/image priority`.
  * **INP < 200ms**: Keep heavy computation off the main thread.
  * **CLS < 0.1**: Reserve explicit aspect-ratio dimensions for images, fonts, and embeds; verify via Lighthouse prior to completion.
* **DOM Cost & Z-Index Scale**:
  * Attach grain/noise filters exclusively to fixed, non-interactive pseudo-elements (`fixed inset-0 z-[60] pointer-events-none`), excluding scrolling containers to preserve mobile GPU frame rates.
  * Lazy-load below-the-fold heavy dependencies (such as Three.js or complex Motion trees).
  * Centralize `z-index` values in a documented project constants scale reserved for systemic layer contexts (sticky navbars, modals, overlays, fixed grain), excluding arbitrary `z-10` or `z-50` utility spamming.

## PATTERN VOCABULARY

* Reference and implement the following canonical UI patterns when aligned with the design read and dial configuration:
  * **Hero Paradigms**:
    * **Asymmetric Split Hero**: Text on one side, visual asset on the other, generous negative space.
    * **Editorial Manifesto Hero**: Large-scale display typography as the sole visual anchor.
    * **Video / Media Mask Hero**: Display typography masking an underlying video background.
    * **Kinetic-Type Hero**: Animated typography acting as the primary focal visual.
    * **Curtain-Reveal Hero**: Hero surface parting laterally or vertically on scroll.
    * **Scroll-Pinned Hero**: Hero remaining pinned while subsequent content scrolls over or behind it.
  * **Navigation & Menus**:
    * **Mac OS Dock Magnification**: Edge navigation bar with icons scaling fluidly on hover proximity.
    * **Magnetic Button**: Interactive trigger pulling toward cursor coordinates.
    * **Gooey Menu**: Sub-items detaching with viscous SVG filter physics.
    * **Dynamic Island**: Morphing pill container for contextual status and alerts.
    * **Contextual Radial Menu**: Circular action menu expanding around the pointer click point.
    * **Floating Speed Dial**: Floating action button springing into a curved arc of secondary actions.
    * **Mega Menu Reveal**: Full-width dropdown with staggered content fade-in.
  * **Layout & Grids**:
    * **Bento Grid**: Asymmetric multi-span tile grouping (Apple Control Center paradigm).
    * **Masonry Layout**: Staggered multi-column grid with variable row heights.
    * **Chroma Grid**: Grid borders and tiles with subtle animating gradient strokes.
    * **Split-Screen Scroll**: Dual viewport halves scrolling in opposing directions or speeds.
    * **Sticky-Stack Sections**: Full-height sections that pin and stack sequentially on scroll.
  * **Cards & Containers**:
    * **Parallax Tilt Card**: 3D perspective tilt tracking mouse coordinates.
    * **Spotlight Border Card**: Card borders illuminating radially beneath the cursor.
    * **Glassmorphism Panel**: Frosted translucent surface with inner specular border refraction.
    * **Holographic Foil Card**: Iridescent rainbow shader/gradient shift on pointer hover.
    * **Tinder Swipe Stack**: Physical card stack supporting drag-and-swipe dismissal.
    * **Morphing Modal**: Trigger button expanding seamlessly into its own modal dialog container (`layoutId`).
  * **Scroll Animations**:
    * **Sticky Scroll Stack**: Cards pinning at viewport top and physically stacking.
    * **Horizontal Scroll Hijack**: Vertical scroll input driving a pinned horizontal content pan.
    * **Locomotive / Sequence Scroll**: Video frames or 3D keyframe sequences scrubbed by scrollbar progress.
    * **Zoom Parallax**: Central background image scaling smoothly across scroll progress.
    * **Scroll Progress Path**: SVG vector path drawing itself in proportion to scroll position.
    * **Liquid Swipe Transition**: Route or section transition wiping with viscous wave geometry.
  * **Galleries & Media**:
    * **Dome Gallery**: 3D spherical/panoramic media gallery.
    * **Coverflow Carousel**: 3D perspective carousel with angled flanking items.
    * **Drag-to-Pan Grid**: Boundless two-dimensional draggable canvas grid.
    * **Accordion Image Slider**: Narrow vertical/horizontal media strips expanding on hover.
    * **Hover Image Trail**: Cursor movement spawning a decaying trail of popping images.
    * **Glitch Effect Image**: RGB-channel displacement shift triggered on hover.
  * **Typography & Text**:
    * **Kinetic Marquee**: Continuous text band reversing direction on scroll velocity (max 1 per page).
    * **Text Mask Reveal**: Massive typography serving as a transparent window to background video.
    * **Text Scramble Effect**: Matrix-style character decoding animation on load or hover.
    * **Circular Text Path**: Typography curving along a rotating SVG circular path.
    * **Gradient Stroke Animation**: Outlined display typography with an animated gradient stroke.
    * **Kinetic Typography Grid**: Grid of letterforms repelling or dodging cursor proximity.
  * **Micro-Interactions & Effects**:
    * **Particle Explosion Button**: CTA bursting into physics particles upon success state.
    * **Liquid Pull-to-Refresh**: Reload indicator detaching like viscous droplets.
    * **Skeleton Shimmer**: Animated light reflection sweeping across layout-matched placeholders.
    * **Directional Hover-Aware Button**: Background fill entering from the exact edge entered by the cursor.
    * **Ripple Click Effect**: Radial wave expanding from pointer click coordinates.
    * **Animated SVG Line Drawing**: Vector strokes animating `stroke-dashoffset` in real time.
    * **Mesh Gradient Background**: Organic multi-stop radial/SVG lava-lamp background blobs.
    * **Lens Blur Depth**: Background UI layers blurring dynamically to isolate foreground action.

## REDESIGN PROTOCOL

### Mode Detection & Pre-Modification Audit
* **Classify the Build Mode**:
  1. **Greenfield**: New build or approved visual/structural replacement; initialize dials from the Dial Configuration Matrix.
  2. **Redesign - Preserve**: Modernize execution while preserving existing brand equity (`State_i = sync(State_{i-1})`); audit existing tokens first and evolve incrementally (`DESIGN_VARIANCE: match existing`, `MOTION_INTENSITY: +1`, `VISUAL_DENSITY: match existing`).
  3. **Redesign - Overhaul**: Apply a new visual language over existing content and information architecture (`State_i = Content(State_{i-1}) + Δ_Visual`; `DESIGN_VARIANCE: +2`, `MOTION_INTENSITY: +2`, `VISUAL_DENSITY: match existing`).
  * Ask exactly **one** clarifying question if the redesign mode is ambiguous: *"Should this redesign preserve the existing brand, or are we starting visually from scratch?"*
* **Execute a 7-Point Baseline Audit Before Modifying Code**:
  1. **Brand Tokens**: Extract primary/accent colors, typography stack, logo treatment, and border radii.
  2. **Information Architecture (IA)**: Map the page tree, primary navigation, and conversion paths.
  3. **Content Blocks**: Catalog active functional blocks versus redundant filler.
  4. **Patterns to Preserve**: Identify signature interactions, recognizable hero structures, and copy voice.
  5. **Patterns to Retire**: Isolate AI-slop tells, broken responsive layouts, dead links, generic stock imagery, and performance bottlenecks.
  6. **Existing Dial Reading**: Infer current `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY` as the starting baseline.
  7. **SEO Baseline**: Record ranking URLs, meta titles, structured data, and Open Graph cards to prevent SEO migration loss.

### Preservation Locks & Modernization Levers
* **Enforce Preservation Locks**:
  * Maintain existing information architecture, URL route slugs, anchor IDs, primary navigation labels, form field names/order (preserving analytics and autofill bindings), brand logos/wordmarks, copy voice, accessibility attributes (focus rings, `alt` text, keyboard navigation, contrast), and legal/consent/cookie copy unless the user explicitly approves changes.
  * Extract existing brand colors prior to applying default color bans (preserving purple for an established purple brand under the Lila Rule override).
* **Apply Modernization Levers in Priority Order (Stopping When Brief Is Satisfied)**:
  1. **Typography Refresh**: Upgrade font pairings, scale hierarchy, and tracking for maximum visual lift at minimal structural risk.
  2. **Spacing & Rhythm**: Expand section padding and normalize vertical rhythm.
  3. **Color Recalibration**: Desaturate secondary tones and unify neutrals while retaining the primary brand accent.
  4. **Motion Layer**: Add `MOTION_INTENSITY`-calibrated micro-interactions to existing components.
  5. **Hero & Key-Section Recomposition**: Restructure top-of-funnel sections using the Pattern Vocabulary.
  6. **Full Block Replacement**: Replace a component block only when its existing DOM/layout structure is unsalvageable.
* **Route via the Redesign Decision Tree**:
  * **Sound IA, Content & SEO** ➔ Execute **Targeted Evolution** (Levers 1-4), capturing `~70%` of visual value at `~40%` of migration risk.
  * **Structural Visual Debt (broken IA, absent design system, broken mobile)** ➔ Execute **Full Redesign** (Levers 1-6) with strict content and SEO preservation.
  * **Brand Identity Replacement** ➔ Execute as **Greenfield**.

## BLOCK LIBRARY CONTRACT

### File Location & Naming Schema
* Store standalone, reusable pattern implementations under the canonical directory hierarchy, appending `--<system>.md` when a block depends on an official design system from the Design System Selection Matrix (e.g., `feature/bento-grid--material.md`):

```text
skills/taste-skill/blocks/
  hero/
    asymmetric-split.md
    editorial-manifesto.md
    kinetic-type.md
    ...
  feature/
    bento-grid.md
    sticky-scroll-stack.md
    zig-zag.md
    ...
  social-proof/
  pricing/
  cta/
  footer/
  navigation/
  portfolio/
  transition/
```

### Block Frontmatter & Body Contract
* Define each block in a dedicated single-block file beginning with the required YAML frontmatter schema:

```yaml
---
name: asymmetric-split-hero
category: hero
dial_compatibility:
  variance: [6, 10]
  motion: [3, 10]
  density: [2, 5]
when_to_use: "Landing pages with one strong asset and one strong message. Default hero for SaaS, agency, premium consumer."
not_for: "Editorial / manifesto launches where the message IS the design."
stack: ["react", "next", "tailwind", "motion"]
---
```

* Include all **8 required body sections** in every block definition and verify that the standalone component passes the Pre-Flight Audit Protocol:
  1. **Visual sketch**: Concise ASCII diagram or structural layout description.
  2. **Props API**: TypeScript interface defining the component contract.
  3. **Code sketch**: Minimal working implementation (Server Component default with isolated `'use client'` leaf for motion).
  4. **Mobile fallback**: Explicit collapse rules for viewports `< 768px`.
  5. **Motion variants**: Explicit variants for each `MOTION_INTENSITY` band (`1-3`, `4-7`, `8-10`) plus `prefers-reduced-motion` fallback.
  6. **Dark-mode notes**: Token strategy specific to the block.
  7. **Anti-patterns**: Specific structural or visual failure modes to exclude.
  8. **References**: Links to live production implementations.

## PRE-FLIGHT AUDIT PROTOCOL

* Execute and verify every gate in the following matrix prior to emitting final code; repair any failing criterion before delivery:

| Audit Domain | Mandatory Verification Criteria |
|---|---|
| **1. Brief, Dials & System** | - Declare the one-line Design Read (`"Reading this as: ..."`).<br>- Derive explicit `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY` values from the brief.<br>- Lock a single official design system package OR label custom aesthetic approximations honestly.<br>- Classify the Redesign Mode and execute the 7-point baseline audit when modifying an existing site. |
| **2. Theme, Color & Shape Locks** | - Lock ONE page-wide theme mode (light, dark, or auto) with zero mid-page theme inversions.<br>- Define and verify dark-mode tokens (`dark:` utilities or CSS variables) across both modes, excluding pure `#000000` and `#ffffff`.<br>- Lock ONE accent color (`< 80%` default saturation) across all sections, excluding unprompted AI-purple glows.<br>- Rotate premium-consumer palettes away from the banned beige/cream + brass/clay/oxblood/ochre + espresso hex families.<br>- Lock ONE consistent corner-radius scale across the page. |
| **3. Typography & Copy Hygiene** | - Eliminate 100% of em-dashes (`—`) and separator en-dashes (`–`) across all visible text and `alt` attributes.<br>- Use approved sans-serif defaults (`Geist`, `Outfit`, `Cabinet Grotesk`, `Satoshi`), reserving `Inter` for explicit overrides and rotating justified serifs from the 20-font pool (excluding `Fraunces` and `Instrument_Serif`).<br>- Apply `leading-[1.1]` min + `pb-1`/`mb-1` clearance on every italic display word containing `y`, `g`, `j`, `p`, or `q`.<br>- Emphasize inline headline words using weight/italic of the same font family.<br>- Audit all visible strings for grammar, clear referents, single copy register, organic data realism, grounded/mock-labeled metrics, and `≤ 3`-line quotes with clean attribution (`Name + Role`).<br>- Eliminate all Production-Test Tells (version eyebrows, section-number prefixes, `01 / 4` counters, chained `·` > 1 per line, decorative status dots, `"Quietly in use at"`, `"Field notes"`, `"Stage 1"`, image tag overlays, fake photo credits, devtool version footers, fake stock counters, locale/weather strips, and scroll cues). |
| **4. Hero, Nav & Section Layout** | - Fit the hero within `min-h-[100dvh]` without scrolling: top padding `≤ pt-24`, headline `≤ 2` lines (`text-4xl` to `text-6xl` default), subtext `≤ 20` words AND `≤ 4` lines, and `≤ 4` total text elements (excluding bottom taglines, trust strips, or decoration text bars).<br>- Render desktop navigation on a single line at `lg` (`1024px`) with height `≤ 80px` (`64-72px` default).<br>- Enforce `eyebrowCount <= ceil(sectionCount / 3)` across all components (counting hero as 1).<br>- Stack section headers vertically (no default left-headline + right-floating-paragraph split headers).<br>- Cap consecutive image+text split sections at `≤ 2` in a row and use `≥ 4` distinct layout families across 8 sections (excluding 3-equal-column card rows).<br>- Match bento cell count exactly to item count ($N$ items ➔ $N$ cells, zero empty cells) with visual background variation in `≥ 2-3` cells.<br>- Route lists `> 5` items and spec sheets to card grids, scroll-snap pills, grouped clusters, or disclosures (excluding per-row `border-t` + `border-b` tables and filled-track progress bars).<br>- Declare explicit `< 768px` mobile collapse rules (`w-full`, `px-4`, `max-w-7xl mx-auto`) and provide loading, empty, and error states. |
| **5. Visual Assets, CTAs & Forms** | - Include real visual assets (image-gen tool first, seeded `picsum.photos` or real URLs second, explicit `<!-- TODO -->` slots third), excluding div-based fake screenshots, hand-rolled decorative SVGs, and pure-text pages.<br>- Place the logo wall below the hero using real SVG marks (Simple Icons, devicon, or inline `<svg>` monograms) with logos only (no category sub-labels or plain-text wordmarks).<br>- Use a single allowed icon library (`@phosphor-icons/react`, `hugeicons-react`, `@radix-ui/react-icons`, `@tabler/icons-react`) with uniform `strokeWidth` and no hand-rolled icon paths.<br>- Verify WCAG AA contrast (`4.5:1` body/forms, `3:1` large text `18px+`) on all buttons and form inputs, keep desktop CTA labels on 1 line (`≤ 3` words), and lock 1 unique CTA label per intent page-wide. |
| **6. Motion, Performance & A11y** | - Deliver working, motivated animations when `MOTION_INTENSITY > 4` (or lower dial to `3`), capping marquees at `≤ 1` per page.<br>- Isolate Motion (`motion/react`), GSAP (`ScrollTrigger`), and Three.js in separate `'use client'` leaf components with strict `useEffect` cleanup and zero cross-library tree mixing.<br>- Implement `StickyStack` and `HorizontalPan` per the canonical skeletons (`start: "top top"`, `pin: true`, function-based `end`, `useReducedMotion` fallback).<br>- Drive continuous/scroll values via `useMotionValue`, `useScroll`, `ScrollTrigger`, `IntersectionObserver`, or CSS `animation-timeline` (zero `window.addEventListener('scroll')` or `useState` scroll tracking).<br>- Animate only `transform` and `opacity`, wrap all `MOTION_INTENSITY > 3` motion in `prefers-reduced-motion`, isolate grain overlays on `fixed inset-0 z-[60] pointer-events-none`, and meet Core Web Vitals (`LCP < 2.5s`, `INP < 200ms`, `CLS < 0.1`). |

## REFERENCE APPENDICES

### Official Design System Installation Commands

```bash
# Material Web (Material 3)
npm install @material/web

# Fluent UI React (v9)
npm install @fluentui/react-components

# Fluent UI Web Components (framework-free)
npm install @fluentui/web-components @fluentui/tokens

# IBM Carbon
npm install @carbon/react @carbon/styles

# Radix Themes
npm install @radix-ui/themes

# shadcn/ui (open code, owned components)
npx shadcn@latest init
npx shadcn@latest add button card badge separator input

# Primer CSS (GitHub product/devtool UI)
npm install --save @primer/css

# Primer Brand (GitHub marketing UI)
npm install @primer/react-brand

# GOV.UK Frontend
npm install govuk-frontend

# USWDS (US Web Design System)
npm install uswds

# Atlassian Design System (Atlaskit)
yarn add @atlaskit/css-reset @atlaskit/tokens @atlaskit/button @atlaskit/badge @atlaskit/section-message @atlaskit/card

# Bootstrap 5.3
npm install bootstrap

# Shopify Polaris Web Components (Shopify apps only)
# Add this to your app HTML head:
#   <meta name="shopify-api-key" content="%SHOPIFY_API_KEY%" />
#   <script src="[https://cdn.shopify.com/shopifycloud/polaris.js](https://cdn.shopify.com/shopifycloud/polaris.js)"></script>
```

### Canonical Documentation Sources

### Material Web
- https://github.com/material-components/material-web
- https://material-web.dev/theming/material-theming/
- https://m3.material.io/develop/web

### Fluent UI
- https://fluent2.microsoft.design/get-started/develop
- https://fluent2.microsoft.design/components/web/react/
- https://github.com/microsoft/fluentui
- https://learn.microsoft.com/en-us/fluent-ui/web-components/

### Carbon
- https://carbondesignsystem.com/
- https://github.com/carbon-design-system/carbon
- https://carbondesignsystem.com/developing/react-tutorial/overview/
- https://carbondesignsystem.com/developing/web-components-tutorial/overview/

### Shopify Polaris
- https://shopify.dev/docs/api/app-home/web-components
- https://github.com/Shopify/polaris-react
- https://polaris-react.shopify.com/components

### Atlassian
- https://atlassian.design/get-started/develop
- https://atlassian.design/components/button/examples
- https://atlaskit.atlassian.com/packages/design-system/button/example/disabled
- https://atlassian.design/tokens/design-tokens

### Primer
- https://primer.style/
- https://github.com/primer/css
- https://github.com/primer/brand

### GOV.UK
- https://design-system.service.gov.uk/components/button/
- https://design-system.service.gov.uk/styles/layout/
- https://github.com/alphagov/govuk-frontend

### USWDS
- https://designsystem.digital.gov/documentation/developers/
- https://designsystem.digital.gov/components/button/
- https://designsystem.digital.gov/components/card/
- https://github.com/uswds/uswds

### Bootstrap
- https://getbootstrap.com/docs/5.3/layout/grid/
- https://getbootstrap.com/docs/5.3/components/card/

### Tailwind
- https://tailwindcss.com/docs/dark-mode
- https://tailwindcss.com/blog/tailwindcss-v4

### Radix
- https://www.radix-ui.com/themes/docs/components/theme
- https://www.radix-ui.com/themes/docs/components/card
- https://github.com/radix-ui/themes

### shadcn/ui
- https://ui.shadcn.com/docs
- https://ui.shadcn.com/docs/components/card
- https://github.com/shadcn-ui/ui

### Native CSS / W3C Standards
- https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/backdrop-filter
- https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-color-scheme
- https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-reduced-motion
- https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Grid_layout
- https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Scroll-driven_animations
- https://drafts.csswg.org/scroll-animations-1/

### Apple Liquid Glass (Apple Platforms Only)
- https://developer.apple.com/design/human-interface-guidelines/materials
- https://developer.apple.com/documentation/TechnologyOverviews/liquid-glass
- https://developer.apple.com/documentation/TechnologyOverviews/adopting-liquid-glass
- https://developer.apple.com/documentation/SwiftUI/Material

### Apple Liquid Glass Web Approximation Skeleton
* Reference Apple's official documentation (Apple Human Interface Guidelines ➔ Materials; Apple Developer Documentation ➔ Liquid Glass & Adopting Liquid Glass; SwiftUI ➔ Material) strictly as native Apple platform specifications, and label any web CSS implementation explicitly as a frosted-glass web approximation (`backdrop-filter`, transparent backgrounds, layered borders, highlight overlays, gradients, motion, and high-contrast fallbacks under `@media (prefers-reduced-transparency: reduce)`):

```css
.liquid-glass-web-approx {
  position: relative;
  isolation: isolate;
  overflow: hidden;
  border-radius: 999px;
  border: 1px solid rgb(255 255 255 / .32);
  background:
    linear-gradient(135deg, rgb(255 255 255 / .30), rgb(255 255 255 / .08)),
    rgb(255 255 255 / .12);
  backdrop-filter: blur(24px) saturate(180%) contrast(1.05);
  -webkit-backdrop-filter: blur(24px) saturate(180%) contrast(1.05);
  box-shadow:
    inset 0 1px 0 rgb(255 255 255 / .48),
    inset 0 -1px 0 rgb(255 255 255 / .12),
    0 18px 60px rgb(0 0 0 / .18);
}

.liquid-glass-web-approx::before {
  content: "";
  position: absolute;
  inset: 0;
  z-index: -1;
  border-radius: inherit;
  background:
    radial-gradient(circle at 20% 0%, rgb(255 255 255 / .55), transparent 34%),
    linear-gradient(90deg, rgb(255 255 255 / .18), transparent 42%, rgb(255 255 255 / .14));
  pointer-events: none;
}

.liquid-glass-web-approx::after {
  content: "";
  position: absolute;
  inset: 1px;
  border-radius: inherit;
  border: 1px solid rgb(255 255 255 / .14);
  pointer-events: none;
}

@media (prefers-color-scheme: dark) {
  .liquid-glass-web-approx {
    border-color: rgb(255 255 255 / .18);
    background:
      linear-gradient(135deg, rgb(255 255 255 / .16), rgb(255 255 255 / .04)),
      rgb(15 23 42 / .42);
    box-shadow:
      inset 0 1px 0 rgb(255 255 255 / .22),
      0 18px 60px rgb(0 0 0 / .42);
  }
}

@media (prefers-reduced-transparency: reduce) {
  .liquid-glass-web-approx {
    background: rgb(255 255 255 / .96);
    backdrop-filter: none;
    -webkit-backdrop-filter: none;
  }
}
```
