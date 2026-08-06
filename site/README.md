# juliemarino.nyc — static site

Rebuild of Julie Marino's playwright site as a plain static site for GitHub Pages.
No build step, no CMS, no dependencies — every page is a hand-editable HTML file.

## Structure

```
index.html                        Home (hero, play cards, Off Book teaser)
plays/index.html                  Plays overview + licensing at a glance
plays/welcome-to-paradise/        Play page: synopsis, trailer, history, licensing
plays/steamboat-willie/           Play page: in development
in-the-works/index.html           New & in-progress work (static display for now)
about/index.html                  Bio, past projects, representation
off-book/index.html               Off Book collection
off-book/*/index.html             Individual reading and listening pages
contact/index.html                Consolidated contact / representation / licensing
privacy-policy/index.html         Privacy policy (rewritten for a static site)
404.html                          Not-found page (GitHub Pages serves this automatically)
assets/style.css                  Site-wide stylesheet (palette + type live here)
assets/julie-portrait-paprika.png Portrait
assets/img/                       Posters, production photos, favicon
```

## Legacy URL redirects

Old WordPress URLs are preserved via meta-refresh redirect stubs:

- `/welcome-to-paradise/` → `/plays/welcome-to-paradise/` (Theatrical Rights Worldwide links to the old URL)
- `/the-writers-salon/` → `/off-book/`
- `/privacy-policy/` — same URL as before, no redirect needed

## Deploying

Pushing to `main` runs `.github/workflows/deploy-pages.yml`, which publishes the
contents of this `site/` directory to GitHub Pages. `.nojekyll` is included so
GitHub serves the files as-is. The custom domain is recorded in `CNAME`.

## Editing notes

- Colors and fonts are CSS variables at the top of `assets/style.css`
  (turmeric and paprika; Fraunces + Inter).
- The header/nav and footer are repeated in each HTML file, so a change to either
  must be applied consistently across the content pages.
