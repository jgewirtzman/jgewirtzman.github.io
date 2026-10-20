# jongewirtzman.com

Source for Jon Gewirtzman's academic website, built with [Quarto](https://quarto.org) and published with GitHub Pages.

- Pages: `index.qmd`, `research.qmd`, `teaching.qmd`, `contact.qmd`
- Styling: `styles.scss` (theme variables), `styles.css` (layout, collapsible sections, galleries)
- Images: `images/` (leads and icons), `images/gallery/`

## Publishing

Every push to `main` runs `.github/workflows/publish.yml`, which checks out the private CV repository (`jgewirtzman/jgewirtzman-cv`), builds `cv-public.tex` into `files/Gewirtzman_CV.pdf`, renders the site, and deploys `docs/` to GitHub Pages. The CV PDF is never committed here; the workflow needs a `SITE_CV_TOKEN` secret with read access to the CV repository.

## Local preview

```sh
quarto preview
```

`files/Gewirtzman_CV.pdf` is ignored by git; build it locally with `latexmk cv-public.tex` in the CV repository and copy it in if you want the link to work in a local preview.
