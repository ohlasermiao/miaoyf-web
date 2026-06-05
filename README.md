# RolePilot — product website

The marketing site for **RolePilot**, a Discord role & membership management bot.
Plain static HTML/CSS/JS — no build step, no backend, no dependencies.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire single-page site + SEO meta + JSON-LD structured data |
| `style.css` | All styling (theme via CSS variables at the top — edit there to re-skin) |
| `script.js` | Tiny vanilla JS: mobile nav toggle only |
| `assets/logo.svg` | Wordmark logo |
| `assets/favicon.svg` | Browser tab icon |
| `assets/og-image.svg` | Social-share preview image |
| `assets/screenshots/` | Drop real screenshots here — see that folder's README |
| `CNAME` | Custom domain for GitHub Pages (`miaoyf.com`); harmless on Vercel/Netlify |

## Preview locally

```bash
cd miaoyf-web
python3 -m http.server 8080
# open http://localhost:8080
```

## Edit the content

- **Text & sections** → `index.html` (everything is plain HTML, clearly sectioned with comments).
- **Colors / spacing** → the `:root { … }` block at the top of `style.css`. The accent color is `--blurple`.
- **Screenshots** → see `assets/screenshots/README.md`.
- **Add an email contact** → in `index.html`, the `#contact` section currently shows only Discord.
  To add an email, duplicate the `.contact__card` block and put your address inside.

## Deploy to miaoyf.com

All three options are zero-build static hosting. Pick one.

### Option A — Vercel (easiest custom domain)
1. Push this folder to a GitHub repo.
2. In Vercel, **Add New → Project → Import** that repo.
   Framework Preset: **Other**. Build command: *(none)*. Output dir: *(root)*.
3. Project → **Settings → Domains → Add** `miaoyf.com`, then update DNS at your
   registrar as Vercel instructs (usually an A record + a `www` CNAME).

### Option B — GitHub Pages (CNAME already included)
1. Push this folder to a GitHub repo (e.g. `miaoyf-web`).
2. Repo **Settings → Pages → Source**: deploy from `main`, root (`/`).
3. The included `CNAME` file already contains `miaoyf.com`. At your registrar, add a
   `CNAME` record for `www` → `<username>.github.io`, and the four GitHub Pages
   `A` records for the apex `miaoyf.com`
   (`185.199.108.153`, `.109.153`, `.110.153`, `.111.153`).

### Option C — Netlify
1. Drag-and-drop this folder onto the Netlify dashboard (or connect the GitHub repo).
2. No build command needed. Publish directory: root.
3. **Domain settings → Add custom domain** `miaoyf.com`, follow the DNS instructions.

DNS changes can take a few minutes to a few hours to propagate. HTTPS certificates are
issued automatically by all three platforms once DNS resolves.
