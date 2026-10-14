# nkwamphilip.github.io

Personal research site — Philip Nkwam. Static: one HTML file, a folder of photos, no build
step and no dependencies. Google Fonts is the only external request.

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

- **Look**: dark, terminal-style, one page. Colours and fonts are CSS custom properties in
  the `:root` block at the top of `<style>` (JetBrains Mono for structure, Work Sans for
  reading). There is no light theme.
- **Sections** are numbered `01`–`10` in the HTML; the script renumbers whichever are
  visible, so adding or removing a section keeps the numbers in order.
- **Links**: every person and organisation named in running text is an `<a class="hl">`
  (mono) or `<a class="lk">` (body font) with a dotted underline. UCL people link to their
  `profiles.ucl.ac.uk` pages.
- **Features** (`#features`) holds press about you; the first card is the highlighted one.
- **Story** (`#story`) is the photo timeline. Each chapter is an `<li>` with a
  `.ph-row` of `<figure class="ph" style="--ar:W/H">`. Set `--ar` to the photo's
  width ÷ height and the row's `--sum` to the total of its `--ar` values; photos in a row
  then come out the same height. Add `pair` to two portraits that should sit side by side
  on a phone. The lightbox walks every story photo in page order.
- **Academic view** (`?view=academic`, the header button) hides the hero, about, story,
  skills, experience and impact, and shows the short bio in `.ac-hero` followed by
  publications, projects, features, news and contact.
- **CV**: drop a file named `cv.pdf` in this folder and the `cv.pdf` buttons appear on
  their own; without it they stay hidden.
- **Portrait**: `img/portrait.jpg` is a square crop of `phil.png` (the desk photo with the PET
  scans on screen). `img/lowdose-pet.png` is the low-dose PET slice used for that project.
