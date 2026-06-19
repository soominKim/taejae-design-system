## Overview

The TAEJAE AI Graduate School design system is an exercise in **treating purple as a strategic weapon on a restrained white canvas**. The default page background is pure white (`{colors.background}` — #ffffff), and body text is carried by a near-black with a purple undertone (`{colors.foreground}` — hsl(270 12% 10%)). The brand color, **TJ Purple** (`{colors.primary-700}` — #522C81), is never used to flood the background — it appears only on heroes, CTAs, badges, and headings as an accent. Filling an entire screen with purple is deliberately avoided. As a result, every appearance of purple reads as a signal: *this matters*.

The second color is **TJ Mint** (`{colors.secondary-600}` — #00A497). Mint is not a surface fill but **the color of interaction** — links, hovers, success states, secondary CTAs, and the English section labels (eyebrows). The space between purple and mint is filled with desaturated warm neutral greys (`{colors.warm}` scale) — not plain grey, but a warm grey carrying a purple undertone, a deliberate detail. Sections alternate between pure white and a pale purple tint (`{colors.primary-50}` — #F7F3FB) to build rhythm, and high-contrast bands use a purple-tinted near-black dark section (`{colors.warm-950}` — #1A1625).

Typography runs entirely on a single typeface, **Pretendard Variable**, which covers the full 45–920 variable weight range. Headings are packed tight with heavy weights and negative tracking (`tracking-tight`), while English eyebrows label sections like a spec sheet in small uppercase with wide tracking. The shape language is, in a word, **Sharp Geometry** — `border-radius: 0` is the brand default. Rounded corners like `rounded-lg`/`rounded-xl` are forbidden; cards, buttons, and inputs all break at right angles. McKinsey's high-contrast editorial grid, Minerva's card-based modular layout, and d.school's expressive type scale serve as reference points — but it is the right-angle geometry that binds them all into one brand.

**Key Characteristics:**
- A **white-dominant** structure where purple-undertone near-black (`{colors.foreground}`) carries body text on a pure-white canvas (`{colors.background}`) — purple never floods the screen.
- **TJ Purple** (`{colors.primary-700}` — #522C81) is an accent reserved for heroes, CTAs, badges, and headings; **TJ Mint** (`{colors.secondary-600}` — #00A497) is the interactive color reserved for links, hovers, success, and secondary CTAs.
- **Sharp Geometry**: `border-radius: 0` is the default (`{rounded.none}`). Rounded corners are a brand violation.
- A single typeface, **Pretendard Variable** (45–920 variable), with negative tracking on headings and uppercase wide-tracked English eyebrows.
- A color-block page rhythm alternating pure white ↔ pale purple tint (`{colors.primary-50}`) ↔ dark (`{colors.warm-950}`).
- Warm neutrals (`{colors.warm}` scale) carry a purple undertone — they are not cold neutral greys.
- A **3-Level token architecture**: raw color scales (mode-invariant) → semantic tokens (auto-switch in dark mode) → layout tokens (auto-switch in dark mode). Raw scales never invert in dark mode (`{colors.primary-700}` is always #522C81).
- A department color system (`{colors.dept-if}`~`{colors.dept-dsai}`) distinguishes the five academic disciplines by color.

## Colors

> Color is managed through a 3-Level architecture. **Level 1 (raw scales)** is identical in light/dark; **Level 2 (semantic)** and **Level 3 (layout)** auto-switch under the `.dark` class. Components never use raw hex directly — always through a token.

### Brand & Accent
- **TJ Purple** (`{colors.primary}` / `{colors.primary-700}` — #522C81): the brand-defining purple. Used for heroes, primary CTA fills, badges, and heading emphasis. Hover is `{colors.primary-600}` (#6B3F94), pressed is `{colors.primary-800}` (#47266E). The semantic value shifts to `{colors.primary-400}` (#A07AC4) in dark mode.
- **TJ Mint** (`{colors.secondary}` / `{colors.secondary-600}` — #00A497): the interactive accent — links, hovers, success, secondary CTAs, and English eyebrow labels. Hover is `{colors.secondary-700}` (#007D74). The semantic value shifts to `{colors.secondary-400}` (#1EDECF) in dark mode.
- **Purple Scale** (`{colors.primary-50}`~`{colors.primary-950}`): an 11-step ladder from #F7F3FB → #250F3D, from tint backgrounds to deep dark.
- **Mint Scale** (`{colors.secondary-50}`~`{colors.secondary-950}`): an 11-step ladder from #EFFEFB → #003230.

### Surface
- **Background** (`{colors.background}` — #ffffff / dark hsl(270 15% 8%)): the default page background — the pure-white sheet everything sits on.
- **Card** (`{colors.card}` — #ffffff / dark hsl(270 15% 10%)): card and panel surfaces.
- **Alt Tint** (`{colors.primary-50}` — #F7F3FB): the pale purple tint section background that alternates with white.
- **Muted** (`{colors.muted}` — hsl(270 10% 96%) / dark hsl(270 10% 15%)): inset wells, secondary-information surfaces.
- **Accent Surface** (`{colors.accent}` — hsl(270 30% 96%) / dark hsl(270 20% 15%)): hover/focus surfaces.

### Text
- **Foreground** (`{colors.foreground}` — hsl(270 12% 10%) / dark hsl(270 5% 95%)): primary headings and body, a purple-undertone near-black.
- **Muted Foreground** (`{colors.muted-foreground}` — hsl(270 5% 45%) / dark hsl(270 5% 60%)): secondary copy, captions, metadata.
- **Primary Text** (`{colors.primary-700}` — #522C81): purple emphasis text.
- **Secondary Text** (`{colors.secondary-600}` — #00A497): interactive/link text and English eyebrows.
- **On Dark** (white / `{colors.white}/80`): text over dark and purple sections.

### Warm Neutrals (Purple-tinted)
A neutral scale carrying a purple undertone — the structural color of backgrounds, borders, and dark sections.
- `{colors.warm-50}` #FAF9FB → `{colors.warm-200}` #EAE7EE (borders) → `{colors.warm-600}` #8E839C (secondary text) → `{colors.warm-950}` #1A1625 (dark sections / footer).

### Borders
- **Border** (`{colors.border}` — hsl(270 10% 90%) / dark hsl(270 10% 20%)): the 1px border on every card, input, and divider — applied globally as the structural workhorse. `{colors.warm-200}` (#EAE7EE) is also used as a border.
- **Ring** (`{colors.ring}` — hsl(270 49% 34%) / dark hsl(270 60% 70%)): the focus ring (purple).

### Semantic
- **Success** (`{colors.success}` — #00A497): success — same as mint.
- **Warning** (`{colors.warning}` — #F59E0B): caution.
- **Error / Destructive** (`{colors.error}` — #EF4444 / `{colors.destructive}` hsl(0 84% 60%), dark hsl(0 62% 50%)): delete / validation failure.
- **Info** (`{colors.info}` — #3B82F6): informational.

### Department Colors
Department badge colors distinguishing the five academic disciplines.
- **IF (Future Convergence)** (`{colors.dept-if}` — #522C81) · **H&S (Humanities & Social Sciences)** (`{colors.dept-hs}` — #00A497) · **BI (Business Innovation)** (`{colors.dept-bi}` — #2563EB) · **NS (Natural Sciences)** (`{colors.dept-ns}` — #EA580C) · **DS&AI (Data Science & AI)** (`{colors.dept-dsai}` — #7C3AED).

### Brand Gradients
Restrained gradients built only from the purple family — the expression is driven by lightness shifts, not color mixing.
- **Hero**: `{colors.primary-700}` (#522C81) → `{colors.primary-950}` (#250F3D) — purple → deep dark purple (135deg).
- **Text Primary**: `{colors.primary-700}` → `{colors.primary-500}` — heading gradient text.
- **Text Mixed**: `{colors.primary-700}` → `{colors.secondary-600}` — purple → mint, reserved for convergence phrasing like "technology and the humanities."

## Typography

### Font Family
The entire system runs on a single typeface, **Pretendard Variable**. A single file (`PretendardVariable.woff2`) covers the full 45–920 variable weight range, and this one face carries UI, prose, headings, and labels alike. There is no second face — `font-mono` and `font-serif` are forbidden. For Korean legibility, `word-break: keep-all` and the `ss01`/`ss02`/`cv01` OpenType features are applied globally.

```css
font-family: "Pretendard Variable", "Pretendard", -apple-system,
  BlinkMacSystemFont, system-ui, "Apple SD Gothic Neo", "Noto Sans KR", sans-serif;
```

### Hierarchy

| Token | Size | Line Height | Use |
|---|---|---|---|
| `{typography.display-7xl}` | 72px | tight | Hero headline |
| `{typography.display-6xl}` | 60px | tight | Page title |
| `{typography.heading-5xl}` | 48px | tight | Large section header |
| `{typography.heading-4xl}` | 36px | tight | Section header |
| `{typography.heading-3xl}` | 30px | snug | Card title |
| `{typography.heading-2xl}` | 24px | snug | Component header |
| `{typography.lead-xl}` | 20px | normal | Lead text |
| `{typography.body-lg}` | 18px | relaxed | Large body |
| `{typography.body-base}` | 16px | relaxed | Default body |
| `{typography.body-sm}` | 14px | normal | Small text, captions |
| `{typography.label-xs}` | 12px | normal | Labels, badges, eyebrows |

### Weights

| Token | Weight | Use |
|---|---|---|
| `{typography.light}` | 300 | Decorative light text |
| `{typography.normal}` | 400 | Body |
| `{typography.medium}` | 500 | Emphasis, navigation |
| `{typography.semibold}` | 600 | Sub-headings, labels, eyebrows |
| `{typography.bold}` | 700 | Headings, buttons |
| `{typography.extrabold}` | 800 | Hero emphasis |
| `{typography.black}` | 900 | Maximum impact |

### Principles
- Headings are packed tight with heavy weights (700–800) and `tracking-tight` (negative tracking). The larger the heading, the tighter.
- Headings are always written at responsive scale — `text-4xl md:text-5xl lg:text-7xl`. Avoid a single fixed size.
- English eyebrows sit above the Korean heading in small uppercase with `tracking-wider` and `{colors.secondary-600}`, labeling sections like spec-sheet headers.
- Gradient text (`text-gradient-primary`, `text-gradient-mixed`) is applied sparingly, to key words only.

### Section Header Pattern
```tsx
<span className="mb-2 inline-block text-sm font-semibold uppercase tracking-wider text-secondary-600">
  Academy Programs
</span>
<h2 className="text-3xl font-bold tracking-tight md:text-4xl">
  교육 과정
</h2>
```

## Layout

### Spacing System
- Vertical section rhythm is the skeleton of the layout. Small `{spacing.sm}` 48px (`py-12`) · Default `{spacing.md}` 80px (`py-20`) · Large `{spacing.lg}` 96px (`py-24`) · XL `{spacing.xl}` 128px (`py-32`).
- Section header bottom margin 48px (`mb-12`), card grid gap 24px (`gap-6`), tight content gap 16px (`gap-4`).
- Container horizontal padding 24px (`px-6`).

### Grid & Container
- Centered container — Default `max-w-7xl` (1280px) · Narrow `max-w-5xl` (1024px) · Wide `max-w-[1440px]`. Horizontal `px-6`.
- Layout is never written by hand — it is composed only with the `<Container>` / `<Section>` components (writing `max-w-7xl mx-auto px-6` directly is forbidden).
- Card grids use 2-up / 3-up (most common) / 4-up patterns, collapsing to 1-up at narrow widths.

### Whitespace Philosophy
Whitespace is structural. The pure-white canvas and generous section padding do the separating work; cards are grouped by a 1px border and right-angle geometry rather than heavy backgrounds. Large gaps between sections (80–128px), tight internal rhythm inside cards.

### Section Alternation
Lay down pure white → pale purple tint (`{colors.primary-50}`) → pure white in alternation, with dark (`{colors.warm-950}`) for stats/contrast bands, purple (`{colors.primary-700}`) for CTAs, and dark for the footer.

```
Header(white sticky) → Hero(gradient/image) → Stats(dark warm-950)
→ Content(white) → Content(tint primary-50) → Content(white)
→ CTA(primary-700) → Footer(warm-950)
```

### Responsive Strategy

#### Breakpoints
| Name | Width | Key Changes |
|---|---|---|
| Mobile | 0px+ | Single-column stacks; nav → menu trigger; hero type scales down |
| `sm` | 640px+ | Large mobile |
| `md` | 768px+ | 2-up card grids; tablet |
| `lg` | 1024px+ | 3–4-up grids; full nav row |
| `xl` | 1280px+ | Centered max-width container |

#### Collapsing Strategy
The nav row collapses behind a menu trigger, multi-column card grids reflow to a single column, and hero type steps down through `text-4xl → md:text-5xl → lg:text-7xl`.

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| 0 — Flat | 1px border (`{colors.border}`), no shadow | Default cards, inputs, dividers, the canvas |
| 1 — Subtle | Border + `shadow-xs` micro-shadow | Lightly-raised cards, outline buttons |
| 2 — Floating | Soft layered shadow | Menus, modals, dropdowns, sticky header |

Depth is deliberately restrained. The system prefers a **1px border + a white-on-white surface step** over a shadow. Because the color-block sections (tint/dark backgrounds) create their own sense of depth, heavy elevation is almost never used.

### Decorative Depth
The only atmospheric element is the hero's **purple gradient** (`bg-gradient-hero`, #522C81 → #250F3D) and its overlay (`bg-gradient-hero-overlay`). Entrance animations use `animate-fade-in` / `animate-slide-up` on an `ease-out-expo` (cubic-bezier(0.16,1,0.3,1)) curve, and card grids stagger by index via Framer Motion (delay `i * 0.1s`). No glows, no heavy gradients.

## Shapes

### Border Radius Scale
**Sharp Geometry** is the brand identity — the default is a right angle (`{rounded.none}` 0). Rounded corners are deliberately restrained.

| Token | Value | Use |
|---|---|---|
| `{rounded.none}` | 0 | **Default** — cards, buttons, inputs, sections, every surface |
| `{rounded.sm}` | 2px | Chips needing the faintest rounding |
| `{rounded.md}` | 4px | shadcn component default (use sparingly) |
| `{rounded.lg}` | 8px | Exceptional large panels |
| `{rounded.full}` | 9999px | Avatars, circular icons, dot indicators |

> The global default of `--radius` is `0rem`. Using `rounded-lg`/`rounded-xl` on content cards is considered a brand violation.

### Geometry
Cards, buttons, and inputs are right-angle rectangles. Only avatars and circular icons use `{rounded.full}`. Heroes are a purple gradient or an image overlay. Centered on photography and type grids rather than illustration.

## Components

> Every component defaults to `rounded-none` (sharp geometry). Color goes through tokens — never raw hex. Layout is composed only with `<Container>`/`<Section>`.

### Layout

**`Container`** — width wrapper
- `size="default"` (max-w-7xl/1280px) · `narrow` (max-w-5xl/1024px) · `wide` (max-w-[1440px]) · `full`. Horizontal `px-6`. All content lives inside it.

**`Section`** — section wrapper
- `variant="default"` (white) · `alt` (pale purple tint `{colors.primary-50}`) · `dark` (`{colors.warm-950}`) · `primary` (`{colors.primary-700}`) · `gradient`. `spacing="sm|md|lg|xl"` (48/80/96/128px).

**`PageHeader`** — page title
- `title`, `description`, `breadcrumbs[]`, `variant="default|primary"`. The title block at the top of a page.

**`Header`** — sticky navigation
- White background, bottom border, right angles. Wordmark + nav links + CTA.

**`Footer`** — site footer
- Dark background (`{colors.warm-950}`), multi-column link groups.

### Buttons (shadcn/ui · New York)
Shared: `inline-flex`, `font-medium`, `transition-all`, focus `ring-ring/50 ring-[3px]`, right angles.

**`button-default`** — the default purple CTA
- Background `{colors.primary}`, text `{colors.primary-foreground}` (white), hover `primary/90`. Default size `h-9 px-4`.

**`button-secondary`** — mint secondary
- Background `{colors.secondary}`, text `{colors.secondary-foreground}`, hover `secondary/80`.

**`button-outline`** — bordered button
- 1px border + `{colors.background}` fill + `shadow-xs`; hover surface `{colors.accent}`.

**`button-ghost`** — ghost
- Transparent; hover surface `{colors.accent}`.

**`button-link`** — link-style
- `{colors.primary}` text + underline on hover.

**`button-destructive`** — delete / danger
- Background `{colors.destructive}`, white text.

- Size tokens: `xs` (h-6) · `sm` (h-8) · `default` (h-9) · `lg` (h-10) · `icon` (size-9) and icon-xs/sm/lg.

### Features

**`HeroSection`** — hero
- `variant="default"` (purple gradient) · `overlay` (image + purple overlay) · `split` (left/right split). `title`, `subtitle` (English), `description`, `primaryCTA`, `secondaryCTA`.

**`CourseCard`** — course card
- `department="IF|H&S|BI|NS|DS&AI"` drives the department-color badge. `title`, `description`, `tags[]`, `duration`, `image`, `href`. Right-angle card.

**`ProfileCard`** — faculty profile
- `name`, `title`, `department`, `image`, `quote`, `specialties[]`.

**`StatsGrid`** — key metrics
- `stats[]` (value/label/suffix), `variant="default|primary|dark"`. Usually placed on a dark section.

**`CTABanner`** — call-to-action banner
- `title`, `description`, `primaryCTA`, `variant="primary|dark|mint"`. End of page.

**`AcademyGrid`** — course grid
- `title`, `subtitle`, `courses[]`, `columns={2|3|4}`.

**`TimelineSection`** — step timeline · **`TestimonialCard`** — student review · **`NewsCard`** — news (`variant="default|horizontal"`) · **`AnnouncementBar`** — top banner (`variant="primary|mint|dark"`, `dismissible`).

### Cards & Containers

**`Card`** — default content card
- Background `{colors.card}`, 1px border `{colors.border}`, text `{colors.card-foreground}`, **right angles** (`rounded-none`), padding 24px. Level-0 flat is the default.

### Forms

**`LoginForm`** · **`RegisterForm`** · **`EnrollmentForm`** (`courseName`) · **`ContactForm`** · **`PrivacyConsent`** (privacy-agreement checkbox). Right-angle inputs, border `{colors.input}`, focus ring `{colors.ring}`.

## Dark Mode

The core of the dark-mode strategy is that **raw scales never invert**. `{colors.primary-700}` stays #522C81 predictably in both light and dark. What switches in dark mode is only the **semantic tokens (Level 2) and layout tokens (Level 3)** — `bg-primary`, `bg-background`, `text-foreground`, etc., automatically flip to their dark values. When a tint background is needed, don't rely on automatic switching — write it explicitly as `bg-primary-50 dark:bg-primary-950`. Activation is class-based (`.dark`).

## Do's and Don'ts

### Do
- Keep the canvas pure white (`{colors.background}`) and place purple (`{colors.primary-700}`) strategically — only on heroes, CTAs, badges, and headings.
- Use mint (`{colors.secondary-600}`) only for **interaction** — links, hovers, success, secondary CTAs, and English eyebrows.
- Make every surface a **right angle** (`rounded-none`) — sharp geometry is the brand.
- Always specify color through tokens (`bg-primary`, `text-primary-700`) and compose layout with `<Container>`/`<Section>`.
- Set headings in Pretendard 700–800 with `tracking-tight`, and label sections with uppercase English eyebrows.
- Build page rhythm by alternating pure white ↔ pale purple tint ↔ dark sections.
- Pair dark-mode tints explicitly, like `bg-primary-50 dark:bg-primary-950`.

### Don't
- Don't flood the whole screen with purple — purple is an accent, not a background.
- Don't use rounded corners (`rounded-lg`/`rounded-xl`) on content cards or buttons — a brand violation.
- Don't hardcode raw hex — `bg-[#522C81]`, `style={{ color: '...' }}` are forbidden.
- Don't use the Tailwind default palette (`bg-purple-500`, `bg-gray-100`) — only `primary-*`/`secondary-*`/`warm-*`.
- Don't change the typeface — Pretendard Variable is the only face; `font-mono`/`font-serif` are forbidden.
- Don't write `max-w-7xl mx-auto px-6` by hand — go through the layout components.
- Don't invert raw scales in dark mode — `{colors.primary-700}` is always #522C81; only semantic tokens switch.
- Don't reach for cold neutral grey — use the purple-undertone warm grey (`{colors.warm}`); a cold grey breaks the tone.
