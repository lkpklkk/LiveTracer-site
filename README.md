# LiveTracer website

Static pages for LiveTracer, hosted on GitHub Pages. No build step: the repo root is the site.
It shares its look with the [RangeBuddy site](https://github.com/lkpklkk/RangeBuddy-site).

| Page | Purpose |
|---|---|
| `/` | Home: what LiveTracer does, with links to the other pages |
| `/support/` | App Store Connect support URL: getting started, questions, contact |
| `/privacy/` | App Store Connect privacy policy URL (camera, microphone, motion, location, add to Photos) |
| `/get/` | Where links and QR codes lead; forwards to the App Store once `TARGET` is set |

## Publish on GitHub Pages

1. Push this folder to a public GitHub repo (the repo name becomes the path:
   `https://<username>.github.io/<repo>/`).
2. Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`.
3. `.nojekyll` makes Pages serve the files as they are.

The RangeBuddy site still has its own copies at `livetracer/` and `livetracer/privacy/`. Once this
site is live and App Store Connect points here, replace those pages with links to it.

## Before publishing

- The support address (`keplee99@gmail.com`) appears in every page; change them together.
- Check the "Last updated" date on the privacy page.
- `get/index.html`: leave `TARGET` empty until there is somewhere to send people; the page then
  shows "Coming soon". Set it to the App Store link at launch. Query parameters on the `/get/` URL
  are passed through to the target.
- Re-check the privacy page whenever the app adds a permission, network access or in-app purchases.

## Where things come from

- `assets/site.css`: the brand tokens from the brand guide (`docs/architecture/brand.md` in the
  GolfApps repo; Original theme, light and dark, Increase Contrast) in an iOS grouped-list layout,
  copied from the RangeBuddy site. Text sizes are in rem; on iOS Safari they follow Dynamic Type.
- LiveTracer has no logo yet, so the banner writes "LiveTracer" in Merriweather and there is no
  favicon. Don't invent one (brand guide); add the real assets here when they exist.
- Copy: the title and subtitle are the app's welcome lines (brand guide, 2026-11-19).
- `assets/fonts/`: Merriweather 400 and 700, Latin subset (SIL OFL, `OFL.txt`), served from this
  site so the pages make no third-party requests.

## Preview locally

```bash
python3 -m http.server 8774 --directory .
```

Then open `http://localhost:8774/`.
