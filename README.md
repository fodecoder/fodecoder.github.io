# Andrea Simone Foderaro — CV site

Live at **https://fodecoder.github.io/**

The whole site is `index.html`: plain HTML and CSS, a few lines of JavaScript, and no build step or dependencies. GitHub Pages serves it straight from the `master` branch, repo root.

## Files

```
index.html            the site
assets/               CV in PDF
docs/                 avatar and favicon
my-resume/index.html  redirect for the old address
404.html              redirect for old deep links, plain 404 for everything else
```

Until October 2026 the site lived at `https://fodecoder.github.io/my-resume/`. Links shared before the move still work:

- `/my-resume/` is a small page with a meta refresh to the root.
- Any other missing path under `/my-resume/` lands on `404.html`, which sends the browser to the same path without the prefix (`/my-resume/assets/…pdf` goes to `/assets/…pdf`).

Both are client-side redirects, since GitHub Pages can't send a real 301.

## Editing

Colors, fonts and spacing are CSS custom properties in `:root` at the top of the `<style>` block. Dark mode follows `prefers-color-scheme`, and there's a print stylesheet, so check Ctrl+P after layout changes.

## Projects section

Each project is an `<article class="card">` inside `.projects-list`. Cards are ordered by how much they say about backend work, not by date.

The links go in a `<p class="card-links">` placed after the tag list (`.card-stack`), which keeps them lined up at the bottom of every card. External links open in a new tab, with `rel="noopener noreferrer"` and an `aria-label` like `fanta-helper on GitHub (opens in new tab)`.

- Only link repos that are public and not empty. Check before adding one.
- When the code can't be shown, write `<span class="card-meta">Code not public</span>` in the link row instead.
- Small or old repos don't get a card. They go in the "Earlier and smaller work" line under the grid.
- To link a post in the Writing section, give its `<details>` an `id` and link to `#that-id`. The script at the bottom of the page opens the post when someone lands on it.
