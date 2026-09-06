# Personal research website — Ruthu Hulikal Rooparaghunath

Static site. No build step, no dependencies. Open `index.html` in a browser.

```
website/
├── index.html          about + news preview + highlighted publications
├── news.html           full news list
├── publications.html   all publications, grouped by year, with a live filter box
├── cv.html             full CV + PDF download button
├── style.css           all styling (accent colour is one variable at the top)
└── assets/
    ├── Ruthu_Rooparaghunath_CV.pdf
    └── img/            put profile.jpg and paper thumbnails here
```

## To view locally

Just double-click `index.html`, or for a proper local server:

```bash
cd website && python3 -m http.server 8000   # then open http://localhost:8000
```

## TODO before publishing

- [ ] Add `assets/img/profile.jpg`, then in `index.html` delete the
      `.profile-photo-placeholder` div and uncomment the `<img class="profile-photo">` line right below it.
- [ ] Add paper thumbnails to `assets/img/` (e.g. `hiervision.png`) and replace each
      `.pub-thumb-placeholder` div with `<img src="assets/img/hiervision.png" alt="" class="pub-thumb">`.
- [ ] Fill in the real GitHub URL in `index.html` (marked `<!-- TODO -->`). LinkedIn is set.
- [ ] Add a link to your UvA staff page if you have one (all other external links were checked and resolve).
- [ ] Add a project page or repo links if you want the video-anomaly-detection work visible before it's published.
- [ ] Once the site is live, fill in the two commented-out `og:url` / `og:image` meta tags in each
      page's `<head>` (replace `USERNAME`) so shared links preview with your photo.

## A note on fonts

The page loads Nunito Sans from Google Fonts. With no internet it falls back to the system
sans-serif stack and still looks fine — only the exact typeface changes. If you want it fully
self-contained, download the font into `assets/` and swap the `<link>` for an `@font-face` rule.

## To put it online (GitHub Pages)

1. Create a public repo named `<your-github-username>.github.io`.
2. From this folder:

```bash
git init
git add .
git commit -m "Personal research website"
git branch -M main
git remote add origin https://github.com/<username>/<username>.github.io.git
git push -u origin main
```

3. In the repo: Settings → Pages → Source: `main` branch, `/ (root)`.
4. It goes live at `https://<username>.github.io` within a minute or two.

Everything is relative paths, so it works from a subdirectory too
(`https://<username>.github.io/website/`) if you'd rather not use the root repo.

## Changing the look

The accent colour is the first line of `:root` in `style.css`:

```css
--accent: #0f766e;   /* teal */
```

Change that one hex value and every link, hover state and active nav item follows.
