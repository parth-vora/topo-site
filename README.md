# Topo — public site

The support page, privacy policy and terms for the Topo app.

These pages are **generated**, not written here. The source is the markdown in
`legal/` in the app repository, converted by `scripts/build-legal.mjs`. Editing
the HTML directly means the next build overwrites it.

To change a policy:

```
# in the app repository
vim legal/privacy-policy.md
npm run publish:site
```

That rebuilds the HTML, commits it, and pushes this directory to the public
repository that GitHub Pages serves.

## Why this is a separate repository

The app repository holds the database schema, every row-level security policy
and forty-odd migrations whose comments describe each weakness found and fixed.
None of that is secret in the sense that a key is — the security is the
policies themselves, not their obscurity — but publishing it hands anyone a map
of where to probe, and the only thing gained would be free hosting for three
static pages.

So the app stays private and this holds the pages, which are public by
definition: the App Store requires the privacy policy at a URL anyone can open.
