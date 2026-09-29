# maksymvavilov.github.io

Personal site — freelance Kubernetes platform engineering.
Live at <https://maksymvavilov.github.io>.

## How it works

Plain HTML and CSS. No build step, no dependencies, no framework. What's in the
repo is exactly what gets served. `.nojekyll` tells GitHub Pages to skip its
Jekyll build and publish the files as-is.

```
index.html              the whole site — one page
assets/css/style.css    all the styling
assets/img/             photo and logo
favicon.ico             browser tab icon
references/             source material (gitignored, never published)
```

## Making changes

Edit `index.html`, commit, push to `main`. GitHub Pages picks it up within a
minute or two.

To preview locally before pushing, either open `index.html` in a browser, or
serve it properly so root-relative paths behave the same as in production:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Where things live in `index.html`

Each section is marked with an `id` matching its nav link — `#services`,
`#how`, `#track-record`, `#public-work`, `#contact`. The colour scheme comes
from the `MV` logo and is defined once at the top of `style.css`, in the
`:root` block; dark mode overrides sit right below it.

The email address is assembled in JavaScript at the bottom of `index.html` so
it isn't sitting in the page source for scrapers. There's a `<noscript>`
fallback for anyone browsing without JS.
