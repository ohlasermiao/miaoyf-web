# Screenshots

Drop your real screenshots here, then they'll show up in the "Under the hood" section.

## Expected files

| Filename | What it shows | Replaces placeholder |
|----------|---------------|----------------------|
| `railway.png`  | Railway deployment dashboard (service running, logs) | "Railway deployment" |
| `supabase.png` | Supabase table editor (`subscriptions` / `members`) | "Supabase database" |
| `discord.png`  | A slash command in Discord (e.g. `/info` or `/approve` result) | "Discord commands" |

## How to wire them in

In `index.html`, inside the `#screenshots` section, replace each
`<div class="shot__placeholder">…</div>` with an image, e.g.:

```html
<figure class="shot">
  <img src="assets/screenshots/railway.png" alt="Railway deployment dashboard" />
  <figcaption>Always-on deployment on Railway.</figcaption>
</figure>
```

Recommended size: ~1600×1000 px (16:10), compressed PNG or JPG under ~300 KB each.
Crop out anything sensitive (real member names, tokens, transaction IDs) before uploading.
