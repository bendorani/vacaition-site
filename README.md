# Vacaition — GitHub Pages (free legal pages)

Static site for **privacy** and **terms** until `vacaition.app` is live on the Phase 0 VM.

## URLs (after Pages is enabled)

| Page | Path | Example |
|------|------|---------|
| Home | `/` | `https://bendorani.github.io/app/` |
| Privacy | `/privacy/` | `https://bendorani.github.io/app/privacy/` |
| Terms | `/terms/` | `https://bendorani.github.io/app/terms/` |

Use the **Privacy** URL in App Store Connect / Play Console until DNS points to the VM.  
At launch, move to `https://vacaition.app/privacy` (Caddy + frontend or static files on the VM).

## Enable GitHub Pages (one-time)

1. GitHub → **bendorani/app** → **Settings** → **Pages**
2. **Build and deployment** → Source: **Deploy from a branch**
3. Branch: **main**, folder: **/docs**
4. Save — site goes live in ~1–2 minutes

Or via CLI (if you have `gh` auth):

```bash
gh api repos/bendorani/app/pages -X POST \
  -f 'build_type=legacy' \
  -f 'source[branch]=main' \
  -f 'source[path]=/docs'
```

## Source of truth

Markdown drafts live in `apps/mobile/marketing/store/`:

- `privacy-policy.md`
- `terms.md`

When you edit policy text, update both the markdown draft and the matching `docs/*/index.html`.
