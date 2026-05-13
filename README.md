# Zaden Maestas — Portfolio

[![Deploy](https://github.com/ZadenMaestas/zaden.dev/actions/workflows/deploy.yml/badge.svg)](https://github.com/ZadenMaestas/zaden.dev/actions/workflows/deploy.yml)

Personal portfolio and blog live at [zaden.dev](https://zaden.dev).

---

## Stack

| Layer | Technology |
|---|---|
| Framework | [Astro 6](https://astro.build/) |
| Language | TypeScript |
| Styling | Vanilla CSS (scoped component styles) |
| Icons | [astro-icon](https://github.com/natemoo-re/astro-icon) + custom SVGs |
| Font | Lato (Google Fonts) |
| Package manager | [Bun](https://bun.sh/) |
| Deployment | [Cloudflare Pages](https://pages.cloudflare.com/) via [wrangler-action](https://github.com/cloudflare/wrangler-action) |

## Getting Started

**Prerequisites:** Bun ≥ 1.0 ([install](https://bun.sh/docs/installation))

```bash
bun install
bun run dev
```

The dev server starts at `http://localhost:4321`.

## Commands

| Command | Action |
|---|---|
| `bun run dev` | Start dev server at `localhost:4321` |
| `bun run build` | Build for production to `./dist/` |
| `bun run preview` | Preview the production build locally |
| `bun run lint` | Run ESLint |

## Project Structure

```
src/
├── components/       # Reusable Astro components (NavBar, Footer, etc.)
├── layouts/
│   ├── Main.astro    # Base HTML shell + global styles
│   └── BlogPost.astro # Layout for individual blog posts
├── pages/
│   ├── index.astro   # Homepage
│   ├── blog.astro    # Blog listing
│   └── posts/        # Markdown blog posts
├── styles/
│   └── global.css    # Global resets and utility classes
└── icons/            # SVG icon assets
```

## Deployment

Pushes to `main` or `master` trigger the [Deploy workflow](.github/workflows/deploy.yml), which:

1. Installs dependencies with Bun
2. Builds the site with `astro build`
3. Deploys `./dist` to Cloudflare Pages via Wrangler

Required repository secrets:

| Secret | Description |
|---|---|
| `CLOUDFLARE_API_TOKEN` | Cloudflare API token with Pages edit permissions |
| `CLOUDFLARE_ACCOUNT_ID` | Cloudflare account ID |
