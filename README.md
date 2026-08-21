# drinks.zellmerhomes.com

The guest menu. One file, no dependencies, no external requests, no analytics.
This is what the QR code points at.

## What is here, and what is deliberately not

`index.html` is generated — it is a copy of `../menu.html`, which
`../build_menu.py` builds from the private `../bar-book.html`. Do not hand-edit
it; the next build overwrites it.

The bar book itself is **not in this repository and must not be**. It names a
real person seventeen times, records her ratings and palate, and lists bottle
prices. GitHub Pages on the free tier requires a public repository, and a
public repository is browsable file by file regardless of any `noindex` tag —
so "unlisted" is not a thing that exists here. The `.gitignore` denies
everything by default for that reason.

## Updating the menu

From the parent directory, after editing `bar-book.html` or `ratings.json`:

    python3 apply_ratings.py
    python3 build_menu.py
    cp menu.html site/index.html
    cd site && git add -A && git commit -m "menu" && git push

Pages redeploys in about a minute.

## The QR code is permanent

A printed QR code cannot be recalled. It points at `drinks.zellmerhomes.com`,
a domain Rich controls, rather than at a hosting provider's URL — so if the
host ever changes, every card already printed keeps working. Do not reprint
codes against any other hostname.
