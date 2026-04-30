# inaaya.site — Monorepo

Two sites, both built with [Astro](https://astro.build) and deployed to **Cloudflare Workers**.

| Site | URL | Directory |
|---|---|---|
| Personal portfolio | `https://inaaya.site` | `apps/inaaya/` |
| Sports photography | `https://shotby.inaaya.site` | `apps/shotby/` |

## Stack

- **Framework**: [Astro](https://astro.build) with [`@astrojs/cloudflare`](https://docs.astro.build/en/guides/integrations-guide/cloudflare/) adapter
- **Deployment**: [Cloudflare Workers](https://workers.cloudflare.com/) via [Wrangler](https://developers.cloudflare.com/workers/wrangler/)
- **Monorepo**: npm workspaces

## Local development

```bash
# Install all dependencies
npm install

# Start the personal portfolio dev server (http://localhost:4321)
npm run dev:inaaya

# Start the sports photography dev server (http://localhost:4322)
npm run dev:shotby
```

## Building

```bash
# Build both sites
npm run build

# Or individually
npm run build:inaaya
npm run build:shotby
```

## Deployment

Each app has a `wrangler.toml` configured with:
- `name` — the Worker name
- `main` — Astro's generated `dist/_worker.js`
- `[assets]` — serves the `dist/` directory as static assets

```bash
# Deploy both sites
npm run deploy

# Or individually
npm run deploy:inaaya
npm run deploy:shotby
```

> **Note:** You must be logged in with `npx wrangler login` before deploying.
> DNS for `shotby.inaaya.site` should point to the `shotby-inaaya-site` Worker.
