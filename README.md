# Health Command Center

A privacy-safe GitHub Pages shell for Hermes-generated health summaries.

## Important privacy note

GitHub Pages is usually public. Do **not** publish raw Garmin data, nutrition logs, health metrics, location-bearing activities, or medical details unless you intentionally want them public.

Recommended pattern:

- Public page: sanitized daily status, simple recommendation, non-sensitive goals.
- Private Hermes files: `/opt/data/health/nutrition.md`, Garmin exports, detailed logs.

## Local preview

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` from the machine running the server.

## GitHub Pages setup

Once GitHub auth is available in Hermes, create/push this repo and enable Pages from the `main` branch root:

```bash
git init
git branch -M main
git add .
git commit -m "feat: create health command center"
gh repo create health-command-center --public --source . --push
# In GitHub UI: Settings → Pages → Deploy from branch → main / root
```

If using the API instead of `gh`, the repo needs GitHub token scopes for repository contents and Pages administration.

## Updating the dashboard

Edit `data.json` for simple text updates. The page loads it dynamically.
