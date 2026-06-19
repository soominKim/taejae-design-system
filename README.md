# TAEJAE Design System

🌐 **English** · [**한국어**](#-한국어-korean)  — _click to jump; the Korean section is a collapsible toggle._

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

- **Live preview (no download)**: open the rendered showcase right in your browser →
  **[design-system-taejae.html (live)](https://raw.githack.com/soominKim/taejae-design-system/main/design-system/design-system-taejae.html)**
  _(once GitHub Pages is enabled, it's also at
  https://soominkim.github.io/taejae-design-system/design-system/design-system-taejae.html )_
- **View it locally**: open [`design-system/design-system-taejae.html`](design-system/design-system-taejae.html)
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

**Easiest — just ask Claude (natural language).** In Claude Code, paste a request like this (copy it
as-is):

> Install the TAEJAE design-system skill from this repo: https://github.com/soominKim/taejae-design-system
> Download the file `skill/taejae-design-system.skill` from the repo
> (raw URL: https://raw.githubusercontent.com/soominKim/taejae-design-system/main/skill/taejae-design-system.skill),
> then unzip it into `~/.claude/skills/taejae-design-system/` so that `SKILL.md` ends up at
> `~/.claude/skills/taejae-design-system/SKILL.md`. Then confirm the skill is discovered.

Claude fetches the file, unzips it to the right place, and the skill is auto-discovered — no manual steps.

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

---

## 🇰🇷 한국어 (Korean)

<details>
<summary><b>한국어 안내 펼치기 / 접기 (click to expand)</b></summary>

<br>

**TAEJAE University AI Graduate School**(태재대학교 AI미래전략대학원)의 브랜드 디자인 시스템과, 이 브랜드에
맞춰 UI를 만들어 주는 Claude 스킬입니다.

한 문단 요약: **화이트 중심 캔버스** 위에서 **TJ Purple `#522C81`** 은 히어로·CTA·뱃지·헤딩에만 쓰는
**전략적 액센트**(배경을 보라로 가득 채우지 않음), **TJ Mint `#00A497`** 은 링크·호버·성공·세컨더리 CTA·
영문 eyebrow에 쓰는 **인터랙션 색**입니다. 뉴트럴은 **보라 언더톤의 따뜻한 그레이**, 모든 표면은
**직각**(Sharp Geometry, `border-radius: 0`), 서체는 **Pretendard Variable** 하나뿐입니다. 섹션은
화이트 → 연보라 틴트 → 다크를 번갈아 깔아 리듬을 만듭니다.

### 레포 구성

```
.
├── design-system/
│   ├── design-system-taejae.md     # 전체 스펙: 토큰, 타이포, 컴포넌트, Do/Don't
│   └── design-system-taejae.html   # 시각 쇼케이스 — 브라우저에서 열기
├── skill/
│   └── taejae-design-system.skill  # 설치형 스킬 패키지(수동 설치용)
├── plugins/
│   └── taejae-design-system/       # 같은 스킬, Claude Code 플러그인 형태
└── .claude-plugin/marketplace.json # 이 레포를 설치형 마켓플레이스로 만드는 매니페스트
```

### 디자인 시스템 사용 (설치 불필요)

- **라이브 미리보기(다운로드 없이)**: 브라우저에서 렌더링된 쇼케이스 바로 열기 →
  **[design-system-taejae.html (live)](https://raw.githack.com/soominKim/taejae-design-system/main/design-system/design-system-taejae.html)**
  _(GitHub Pages를 켜면
  https://soominkim.github.io/taejae-design-system/design-system/design-system-taejae.html 에서도 열립니다)_
- **로컬에서 보기**: [`design-system/design-system-taejae.html`](design-system/design-system-taejae.html) 를
  브라우저로 열면 색 스와치·타입·버튼·카드·스페이싱·라디우스가 렌더링됩니다.
- **스펙 읽기**: [`design-system/design-system-taejae.md`](design-system/design-system-taejae.md) 에 모든
  토큰(색 스케일, 타이포, 스페이싱, 라디우스, 그라데이션, 학과색), 컴포넌트 카탈로그, Do/Don't가 있습니다.

### 스킬 설치

스킬을 깔면 Claude가 태재 브랜드로 디자인합니다. *"태재 스타일로 랜딩페이지 만들어줘"* 처럼 말하면
규칙에 맞는 Next.js + Tailwind v4 코드나 단독 HTML 목업을 만들어 줍니다.

**방법 A — Claude Code, 한 줄 설치(추천)**
```
/plugin marketplace add soominKim/taejae-design-system
/plugin install taejae-design-system
```
필요하면 `/reload-plugins`. 태재 디자인 작업을 요청하면 스킬이 자동으로 활성화됩니다.

**방법 B — `.skill` 파일 설치**

가장 쉬운 방법은 **Claude에게 자연어로 부탁**하는 것입니다. Claude Code에 이렇게 붙여넣으세요:

> 태재 디자인 시스템 스킬을 설치해줘. 이 레포의 `.skill` 파일을 받아서 깔면 돼:
> https://raw.githubusercontent.com/soominKim/taejae-design-system/main/skill/taejae-design-system.skill
> `~/.claude/skills/taejae-design-system/` 에 압축을 풀어서 SKILL.md가
> `~/.claude/skills/taejae-design-system/SKILL.md` 에 오도록 해줘. 설치되면 확인해줘.

직접 받으려면 GitHub에서 [`skill/taejae-design-system.skill`](skill/taejae-design-system.skill) 을 열고
**Download** 클릭(미리보기가 비어 보이는 건 바이너리 zip이라 정상이며 ~16KB입니다). 그다음:
- **Claude Code**: `~/.claude/skills/taejae-design-system/` 에 압축 해제(`SKILL.md`가 그 안에 오도록).
- **Claude 데스크톱 / Cowork**: Customize → Skills → **+** 로 `.skill` 파일 추가.

### 스킬이 강제하는 브랜드 규칙
- 보라는 액센트, 전체 배경 금지
- 민트는 인터랙션 전용
- Sharp Geometry — 카드·버튼에 둥근 모서리 금지
- 토큰만 사용 — 원시 hex·Tailwind 기본 팔레트 금지
- 서체는 Pretendard Variable 하나
- 절제된 깊이 — 그림자보다 1px 보더 우선

### 라이선스
MIT — [`LICENSE`](LICENSE) 참고.

</details>
