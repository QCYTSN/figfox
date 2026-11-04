# FigFox public site

[Open FigFox](https://qcytsn.github.io/figfox/).

Production builds come exclusively from a reviewed, full commit SHA in
[QCYTSN/autodraftman-product](https://github.com/QCYTSN/autodraftman-product).
This repository owns the GitHub Pages workflow. Historical `site/` and root-level
frontend files are archives, not production build inputs. Ordinary pushes here
do not publish the site.

## Publish a reviewed version

1. Build and check the product source following its
   [deployment guide](https://github.com/QCYTSN/autodraftman-product/blob/codex/figfox-complete-redesign/deploy/README.md).
2. Commit and push the checked source, including exported public assets.
3. From that source checkout run `node deploy/publish-pages.mjs <full-source-SHA>`.
   Alternatively dispatch this repository's Pages workflow with the required
   `source_revision` input set to the same full 40-character commit SHA.
4. The workflow checks out that exact source commit, verifies HEAD, installs locked
   dependencies and builds `frontend/dist` for `/figfox/`. `_release.json` records
   the actual checked-out SHA and workflow run.
5. Wait for deployment, confirm the live `_release.json`, and inspect the site.

The workflow template is versioned at `deploy/pages-workflow.yml` in the source
repository. Install reviewed workflow changes here before releasing.
To roll back, explicitly dispatch a previously reviewed source SHA.
