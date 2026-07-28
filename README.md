# steeple-pages

The three public pages Apple loads when it checks Steeple's privacy policy, terms
and support URLs.

| page | URL |
|---|---|
| Privacy policy | https://arsh1219.github.io/steeple-pages/privacy |
| Terms of use | https://arsh1219.github.io/steeple-pages/terms |
| Support | https://arsh1219.github.io/steeple-pages/support |

## Do not edit the HTML here by hand

These files are generated. The source is `legal/*.md` in the Steeple app repo,
built with `python3 tool/build_docs.py`. Editing the published HTML directly
means the live page and the app's own copy start describing different apps,
which is the exact failure the 28 July 2026 privacy rewrite existed to fix.

Change `legal/`, rebuild, and republish all of them together.

## Why the pages are plain HTML

Each page is entirely self contained: inline CSS, the system font stack, no
script tag, no image, and no request to any other host. A privacy policy that
pulls a webfont from a third party CDN invites a question you do not want to
answer. `.nojekyll` tells GitHub Pages to serve the files exactly as committed
rather than running them through Jekyll, whose stock themes load CSS and fonts
from other hosts.

## Serving

Pages is served from the root of `main`, not from a `/docs` folder. The app repo
keeps these files under `docs/` because that is where its generator writes them;
this repo holds only the published output, so they sit at the root.
