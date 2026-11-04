# Documentation verification

This procedure builds the study's documentation. It uses a disposable checkout because the build generates files. It performs no research recalculation, source verification or deployment. [Build configuration](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/mkdocs.yml), [workflow](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/.github/workflows/deploy-mkdocs.yml).

## Environment

Use Python 3.11, matching the [workflow](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/.github/workflows/deploy-mkdocs.yml). Install the declared MkDocs, Material, Glightbox and PyMdown requirements. Their lower bounds allow dependency versions to vary between installations. Record the installed versions with each review. [Requirements](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/requirements.txt).

```sh
python3.11 -m venv .venv
. .venv/bin/activate
python -m pip install -r requirements.txt
python -m pip freeze > /tmp/rgds-study-build-environment.txt
```

## Build locally

From the repository root:

```sh
build_dir=$(mktemp -d)
python -m mkdocs build --clean --site-dir "$build_dir/site"
test -s "$build_dir/site/index.html"
```

Expected output: MkDocs completes the documentation build and writes `index.html` under the temporary site directory. Review any warnings before drawing conclusions about link health. The repository contains historical navigation and reference paths whose rendering needs separate inspection. [Configuration](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/mkdocs.yml), [bibliography](references/bibliography.md).

A successful build establishes that the selected documentation toolchain generated HTML. It leaves source accuracy, calculation validity, current regulatory applicability and empirical effects to the [substantive review](current-review.md).

## Deployment boundary

The existing workflow deploys GitHub Pages after a main-branch push. This draft supplies a local build procedure. Publishing the study remains a separate action. [Deployment workflow](https://github.com/node-and-norm/rgds-independent-study/blob/6eeb02601440380dda990f2a097eb92164d66558/.github/workflows/deploy-mkdocs.yml).
