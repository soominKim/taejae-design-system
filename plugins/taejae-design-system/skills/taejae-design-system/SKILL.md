---
name: taejae-design-system
description: >-
  Build UI, pages, components, or mockups in the TAEJAE University (태재대학교 AI미래전략대학원 /
  TAEJAE AI Graduate School) brand design system. Use this skill WHENEVER the user wants to
  design, build, lay out, redesign, or style anything that should look like TAEJAE — a webpage,
  landing page, hero, card, button, form, section, slide, or component — even if they don't say
  "design system." Trigger on phrases like "태재 스타일로", "태재대 디자인으로 만들어", "TAEJAE 브랜드로",
  "make this look like Taejae", "태재 홈페이지 컴포넌트", "보라색 태재 톤으로", or any request to apply the
  TJ Purple / TJ Mint brand, sharp geometry, or Pretendard look. The skill enforces the brand rules
  (white-dominant canvas, purple as accent only, mint for interaction, right-angle geometry, the
  3-level token system) and outputs either Next.js + Tailwind v4 code (the real codebase stack) or a
  self-contained HTML/CSS mockup.
---

# TAEJAE Design System

You are designing in the TAEJAE AI Graduate School brand. This skill gives you the tokens, rules, and
patterns to produce on-brand UI. The brand has a strong, opinionated point of view — follow it closely,
because the consistency *is* the brand.

## The one-paragraph mental model

A **white canvas** with **purple used as a strategic accent, never a background flood**. TJ Purple
(`#522C81`) appears only on heroes, CTAs, badges, and heading emphasis — every time it shows up it
signals "this matters." TJ Mint (`#00A497`) is the **interaction color** — links, hovers, success,
secondary CTAs, and the small uppercase English eyebrows that label sections. The space between is
**warm, purple-tinted neutrals** (not cold grey). Everything is **sharp** — `border-radius: 0` is the
default; rounded corners are off-brand. One typeface only: **Pretendard Variable**, headings packed
tight with heavy weight and negative tracking. Sections alternate white → pale purple tint → dark to
build rhythm. Reference points: McKinsey's editorial grid, Minerva's modular cards, d.school's
expressive type — bound together by right-angle geometry.

## Step 1 — Choose the output target

Ask yourself (or the user, if unclear) which is wanted:

- **Next.js + Tailwind v4** — the real TAEJAE codebase stack (Next.js 15, Tailwind v4 `@theme inline`
  tokens, shadcn/ui New York, Pretendard, Framer Motion). Use this when the work plugs into the actual
  project or the user mentions components, `.tsx`, Tailwind, or their repo. Read `references/nextjs.md`.
- **Standalone HTML/CSS mockup** — a single self-contained file that opens in any browser, no build
  step. Use for quick prototypes, visual proposals, or when there's no project to plug into. Read
  `references/html.md` and use `assets/taejae-tokens.css` + `assets/starter.html`.

When in doubt and the user gave no signal, default to a standalone HTML mockup (it's viewable
immediately) and mention they can get Next.js code instead.

## Step 2 — Load the tokens

The full token tables (every color step, type scale, spacing, radius, gradients, department colors)
live in `references/tokens.md`. Read it before producing anything beyond a trivial snippet — using a
hex value that isn't in the system, or the wrong token, is the most common way to break the brand.

The brand essentials you must keep in your head:

| Token | Value | Use |
|---|---|---|
| TJ Purple `primary-700` | `#522C81` | Brand accent — heroes, CTA fill, badges, heading emphasis |
| TJ Mint `secondary-600` | `#00A497` | Interaction — links, hover, success, secondary CTA, eyebrows |
| Foreground | `hsl(270 12% 10%)` | Body/heading text — purple-undertone near-black |
| Background | `#ffffff` | The default canvas |
| Alt tint `primary-50` | `#F7F3FB` | Pale purple section, alternates with white |
| Dark `warm-950` | `#1A1625` | Stats bands, footer |
| Border `warm-200` | `#EAE7EE` | The 1px border on cards/inputs/dividers |
| Font | Pretendard Variable | The only typeface (45–920 variable) |
| Radius | `0` | Sharp geometry — the default for every surface |

