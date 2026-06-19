# TAEJAE — Next.js + Tailwind v4 patterns

The real codebase: **Next.js 15 (App Router), TypeScript strict, Tailwind CSS v4 (`@theme inline`),
shadcn/ui (New York), Pretendard Variable, Framer Motion, Lucide icons.** Frontend-only — data lives
in `localStorage`; never add `app/api/`, `"use server"`, a DB, or external API calls.

## Hard rules (these are enforced by `npm run check:tokens`)
1. No backend/API — `localStorage` only.
2. No hardcoded hex — `bg-[#522C81]`, inline `style={{color}}` forbidden. Use tokens.
3. No Tailwind default palette — `bg-purple-500`, `bg-gray-100` forbidden. Use `primary-*`,
   `secondary-*`, `warm-*`.
4. No rounded corners — `rounded-lg`/`rounded-xl`/`rounded-md` forbidden. Brand default is
   `rounded-none` (sharp geometry).
5. No font changes — Pretendard Variable is the global default (`font-sans`).
6. No bypassing layout components — never write `max-w-7xl mx-auto px-6` by hand; use `<Container>` /
   `<Section>`.
7. No inverting raw scales in dark mode — `primary-700` is always `#522C81`; only semantic tokens switch.

Import alias is `@/`. Example: `import { Button } from "@/components/ui/button"`.

## The `@theme inline` token block (globals.css, Tailwind v4)
Tokens are declared as CSS custom properties inside `@theme inline { … }`, which makes them available
as Tailwind utilities. Raw scales (`--color-primary-700: #522c81;` …), then shadcn semantic tokens,
then layout tokens, with `.dark { … }` overriding only the semantic/layout ones. The full table is in
`tokens.md`. Sharp geometry: `--radius: 0rem`. Useful custom utilities already defined:
`text-gradient-primary`, `text-gradient-mixed`, `bg-gradient-hero`, `bg-gradient-hero-overlay`,
`bg-section-alt`, `bg-section-dark`, `animate-fade-in`, `animate-slide-up`.

## Layout components
```tsx
<Container size="default|narrow|wide|full">…</Container>   // width wrapper, px-6
<Section variant="default|alt|dark|primary|gradient" spacing="sm|md|lg|xl">…</Section>
<PageHeader title="" description="" breadcrumbs={[{label,href}]} variant="default|primary" />
<Header />   // sticky white nav, bottom border
<Footer />   // dark warm-950, multi-column
```
- `Section variant`: `default`=white, `alt`=`primary-50` tint, `dark`=`warm-950`, `primary`=`primary-700`.

## Feature components
```tsx
<HeroSection variant="default|overlay|split"
  title="AI 시대를 선도하는 융합형 인재" subtitle="TAEJAE AI GRADUATE SCHOOL"
  description="" primaryCTA={{label,href}} secondaryCTA={{label,href}}
  backgroundImage="/images/campus.jpg" />

<CourseCard title="" description="" department="IF|H&S|BI|NS|DS&AI"
  tags={["리더십"]} duration="2학기" image="" href="" />

<ProfileCard name="" title="" department="IF" image="" quote="" specialties={[]} />

<StatsGrid stats={[{value:"95",label:"취업률",suffix:"%"}]} variant="default|primary|dark" />

<CTABanner title="" description="" primaryCTA={{label,href}} variant="primary|dark|mint" />

<AcademyGrid title="" subtitle="" courses={[{title,description,department,href}]} columns={2|3|4} />

<AnnouncementBar message="" href="" linkText="" variant="primary|mint|dark" dismissible />
<TimelineSection steps={[]} />  <TestimonialCard … />  <NewsCard variant="default|horizontal" … />
```

## Buttons (shadcn/ui, sharp)
```tsx
<Button>입학 지원하기</Button>                         {/* default: bg-primary text-primary-foreground */}
<Button variant="secondary">더 알아보기</Button>        {/* mint */}
<Button variant="outline">전체 보기</Button>
<Button variant="ghost">자세히</Button>
<Button variant="link">바로가기</Button>
<Button variant="destructive">삭제</Button>
<Button size="sm|default|lg|icon">…</Button>
```
All buttons are right-angled (`rounded-none` via the token). Hover: `primary/90`, `secondary/80`.

## Forms
`<LoginForm>`, `<RegisterForm>`, `<EnrollmentForm courseName="">`, `<ContactForm>`, `<PrivacyConsent>`.
Inputs are sharp, border `--color-input`, focus ring `--color-ring` (purple).

## Typical page
```tsx
import { Header } from "@/components/layout/Header";
import { Footer } from "@/components/layout/Footer";
import { Section } from "@/components/layout/Section";
import { Container } from "@/components/layout/Container";
import { HeroSection } from "@/components/features/HeroSection";

export default function Page() {
  return (
    <>
      <Header />
      <main>
        <HeroSection title="AI 시대를 선도하는 융합형 인재"
          subtitle="TAEJAE AI GRADUATE SCHOOL"
          primaryCTA={{ label: "입학 지원하기", href: "/admissions" }} />
        <Section>
          <Container>
            <span className="mb-2 inline-block text-sm font-semibold uppercase tracking-wider text-secondary-600">
              Academy Programs
            </span>
            <h2 className="text-3xl font-bold tracking-tight md:text-4xl">교육 과정</h2>
            <div className="mt-12 grid gap-6 md:grid-cols-2 lg:grid-cols-3">{/* CourseCards */}</div>
          </Container>
        </Section>
        <Section variant="alt"><Container>{/* tint section */}</Container></Section>
        <CTABanner title="AI 시대의 리더가 되어보세요" primaryCTA={{label:"상담 신청",href:"/admissions"}} variant="primary" />
      </main>
      <Footer />
    </>
  );
}
```

## Section header pattern (use everywhere)
```tsx
<span className="mb-2 inline-block text-sm font-semibold uppercase tracking-wider text-secondary-600">
  English Eyebrow
</span>
<h2 className="text-3xl font-bold tracking-tight md:text-4xl">한국어 제목</h2>
```

## Animation pattern (Framer Motion card grid)
```tsx
{items.map((item, i) => (
  <motion.div key={item.id} initial={{ opacity: 0, y: 20 }} whileInView={{ opacity: 1, y: 0 }}
    viewport={{ once: true }} transition={{ duration: 0.5, delay: i * 0.1 }}>
    <CourseCard {...item} />
  </motion.div>
))}
```

If the components above don't exist yet in the target project, build them with the same tokens and the
sharp-geometry rule — or fall back to plain Tailwind utilities using the token classes
(`bg-primary-700`, `text-secondary-600`, `bg-warm-950`, `border-warm-200`, `rounded-none`).
