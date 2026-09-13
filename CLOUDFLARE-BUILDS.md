# Parmis — Cloudflare Workers Builds

## Recommended Cloudflare Workers Builds settings

- **Root directory:** `/`
- **Install command:** leave empty (Cloudflare automatically runs npm install), or use `npm install --no-audit --no-fund`
- **Build command:** `npm run build`
- **Deploy command:** `npx wrangler deploy`
- **Node.js version:** `20` or newer

Do not use `npm ci` unless a package-lock.json generated from this exact package.json exists.

## Local verification

```bash
npm install
npm run build
npx wrangler deploy
```

The Worker entry point is `worker.js`, configured in `wrangler.jsonc`.
