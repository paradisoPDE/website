# paradiso PDE — website

Static HTML site for the indie band **paradiso PDE**. No frameworks, no build step — just HTML and a single shared CSS file. Open any `.html` in a browser, or host the folder on GitHub Pages.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Redirects to the home page (so GitHub Pages serves it at the root URL) |
| `paradiso-PDE-home.html` | Landing page with Spotify embed |
| `paradiso-PDE-bio.html` | Band story + members |
| `paradiso-PDE-shows.html` | Upcoming + past gigs |
| `paradiso-PDE-music.html` | Spotify embed + release list |
| `paradiso-PDE-video.html` | Music videos and live takes |
| `paradiso-PDE-merch.html` | Vinyl, tees, prints |
| `paradiso-PDE-press.html` | Quotes, press shots, press kit |
| `paradiso-PDE-blog.html` | News + newsletter signup |
| `paradiso-PDE-contact.html` | Email + contact form |
| `style.css` | Shared styles |

## Run locally

Just double-click `index.html` — it opens in your default browser. No server needed.

## Deploy to GitHub Pages

1. Create a new public repo on GitHub (e.g. `paradiso-pde-site`).
2. From this folder, push the files:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/paradiso-pde-site.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. Wait ~1 minute. Your site is live at `https://<your-username>.github.io/paradiso-pde-site/`.

To use a custom domain (e.g. `paradisopde.com`), add a `CNAME` file containing only your domain name, and configure DNS per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Replacing placeholders with real content

The site uses CSS gradient blocks (`<div class="ph">…</div>`) wherever a real photo or video would go. To swap in real media:

**Images** — replace:
```html
<div class="ph">Band portrait · placeholder</div>
```
with:
```html
<img src="images/band-portrait.jpg" alt="paradiso PDE" />
```

**Videos** — replace a `<div class="ph wide">` inside an `.embed.embed-video` wrapper with a YouTube/Vimeo iframe:
```html
<iframe src="https://www.youtube.com/embed/VIDEO_ID"
        allowfullscreen frameborder="0"></iframe>
```

Drop images into an `images/` subfolder and reference them with relative paths.

## Editing copy

Almost all text lives inside each `.html` file. There is no templating layer — edit headings, paragraphs, and lists directly. Navigation lives in the `<nav class="site-nav">` block at the top of each page; if you add a page, update the nav in all nine files.

## Links wired in

- Spotify artist: `https://open.spotify.com/artist/08rzidI7HeLZCssOCMhvsW`
- Instagram: `https://www.instagram.com/paradiso_parade/`

Email addresses (`hello@`, `booking@`, `press@`, `store@paradiso-pde.example`) are placeholders — swap for real ones before launch.

## Design

Layout and tone: warm off-white background, generous whitespace, serif headings on a sans-serif body, full-width imagery, and `* * *` dividers between sections. The accent colour (used on the `PDE` mark and on hover states) is a muted terracotta. All styling is in `style.css` — change the CSS custom properties at the top of that file to retheme the whole site in seconds.
