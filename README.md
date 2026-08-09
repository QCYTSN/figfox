# FigFox public site

This repository is the GitHub Pages deployment mirror for FigFox.
It publishes the generated static site at:

`https://qcytsn.github.io/figfox/`

## Source of truth

All product development happens in
[`QCYTSN/autodraftman-product`](https://github.com/QCYTSN/autodraftman-product).
Do not edit product features directly in this repository.

The `site/` directory is the deployable output built from that product source
with its GitHub Pages base path. A commit to `main` deploys `site/` directly.

The older root-level frontend files are retained as historical material only and
are no longer part of the Pages build. Public FigFox output lives only in `site/`.

## Update procedure

1. In `autodraftman-product/frontend`, run `npm run build:pages`.
2. Copy the generated `dist/` contents into this repository's `site/` directory.
3. Commit and push the resulting `site/` changes here.
