# TAEJAE Design System

The brand design system for **TAEJAE University AI Graduate School** (태재대학교 AI미래전략대학원), plus a
Claude skill that generates on-brand UI for you.

The brand in one paragraph: a **white-dominant canvas** where **TJ Purple `#522C81`** is a strategic
**accent only** (heroes, CTAs, badges, headings — never a background flood), **TJ Mint `#00A497`** is the
**interaction** color (links, hovers, success, secondary CTAs, eyebrows), neutrals are **warm and
purple-tinted**, every surface is a **right angle** (sharp geometry, `border-radius: 0`), and the only
typeface is **Pretendard Variable**. Sections alternate white → pale purple tint → dark to build rhythm.

---

## Repository map

```
.
├── design-system/
│   ├── design-system-taejae.md     # Full spec: tokens, type, components, do's & don'ts
│   └── design-system-taejae.html   # Visual showcase — open in a browser
├── skill/
│   └── taejae-design-system.skill  # Installable skill package (for manual install)
├── plugins/
│   └── taejae-design-system/       # Same skill, as a Claude Code plugin
│       ├── .claude-plugin/plugin.json
│       └── skills/taejae-design-system/   (SKILL.md, references/, assets/)
└── .claude-plugin/marketplace.json # Makes this repo an installable marketplace
```

---

## Use the design system

No install needed.

- **View it**: open [`design-system/design-system-taejae.html`](design-system/design-system-taejae.html)
  in any browser — rendered color swatches, type specimens, buttons, cards, spacing, radius, and more.
- **Read the spec**: [`design-system/design-system-taejae.md`](design-system/design-system-taejae.md)
  has every token (color scales, typography, spacing, radius, gradients, department colors), the
  component catalog, and the do's & don'ts.

---

## Install the skill

The skill makes Claude design in the TAEJAE brand. Say something like *"태재 스타일로 랜딩페이지 만들어줘"*
or *"make this card look like TAEJAE"* and it produces Next.js + Tailwind v4 code or a standalone HTML
mockup that follows the brand rules.

### Option A — Claude Code, one-line install from this repo (recommended)

```
/plugin marketplace add soominKim/taejae-design-system
/plugin install taejae-design-system
```

Then reload plugins if needed (`/reload-plugins`). The skill activates automatically when you ask for
TAEJAE-branded design work.

### Option B — Install the `.skill` file

**Easiest — just ask Claude (natural language).** In Claude Code, paste a request like this:

> Install the TAEJAE design-system skill. Download this .skill file and unzip it into
> ~/.claude/skills/taejae-design-system/ so that SKILL.md ends up at
> ~/.claude/skills/taejae-design-system/SKILL.md, then confirm it's discovered:
> https://raw.githubusercontent.com/soominKim/taejae-design-system/main/skill/taejae-design-system.skill

Claude fetches the file, unzips it to the right place, and the skill is auto-discovered.

**Or do it by hand.** On GitHub, open
[`skill/taejae-design-system.skill`](skill/taejae-design-system.skill) and click **Download** (the file
preview looks blank because it's a binary zip — that's normal, it's ~16 KB, not empty). Then:

- **Claude Code**: unzip it into `~/.claude/skills/taejae-design-system/` (so `SKILL.md` sits at
  `~/.claude/skills/taejae-design-system/SKILL.md`). It's auto-discovered.
- **Claude desktop / Cowork**: Customize → Skills → **+**, and add the `.skill` file.

> Direct download (raw) URL, if you need it:
> `https://raw.githubusercontent.com/soominKim/taejae-design-system/main/skill/taejae-design-system.skill`

---

## What the skill enforces

- Purple is an accent, never a full-page background.
- Mint is for interaction only.
- Sharp geometry — no rounded corners on cards or buttons.
- Tokens only — no raw hex, no Tailwind default palette.
- One typeface — Pretendard Variable.
- Restrained depth — a 1px border before any shadow.

See [`plugins/taejae-design-system/skills/taejae-design-system/SKILL.md`](plugins/taejae-design-system/skills/taejae-design-system/SKILL.md)
and its `references/` for the full token tables, the Next.js component patterns, and the HTML approach.

---

## License

MIT — see [`LICENSE`](LICENSE).
