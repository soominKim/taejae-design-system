# TAEJAE Design Tokens — Complete Reference

The single source of truth for every color, type, spacing, radius, and gradient value in the brand.
Never use a value that isn't here. In the Next.js codebase, reach these through Tailwind tokens
(`bg-primary-700`, `text-secondary-600`, `bg-warm-950`); in HTML mockups, reach them through the CSS
custom properties in `assets/taejae-tokens.css` (`var(--primary-700)`).

## Contents
1. Color architecture (3 levels)
2. Purple scale (primary)
3. Mint scale (secondary)
4. Warm neutrals
5. Department colors
6. Semantic / functional colors
7. Layout & component semantic tokens (light + dark)
8. Brand gradients
9. Typography (scale + weights)
10. Spacing
11. Border radius
12. Elevation
13. Dark mode rule

---

## 1. Color architecture (3 levels)

- **Level 1 — Raw scales** (`primary-50…950`, `secondary-50…950`, `warm-50…950`): identical in light
  and dark. `primary-700` is ALWAYS `#522C81`. Use for brand surfaces that must stay fixed.
- **Level 2 — Semantic tokens** (`primary`, `secondary`, `destructive`, …): auto-switch under `.dark`.
  Use for buttons, badges.
- **Level 3 — Layout tokens** (`background`, `foreground`, `card`, `muted`, `accent`, `border`, `ring`):
  auto-switch under `.dark`. Use for page/card backgrounds and text.

Selection guide:
| Situation | Level | Example |
|---|---|---|
| Brand surface (always purple) | 1 | `bg-primary-700 text-white` |
| Button / badge (needs dark-mode switch) | 2 | `bg-primary text-primary-foreground` |
| Page / card background | 3 | `bg-background`, `bg-card` |
| Tint background | 1 + dark variant | `bg-primary-50 dark:bg-primary-950` |

## 2. Purple scale (TJ Purple — primary)
| Step | Hex | Tailwind | Note |
|---|---|---|---|
| 50 | `#F7F3FB` | `primary-50` | Alt section background |
| 100 | `#EDE5F5` | `primary-100` | Hover background |
| 200 | `#D9C8EA` | `primary-200` | Light accents |
| 300 | `#BFA3D9` | `primary-300` | Disabled |
| 400 | `#A07AC4` | `primary-400` | Dark-mode semantic primary |
| 500 | `#8254AC` | `primary-500` | Gradient stop |
| 600 | `#6B3F94` | `primary-600` | Primary hover |
| **700** | **`#522C81`** | **`primary-700`** | **Brand primary** |
| 800 | `#47266E` | `primary-800` | Active / pressed |
| 900 | `#3B1F5B` | `primary-900` | — |
| 950 | `#250F3D` | `primary-950` | Deep dark / gradient end |

## 3. Mint scale (TJ Mint — secondary)
| Step | Hex | Tailwind | Note |
|---|---|---|---|
| 50 | `#EFFEFB` | `secondary-50` | Light background |
| 100 | `#C8FFF6` | `secondary-100` | — |
| 200 | `#91FFED` | `secondary-200` | — |
| 300 | `#52F5E1` | `secondary-300` | — |
| 400 | `#1EDECF` | `secondary-400` | Dark-mode semantic secondary |
| 500 | `#00C2B5` | `secondary-500` | — |
| **600** | **`#00A497`** | **`secondary-600`** | **Brand secondary** |
| 700 | `#007D74` | `secondary-700` | Secondary hover |
| 800 | `#06635D` | `secondary-800` | — |
| 900 | `#0A524D` | `secondary-900` | — |
| 950 | `#003230` | `secondary-950` | Deep dark mint |

## 4. Warm neutrals (purple-tinted — not cold grey)
| Step | Hex | Tailwind | Note |
|---|---|---|---|
| 50 | `#FAF9FB` | `warm-50` | Subtle background |
| 100 | `#F4F2F6` | `warm-100` | — |
| 200 | `#EAE7EE` | `warm-200` | Borders |
| 300 | `#D8D3E0` | `warm-300` | — |
| 400 | `#BFB8CA` | `warm-400` | Placeholder text |
| 500 | `#A69DB3` | `warm-500` | — |
| 600 | `#8E839C` | `warm-600` | Secondary text |
| 700 | `#766B84` | `warm-700` | — |
| 800 | `#635A6E` | `warm-800` | — |
| 900 | `#524A5B` | `warm-900` | — |
| **950** | **`#1A1625`** | **`warm-950`** | **Dark sections, footer** |

## 5. Department colors (badges for the 5 disciplines)
| Dept | Hex | Tailwind |
|---|---|---|
| IF — 미래융합 / Future Convergence | `#522C81` | `dept-if` |
| H&S — 인문사회 / Humanities & Social | `#00A497` | `dept-hs` |
| BI — 비즈니스혁신 / Business Innovation | `#2563EB` | `dept-bi` |
| NS — 자연과학 / Natural Sciences | `#EA580C` | `dept-ns` |
| DS&AI — 데이터사이언스 / Data Science & AI | `#7C3AED` | `dept-dsai` |

## 6. Semantic / functional colors
| Type | Hex | Tailwind |
|---|---|---|
| Success | `#00A497` | `success` (= mint) |
| Warning | `#F59E0B` | `warning` |
| Error | `#EF4444` | `error` |
| Info | `#3B82F6` | `info` |

