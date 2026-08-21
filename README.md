# drinks.zellmerhomes.com

The guest cocktail menu. Published with GitHub Pages from the repo root.

## What this repo is

A single generated page. `index.html` is written by `build.py`, which lives one
directory up and is **not** part of this repo. Do not edit `index.html` by hand —
the next build overwrites it.

To change the menu, edit `data/drinks.json` in the parent project, run
`python3 build.py`, then commit whatever `index.html` becomes.

## What this repo is not

It is not the bar book. The book holds bottle prices, tasting notes, drink ratings
by name, and written palate profiles for real people. It stays in the parent
directory, outside this repo, permanently.

This repo is public — GitHub Pages requires that on the free tier — and a public
repo is browsable file-by-file regardless of any `noindex` meta tag. There is no
"unlisted" here. Hence the deny-by-default `.gitignore`: four files are allowed,
everything else is refused.

`build.py` also runs a `guard()` before writing, which aborts if a name, pronoun,
score or price reaches the rendered page. Three locks: directory separation,
`.gitignore`, and the guard.

## Custom domain

`CNAME` tells GitHub Pages the domain. That alone is not enough — the subdomain
also needs a DNS `CNAME` record at the registrar pointing `drinks` at
`<username>.github.io`. Without it the domain will not resolve, and the symptom
is a GitHub 404 rather than a DNS error, which is confusing.

Once the QR code is printed, this URL is permanent. Changing it later means
reprinting every code.
