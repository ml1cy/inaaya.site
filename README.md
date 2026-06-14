# Inaaya – Sports Photography Portfolio

A personal sports photography portfolio built with [Astro](https://astro.build) and deployed to **Cloudflare Workers**. 

This repository was originally a monorepo containing two separate websites, but has been flattened into a unified application combining the layout and aesthetic of the personal site with the sports photography content.

## Stack

- **Framework**: [Astro](https://astro.build) with [`@astrojs/cloudflare`](https://docs.astro.build/en/guides/integrations-guide/cloudflare/) adapter
- **Styling**: Custom CSS (Vanilla)
- **Deployment**: [Cloudflare Workers](https://workers.cloudflare.com/) via [Wrangler](https://developers.cloudflare.com/workers/wrangler/)

## Local development

```bash
# Install all dependencies
npm install

# Start the dev server (http://localhost:4321)
npm run dev
```

## Building

```bash
# Build the site for production
npm run build
```

## Deployment

The application uses `wrangler.toml` configured with:
- `name` — the Worker name
- `main` — Astro's Cloudflare entrypoint `@astrojs/cloudflare/entrypoints/server`
- `[assets]` — serves the `dist/` directory as static assets

```bash
# Log in from a headless terminal/container
npx wrangler login --browser false

# Deploy the site to Cloudflare
npm run deploy
```
