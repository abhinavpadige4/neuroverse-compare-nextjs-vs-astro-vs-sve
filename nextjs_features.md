# Next.js — Features (2026)

Next.js is the React-based full-stack framework maintained by Vercel. In 2026 the
current stable line is **Next.js 15.x** (with Next.js 16 in early access for
some users). It is the most mature of the three frameworks compared here and
the default choice for teams that already know React.

## Rendering modes

| Mode | Status in 2026 | Notes |
|------|----------------|-------|
| Static Site Generation (SSG) | ✅ Stable | `export const dynamic = 'error'` + `next build` produces a fully static export. |
| Server-Side Rendering (SSR) | ✅ Stable | Runs on Node.js runtime on Vercel, or on any Node host. |
| Incremental Static Regeneration (ISR) | ✅ Stable | `revalidate: 60` etc. Still the go-to for blogs with frequent updates. |
| Partial Prerendering (PPR) | ✅ Stable in 15.x | Splits a page into a static shell + dynamic islands. Big win for blogs with dynamic sidebars. |
| Client-side rendering (CSR) | ✅ Stable | Via `'use client'` islands. |
| React Server Components (RSC) | ✅ Stable | Default for new pages. Server components can read DBs directly. |

## Core features

- **File-based routing** with `app/` directory (App Router) and legacy `pages/`.
- **Middleware** (`middleware.ts`) for edge-side auth, redirects, A/B tests.
- **Route Handlers** for API endpoints (`app/api/*/route.ts`).
- **Server Actions** — mutate data from forms without writing an API.
- **Image Optimization** — `next/image` with automatic AVIF/WebP, lazy loading,
  responsive srcsets, and CDN caching.
- **Fonts** — `next/font` self-hosts Google Fonts and optimizes them.
- **Metadata API** — declarative SEO (`export const metadata`).
- **Caching** — `fetch` caching, `React.cache`, `unstable_cache`, and the new
  **Data Cache** in 15.x.
- **Turbopack** — default dev bundler in 15.x; ~10× faster HMR than Webpack.
  Webpack still used for production builds (Turbopack prod is beta).
- **TypeScript** — first-class, zero-config.
- **ESLint / Prettier** — built-in linter via `next lint`.
- **Taint tracking** — experimental XSS protection for Server Actions.
- **View Transitions** — built-in page transitions API.
- **Caching headers** — `Cache-Control` and `s-maxage` helpers.
- **Edge runtime** — run middleware and route handlers on V8 isolates.
- **PWA support** — via `next-pwa` community plugin (not built-in).

## Blog-relevant features

- **MDX** — first-class support via `@next/mdx` or `next-mdx-remote`.
- **RSS / sitemap** — via `next-sitemap` and `@actions/rss`.
- **Search** — Algolia DocSearch, Meilisearch, or Typesense integrations.
- **Comments** — Giscus, Utterances, or custom Server Action + DB.
- **Analytics** — Vercel Analytics, PostHog, Plausible, Umami.
- **CMS** — Sanity, Contentful, Strapi, Payload, Ghost, WordPress (via WPGraphQL).
- **i18n** — built-in `next-intl` and `i18n` config in `next.config.js`.

## Performance

- **Lighthouse** — typically 90–100 for static pages, 70–90 for SSR pages.
- **Bundle size** — React + Next.js runtime is ~45–90 KB gzipped for a minimal
  page. Larger than Astro's zero-JS default.
- **TTFB** — 50–200 ms on Vercel edge; 100–400 ms on self-hosted Node.
- **Core Web Vitals** — 35–55% of Next.js sites pass all three (per 2025
  web.dev data), mainly because of React hydration cost.

## DX (Developer Experience)

- **HMR** — sub-100 ms with Turbopack.
- **Docs** — best-in-class, at `nextjs.org/docs`.
- **Community** — largest React ecosystem; ~100k GitHub stars, huge npm
  download count, huge tutorial ecosystem.
- **Learning curve** — moderate to steep. RSC, Server Actions, and the
  App Router mental model take time to internalize.
- **CLI** — `create-next-app` scaffolds a project in seconds.

## Ecosystem & integrations

- **Auth** — NextAuth.js (Auth.js), Clerk, Supabase Auth, Lucia.
- **DB** — Prisma, Drizzle, Kysely, Mongoose, PlanetScale.
- **Payments** — Stripe (with official `@stripe/next-js`).
- **Styling** — Tailwind CSS, CSS Modules, styled-jsx, vanilla-extract.
- **State** — Zustand, Jotai, TanStack Query, Redux Toolkit.
- **Forms** — React Hook Form, TanStack Form, Zod.

## Hosting

- **Vercel** — first-party, best DX. Free tier: 100 GB bandwidth, 100 builds/mo.
- **Netlify** — supported, but some Vercel-only features (Edge Middleware,
  Fluid Compute) don't work.
- **Cloudflare Pages** — supported with limitations (no Edge Middleware).
- **Self-hosted** — `next start` on any Node 18+ server. Docker image available.
- **AWS** — ECS, Lambda (via `@vercel/nft`), or Amplify.

## Pricing (Vercel, 2026)

| Plan | Price | Bandwidth | Builds |
|------|-------|-----------|--------|
| Hobby | Free | 100 GB | 100/mo |
| Pro | $20/user/mo | 500 GB | Unlimited |
| Team | $20/user/mo | 500 GB | Unlimited + SSO |
| Enterprise | Custom | Custom | Custom |

## Limitations for a personal blog

- **Overkill** — a personal blog rarely needs SSR, Server Actions, or edge
  middleware.
- **Bundle weight** — React runtime is always shipped unless you use RSC
  aggressively.
- **Build times** — large blogs (500+ posts) can take 2–5 minutes to build.
- **Lock-in** — some features (Fluid Compute, Edge Middleware) only work on
  Vercel.

## Sources

- https://nextjs.org/docs
- https://nextjs.org/blog
- https://vercel.com/pricing
- https://web.dev/articles/vitals
