# TAEJAE — Standalone HTML/CSS approach

For mockups and prototypes that open in any browser with no build step. The brand is reproduced with
plain CSS custom properties (the same token values as the codebase) and right-angle geometry.

## How to build
1. Start from `assets/starter.html` (it already links Pretendard, embeds the token sheet, and includes
   a header + hero + one section).
2. Or, in a fresh file, paste the contents of `assets/taejae-tokens.css` into a `<style>` block (or
   `<link>` it) and use `var(--token)` everywhere.
3. Load Pretendard from CDN in `<head>`:
```html
<link rel="stylesheet" as="style" crossorigin
  href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css">
```
4. Keep `lang="ko"` and `word-break: keep-all` on the body for Korean line breaking.

## Core rules in CSS terms
- Body: `background: var(--background); color: var(--foreground); font-family: var(--font);`
- Every surface: `border-radius: 0;` (sharp geometry). Only avatars/icons use `border-radius: 9999px`.
- Cards: `background:#fff; border:1px solid var(--border); padding:24px;` (flat — border before shadow).
- Purple is accent only — hero, CTA, badges, heading emphasis. Never a full-page background.
- Sections alternate: white → `var(--primary-50)` tint → `var(--warm-950)` dark.

## Component classes (paste-ready)
The token sheet ships with these utility classes. Use them directly:

```html
<!-- Section eyebrow + heading -->
<span class="tj-eyebrow">Academy Programs</span>
<h2 class="tj-h2">교육 과정</h2>

<!-- Buttons -->
<button class="tj-btn tj-btn--default">입학 지원하기</button>
<button class="tj-btn tj-btn--secondary">더 알아보기</button>
<button class="tj-btn tj-btn--outline">전체 보기</button>
<button class="tj-btn tj-btn--ghost">자세히</button>

<!-- Card with department badge -->
<div class="tj-card">
  <span class="tj-badge" style="background:var(--dept-if)">IF · 미래융합</span>
  <h4 class="tj-card__title">AI 융합 전략 리더십</h4>
  <p class="tj-card__text">AI 기술을 비즈니스 전략에 융합하는 리더 양성 과정.</p>
</div>

<!-- Sections -->
<section class="tj-section">…</section>              <!-- white -->
<section class="tj-section tj-section--alt">…</section> <!-- pale purple tint -->
<section class="tj-section tj-section--dark">…</section><!-- warm-950 dark -->

<!-- Hero -->
<header class="tj-hero">
  <span class="tj-hero__eyebrow">TAEJAE AI GRADUATE SCHOOL</span>
  <h1 class="tj-hero__title">AI 시대를 선도하는<br>융합형 인재</h1>
  <p class="tj-hero__desc">기술과 인문학을 잇는 융합 교육.</p>
  <a class="tj-btn tj-btn--on-dark">입학 지원하기</a>
</header>

<!-- Grid -->
<div class="tj-grid tj-grid--3">…cards…</div>   <!-- also tj-grid--2, tj-grid--4 -->
```

## Layout skeleton (color-block rhythm)
```html
<body>
  <nav class="tj-nav">…</nav>                       <!-- white sticky, bottom border -->
  <header class="tj-hero">…</header>                <!-- purple gradient -->
  <section class="tj-section tj-section--dark">…</section>  <!-- stats -->
  <section class="tj-section">…</section>           <!-- white -->
  <section class="tj-section tj-section--alt">…</section>   <!-- tint -->
  <section class="tj-cta">…</section>               <!-- purple CTA banner -->
  <footer class="tj-footer">…</footer>              <!-- dark -->
</body>
```

## Type & spacing reminders
- Headings: heavy weight + tight tracking, responsive via `clamp()`. The sheet's `.tj-h1/.tj-h2/.tj-h3`
  already do this.
- Section padding 48 / 80 / 96 / 128px (`.tj-section` defaults to 80px).
- Container max-width 1180–1280px, centered, `padding: 0 32px`.

For the full value tables see `tokens.md`. If you need a richer reference of every component rendered,
the companion `design-system-taejae.html` showcase demonstrates them visually.
