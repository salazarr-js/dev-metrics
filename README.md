# dev-metrics

Personal Jira + GitHub dashboard. See `PLAN.md` for the full design.

## Quick start

```bash
pnpm install
cp .env.example .env        # fill in tokens
pnpm sync                   # pull data -> public/data.json
pnpm dev                    # open http://localhost:5173
```

## Scripts

| Command | What it does |
|---|---|
| `pnpm dev` | Vite dev server + `/api/update` middleware |
| `pnpm sync` | CLI sync: runs the same code the Refresh button calls |
| `pnpm build` | Type-check + static build into `dist/` |
| `pnpm typecheck` | `vue-tsc --noEmit` |

## Tokens

- **Jira**: https://id.atlassian.com/manage-profile/security/api-tokens
- **GitHub**: https://github.com/settings/tokens - scopes `repo`, `read:org`

Put them in `.env` (gitignored). Never commit tokens.

## Layout

- `src/server/` - TS files run by `tsx` (CLI) and loaded by Vite middleware
- `src/web/` - Vue 3 dashboard
- `public/data.json` - what the UI reads (written by `sync`)
- `data/raw.json` - raw API snapshot (gitignored, debug-friendly)

## Current state

Phase 1: scaffold. Shows setup status only - no metrics yet.
