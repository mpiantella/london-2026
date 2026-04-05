# london-2026

Trip guide as a static site (**Hugo** + [Pico CSS](https://picocss.com/)), tuned for phone use: bottom navigation, **Google Maps** buttons, and copy that treats restaurant lists as **alternatives** (see [Shared](content/shared.md)).

**Live site (after deploy):** [https://mpiantella.github.io/london-2026/](https://mpiantella.github.io/london-2026/)

## Edit the guide

- **Home:** [content/_index.md](content/_index.md)
- **Repeats / home base:** [content/shared.md](content/shared.md)
- **Each day:** [content/days/](content/days/) — filenames `friday.md` … `wednesday.md`
- **Map buttons:** `{{< maps "Place Name" >}}` shortcode in any page ([layouts/shortcodes/maps.html](layouts/shortcodes/maps.html))
- **Internal links:** use `{{< relref "shared.md" >}}` (or the right path) so links work on GitHub Pages under `/london-2026/`.

Front matter on day pages includes `short` (nav label) and `weight` (order).

## Preview locally

Install [Hugo](https://gohugo.io/) (0.120+), then:

```bash
hugo server -D
```

Open the URL shown (usually [http://localhost:1313/london-2026/](http://localhost:1313/london-2026/) — path matches `baseURL` in [hugo.toml](hugo.toml)).

## Deploy (GitHub Pages)

1. Repo **Settings → Pages**: **Build and deployment** → Source: **GitHub Actions**.
2. Push to `main`; the [workflow](.github/workflows/hugo.yml) builds with Hugo and deploys `public/`.
3. If the repo or username changes, update `baseURL` in [hugo.toml](hugo.toml) to `https://<user>.github.io/<repo>/`.

## PDFs

Original exports can stay in the repo for reference; the site content lives in `content/` only.