## Step 3 — Apply the brand rules

These rules are non-negotiable because each one is load-bearing for the brand's identity.

**Do**
- Keep the canvas white and place purple only on heroes, CTAs, badges, headings — purple is a signal,
  not a wallpaper.
- Use mint for *interaction* (links, hover, success, secondary CTA) and for uppercase English eyebrows
  above section titles.
- Make every surface a **right angle** (`rounded-none` / `border-radius:0`). Sharp geometry is the brand.
- Build vertical rhythm by alternating white → pale tint (`primary-50`) → dark (`warm-950`) sections.
- Set headings in Pretendard 700–800 with tight (negative) letter-spacing; label sections with a small
  uppercase mint eyebrow.
- Prefer a flat 1px border over a shadow. Depth is restrained — the color-block sections create depth.
- Use the warm, purple-tinted neutral scale — never a cold/blue grey.

**Don't**
- Don't flood a screen with purple — it's an accent, not a background.
- Don't use rounded corners (`rounded-lg`/`rounded-xl`, `border-radius` > a few px) on cards or buttons.
- Don't hardcode raw hex in the Next.js codebase (`bg-[#522C81]`, inline `style` colors) — use tokens.
- Don't use Tailwind's default palette (`bg-purple-500`, `bg-gray-100`) — only `primary-*`,
  `secondary-*`, `warm-*`.
- Don't introduce a second typeface (`font-mono`, `font-serif`) — Pretendard only.
- Don't pile on shadows or gradients. The hero purple gradient (`#522C81 → #250F3D`) is the only
  atmospheric flourish.
- Don't invert the raw color scales in dark mode — `primary-700` is always `#522C81`; only semantic
  tokens switch.

## Step 4 — Compose with the standard structure

A TAEJAE page reads top to bottom as a color-block rhythm:

```
Header (white, sticky)
Hero (purple gradient or image overlay)
Stats (dark, warm-950)
Content (white)
Content (pale tint, primary-50)
Content (white)
CTA banner (purple, primary-700)
Footer (dark, warm-950)
```

Each section: a small uppercase **mint eyebrow** → a tight, heavy **Korean heading** → content.
Card grids are 2-up / 3-up (most common) / 4-up, collapsing to 1-up on mobile. Headings scale
responsively (`text-4xl md:text-5xl lg:text-7xl`). Section padding runs 48 / 80 / 96 / 128px.

The component catalog (Container, Section, PageHeader, HeroSection, CourseCard, ProfileCard, StatsGrid,
CTABanner, AcademyGrid, Button variants, forms) with full props and code lives in `references/nextjs.md`.
The HTML equivalents (ready-to-paste classes for the same components) live in `references/html.md`.

## Step 5 — Self-check before delivering

Run this quick checklist — it catches the off-brand mistakes that matter most:

1. Is the canvas white and purple used only as an accent (not a full background)?
2. Are all corners square (no rounded cards/buttons)?
3. Is Pretendard the only font, headings tight and heavy?
4. Are colors from the token set (no stray hex, no Tailwind default palette)?
5. Does every section lead with a mint uppercase eyebrow + tight heading?
6. Is depth a 1px border first, shadow only when floating?
7. (Next.js) Are tokens used, not hardcoded values? (HTML) Are CSS variables used from the token sheet?

If you produced a file, save it and show it to the user. For HTML mockups, the file is directly
viewable — present it so they can open it.

## Reference files

- `references/tokens.md` — Complete token tables: colors (all scales), typography, spacing, radius,
  elevation, gradients, department colors, dark mode. Read for any non-trivial work.
- `references/nextjs.md` — Next.js 15 + Tailwind v4 + shadcn patterns, component APIs, code examples,
  the `@theme inline` token block, and the project's hard rules.
- `references/html.md` — Standalone HTML/CSS approach: how to use the token sheet, component classes,
  and the page scaffold.
- `assets/taejae-tokens.css` — Drop-in CSS custom properties (all tokens) for HTML mockups.
- `assets/starter.html` — A minimal on-brand HTML page scaffold to build from.
