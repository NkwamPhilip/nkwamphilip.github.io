# nkwamphilip.github.io

Personal research site — Philip Nkwam. Static: one HTML file, nine images, no build step
and no dependencies. Google Fonts is the only external request.

```
index.html      the whole site (styles and script inline)
img/            photographs
.nojekyll       tells GitHub Pages to serve the files as-is
```

## Publish to GitHub Pages

1. On GitHub, create a **public** repository named exactly `nkwamphilip.github.io`
   under the `NkwamPhilip` account. Don't add a README, .gitignore or licence.
2. From this folder:

```bash
git init -b main
git add .
git commit -m "Research site"
git remote add origin https://github.com/NkwamPhilip/nkwamphilip.github.io.git
git push -u origin main
```

The site goes live at <https://nkwamphilip.github.io/> within a minute or two. For a
user site GitHub Pages turns itself on automatically from the default branch — no
settings to change. If it hasn't appeared after five minutes, check
Settings → Pages shows "Deploy from a branch", branch `main`, folder `/ (root)`.

## Updating it later

Edit `index.html`, then:

```bash
git add . && git commit -m "Update" && git push
```

## Editing notes

- **Colours and fonts** are CSS custom properties in the `:root` block at the top of
  `<style>`. Both light and dark themes are defined there; change a token once and it
  propagates. Dark values appear twice on purpose (a `prefers-color-scheme` block and a
  `[data-theme="dark"]` block) so the manual toggle works in both directions.
- **Publications** live in the `PUBS` array in the script near the bottom. Each entry is
  `{t: title, a: authors, v: venue, em: emphasis, u: url, k: [filter keys], badge: ...}`.
  Filter keys are `peer`, `review`, `first`, `senior`. Add an entry and it appears
  automatically, numbering and counts included.
- **Figure 1** is a simulation, not patient data. The phantom is defined in SUVR units
  (white matter reference = 1.00, cortical ribbon peaks at 1.50, ventricles = 0.25).
  Noise is Poisson, approximated by a Gaussian, measured inside the dashed reference ROI
  so the readout reflects counting statistics rather than anatomy — it scales as
  1/sqrt(dose), which is the point of the figure. `COUNTS_AT_UNITY` sets the full-dose
  noise level (1200 counts gives ~2.9%).
- **Photo captions** are `data-cap` and `data-sub` attributes on each `<figure>`; the
  lightbox reads them.
