# respoken-apex

The page that serves at **respoken.dev** (the apex domain).

Just the brand fingerprint, centered on the brand mint. No copy,
no nav, no CTA. A quiet "we're here" gesture, deliberately
distinct from the marketing site at [web.respoken.dev](https://web.respoken.dev).

## Stack

One HTML file, one PNG. No build, no JS, no dependencies.
Cloudflare Pages serves it from the edge.

## Deploy

Auto-deploys on push to `main` once the GitHub auto-deploy
connection is wired in the CF Pages dashboard. Until then,
manual deploy:

```sh
cd /Users/josepc/GitHub/respoken-apex
CLOUDFLARE_API_TOKEN="$(cf-personal-token)" \
CLOUDFLARE_ACCOUNT_ID="$(cf-personal-account)" \
  npx wrangler pages deploy . --project-name=respoken-apex --branch=main --commit-dirty=true
```

The `cf-personal-token` / `cf-personal-account` shell wrappers
live in `lab/shell/cloudflare-keychain.sh`.
