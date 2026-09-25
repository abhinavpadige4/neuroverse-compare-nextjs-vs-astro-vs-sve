# Astro — Features (2026)

Astro is a content-first, framework-agnostic web framework. In 2026 the
current stable line is **Astro 5.x** (Astro 4.x still widely used). It is the
default choice for content-heavy sites like blogs, docs, and marketing pages.

## Core philosophy

- **Zero JavaScript by default** — Astro ships only the JS needed to hydrate
  interactive "islands".
- **Islands architecture** — each interactive component is hydrated
  independently; the rest of the page is static HTML.
- **Framework-agnostic** — use React, Vue, Svelte, Solid, Preact, Qwik, or
  Alpine components side-by-side in the same page.
- **Content-first** — first-class Markdown, MDX, and content collections.

## Rendering modes

| Mode | Status in 2026 | Notes |
|------|----------------|-------|
| Static Site Generation (SSG) | ✅ Default | `astro build` produces static HTML. |
| Server-Side Rendering (SSR) | ✅ Stable | `output: 'server'` in `astro.config.mjs`. |
| Hybrid (static + SSR) | ✅ Stable | `output: 'hybrid'` — mix static and SSR routes. |
| Client-side rendering (CSR) | ✅ Stable | Via `client:only` directive. |
| View Transitions | ✅ Stable | Built-in SPA-like navigation. |
| Streaming SSR | ✅ Stable | Stream HTML as it renders. |

## Core features

- **File-based routing** with `src/pages/`.
- **Content Collections** — typed, schema-validated content (Zod).
- **Content Layer API** — unified API for local + remote content sources.
- **Markdown & MDX** — first-class, with frontmatter parsing.
- **Astro Components** — `.astro` files with scoped styles and JSX-like syntax.
- **Islands** — `client:load`, `client:visible`, `client:media`,
  `client:idle`, `client:explicit`, `client:only` hydration directives.
- **Server Islands** — render dynamic content on the server without hydrating
  the whole page.
- **Hydration** — fine-grained, per-island.
- **Asset pipeline** — image optimization, font optimization, CSS/JS bundling.
- **Image component** — `<Image />` with automatic AVIF/WebP, lazy loading.
- **Fonts** — `@fontsource` integration, self-hosted fonts.
- **Middleware** — request/response middleware (Astro 5+).
- **API routes** — `src/pages/api/*.ts` for serverless functions.
- **View Transitions** — built-in SPA-like navigation.
- **TypeScript** — first-class, zero-config.
- **ESLint / Prettier** — via `astro check` and community configs.
- **Dev server** — Vite-based, fast HMR.
- **SSR adapters** — deploy to Node, Vercel, Netlify, Cloudflare, AWS, etc.

## Blog-relevant features

- **Markdown** — best-in-class, with frontmatter, syntax highlighting, and
  smartypants.
- **MDX** — first-class, with component imports.
- **Content Collections** — typed blog posts with Zod schemas.
- **RSS** — `@astrojs/rss` integration.
- **Sitemap** — `@astrojs/sitemap` integration.
- **Search** — Pagefind (built-in static search), Algolia, Meilisearch.
- **Comments** — Giscus, Utterances, or custom Server Island.
- **Analytics** — Plausible, Umami, PostHog, Fathom.
- **CMS** — Sanity, Contentful, Strapi, Payload, Ghost, WordPress (via
  `@astrojs/partytown` + API).
- **i18n** — built-in `astro:i18n` config.
- **Syntax highlighting** — Shiki (default), Prism, highlight.js.
- **Smartypants** — automatic typographic quotes and dashes.
- **Remark / Rehype** — full Markdown pipeline customization.

## Performance

- **Lighthouse** — typically 95–100 for static pages.
- **Bundle size** — 0 KB JS for a pure static page; 5–30 KB for a page with
  one interactive island.
- **TTFB** — 20–100 ms on CDN (Cloudflare, Vercel, Netlify).
- **Core Web Vitals** — 71% of Astro sites pass all three (per 2025 web.dev
  data), the highest of any framework.
- **Page weight** — typically 50–150 KB total for a blog post.

## DX (Developer Experience)

- **HMR** — sub-100 ms via Vite.
- **Docs** — excellent, at `docs.astro.build`.
- **Community** — growing fast; ~45k GitHub stars, large npm download count.
- **Learning curve** — low. `.astro` syntax is intuitive; islands are easy to
  grasp.
- **CLI** — `astro init` scaffolds a project in seconds.
- **Type safety** — Content Collections + TypeScript = end-to-end type safety.

## Ecosystem & integrations

- **Auth** — via SSR adapters (Lucia, Better Auth, Supabase Auth).
- **DB** — Drizzle, Prisma, Kysely (via SSR).
- **Payments** — Stripe (via SSR).
- **Styling** — Tailwind CSS, CSS Modules, vanilla-extract, UnoCSS.
- **State** — not needed for static sites; Zustand for islands.
- **Forms** — via SSR + Server Actions (Astro 5+).

## Hosting

- **Cloudflare Pages** — first-class, free tier is generous.
- **Vercel** — first-class, free tier available.
- **Netlify** — first-class, free tier available.
- **GitHub Pages** — supported via `@astrojs/partytown`.
- **Self-hosted** — `astro build` produces static files; serve with any web
  server.
- **AWS** — S3 + CloudFront, or Lambda via SSR adapter.

## Pricing (hosting, 2026)

Astro itself is free and open-source. Pricing depends on the host:

| Host | Free tier | Paid tier |
|------|-----------|-----------|
| Cloudflare Pages | 500 builds/mo, unlimited bandwidth | $5/mo (Pro) |
| Vercel | 100 GB bandwidth, 100 builds/mo | $20/user/mo (Pro) |
| Netlify | 100 GB bandwidth, 300 builds/mo | $19/mo (Pro) |
| GitHub Pages | Free, unlimited bandwidth | Free |
| Self-hosted | Free (your server cost) | Free |

## Limitations for a personal blog

- **SSR is newer** — Astro's SSR is less mature than Next.js's.
- **Ecosystem smaller** — fewer tutorials, fewer Stack Overflow answers.
- **Complex apps** — not ideal for highly interactive apps (dashboards, etc.).
- **Learning curve for islands** — takes time to understand when to use which
  hydration directive.

## Sources

- https://docs.astro.build
- https://astro.build/blog
- https://github.com/withastro/astro
- https://web.dev/articles/vitals
