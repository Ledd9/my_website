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
off-book/index.html               Off Book (formerly The Writers' Salon)
contact/index.html                Consolidated contact / representation / licensing
privacy-policy/index.html         Privacy policy (rewritten for a static site)
404.html                          Not-found page (GitHub Pages serves this automatically)
assets/style.css                  Site-wide stylesheet (palette + type live here)
assets/julie-portrait.jpeg        Portrait
assets/img/                       Posters, production photos, favicon
```

## Legacy URL redirects

Old WordPress URLs are preserved via meta-refresh redirect stubs:

- `/welcome-to-paradise/` → `/plays/welcome-to-paradise/` (Theatrical Rights Worldwide links to the old URL)
- `/the-writers-salon/` → `/off-book/`
- `/privacy-policy/` — same URL as before, no redirect needed

## Before going live

1. **Archive**: copy the existing static archive into an `archive/` folder at the
   repo root — the footer links to `archive/index.html` on every page.
2. **Domain**: add a `CNAME` file containing `juliemarino.nyc` (GitHub Pages
   settings → custom domain does this for you).
3. **og:image URLs**: the Open Graph image tags point at
   `https://juliemarino.nyc/assets/img/...` — correct once the domain points at
   GitHub Pages; update if the domain changes.

## Deploying

Push this folder's contents to the root of a GitHub repository, then enable
GitHub Pages (Settings → Pages → deploy from branch → `main` / root).
`.nojekyll` is included so GitHub serves files as-is.

## Editing notes

- Colors and fonts are CSS variables at the top of `assets/style.css`
  (Pantone 1245C gold base, aubergine/violet/teal accents; Space Grotesk + Inter).
- The rotating hero taglines are the small `<script>` at the bottom of `index.html`.
- The header/nav and footer are repeated in each HTML file — a change to either
  must be applied to every page (there are 9 content pages).