## 7. Layout & component semantic tokens (light → dark)
| Token | Light | Dark | Tailwind |
|---|---|---|---|
| primary | `#522C81` | `#A07AC4` | `bg-primary` |
| primary-foreground | `#FFFFFF` | `#250F3D` | `text-primary-foreground` |
| secondary | `#00A497` | `#1EDECF` | `bg-secondary` |
| secondary-foreground | `#FFFFFF` | `#003230` | `text-secondary-foreground` |
| destructive | `hsl(0 84% 60%)` | `hsl(0 62% 50%)` | `bg-destructive` |
| background | `#FFFFFF` | `hsl(270 15% 8%)` | `bg-background` |
| foreground | `hsl(270 12% 10%)` | `hsl(270 5% 95%)` | `text-foreground` |
| card | `#FFFFFF` | `hsl(270 15% 10%)` | `bg-card` |
| muted | `hsl(270 10% 96%)` | `hsl(270 10% 15%)` | `bg-muted` |
| muted-foreground | `hsl(270 5% 45%)` | `hsl(270 5% 60%)` | `text-muted-foreground` |
| accent | `hsl(270 30% 96%)` | `hsl(270 20% 15%)` | `bg-accent` |
| border | `hsl(270 10% 90%)` | `hsl(270 10% 20%)` | `border-border` |
| ring | `hsl(270 49% 34%)` | `hsl(270 60% 70%)` | `ring-ring` |

## 8. Brand gradients (purple family — driven by lightness, not color mixing)
| Name | Stops | Utility |
|---|---|---|
| Hero | `#522C81` → `#250F3D` (135deg) | `bg-gradient-hero` |
| Text primary | `primary-700` → `primary-500` | `text-gradient-primary` |
| Text mixed | `primary-700` → `secondary-600` | `text-gradient-mixed` (convergence phrases) |
| Hero overlay | `primary-950` 90% → 40% (left→right) | `bg-gradient-hero-overlay` (image heroes) |

## 9. Typography
Font: **Pretendard Variable** (45–920 variable), the only typeface. `word-break: keep-all` and
OpenType `ss01`/`ss02`/`cv01` applied globally for Korean.

```
"Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, system-ui,
"Apple SD Gothic Neo", "Noto Sans KR", sans-serif
```

Scale:
| Class | Size | Use |
|---|---|---|
| `text-7xl` | 72px | Hero headline |
| `text-6xl` | 60px | Page title |
| `text-5xl` | 48px | Large section header |
| `text-4xl` | 36px | Section header |
| `text-3xl` | 30px | Card title |
| `text-2xl` | 24px | Component header |
| `text-xl` | 20px | Lead text |
| `text-lg` | 18px | Large body |
| `text-base` | 16px | Body |
| `text-sm` | 14px | Small / caption |
| `text-xs` | 12px | Label / badge / eyebrow |

Weights: `light` 300 · `normal` 400 · `medium` 500 (nav) · `semibold` 600 (sub-head, eyebrow) ·
`bold` 700 (heading, button) · `extrabold` 800 (hero) · `black` 900 (max impact).

Principles: headings use 700–800 + `tracking-tight`; always responsive
(`text-4xl md:text-5xl lg:text-7xl`); eyebrows are uppercase + `tracking-wider` + `text-secondary-600`;
gradient text only on key words.

## 10. Spacing
Section vertical rhythm is the layout skeleton.
| Use | px | Tailwind |
|---|---|---|
| Small section | 48 | `py-12` |
| Default section | 80 | `py-20` |
| Large section | 96 | `py-24` |
| XL section | 128 | `py-32` |
| Section header margin-bottom | 48 | `mb-12` |
| Card grid gap | 24 | `gap-6` |
| Tight content gap | 16 | `gap-4` |
| Container horizontal pad | 24 | `px-6` |

Container widths: Default `max-w-7xl` (1280px) · Narrow `max-w-5xl` (1024px) · Wide `max-w-[1440px]`.

## 11. Border radius — Sharp Geometry
`--radius` global default is `0`. Right angles are the brand.
| Token | Value | Use |
|---|---|---|
| none | `0` | **Default** — cards, buttons, inputs, sections |
| sm | `2px` | Faintest chips only |
| md | `4px` | shadcn default; use sparingly |
| lg | `8px` | Exceptional large panels |
| full | `9999px` | Avatars, circular icons only |

Using `rounded-lg`/`rounded-xl` on content cards or buttons is a brand violation.

## 12. Elevation
| Level | Treatment | Use |
|---|---|---|
| 0 Flat | 1px border, no shadow | Default cards, inputs, dividers |
| 1 Subtle | border + `shadow-xs` | Lightly-raised cards, outline buttons |
| 2 Floating | soft layered shadow | Menus, modals, dropdowns, sticky header |

Prefer a 1px border + white-on-white surface step over shadow. Animations: `animate-fade-in` /
`animate-slide-up` on `ease-out-expo` cubic-bezier(0.16,1,0.3,1); card grids stagger by index
(`delay i*0.1s`) via Framer Motion.

## 13. Dark mode rule
Raw scales never invert — `primary-700` stays `#522C81` in dark. Only Level-2 and Level-3 semantic
tokens switch (`bg-primary`, `bg-background`, `text-foreground`). For a tint background in both modes,
write it explicitly: `bg-primary-50 dark:bg-primary-950`. Activation is class-based (`.dark`).
