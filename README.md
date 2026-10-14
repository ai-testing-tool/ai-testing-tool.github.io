# ai-testing-tool.github.io

Public user guide for **Testing tool** (Marketplace: AI Testing Tool), published at [https://ai-testing-tool.github.io/](https://ai-testing-tool.github.io/).

GitHub Pages builds from the **root** of `main` with the [Minimal](https://github.com/pages-themes/minimal) Jekyll theme. Guide pages live under `docs/` and are synced from the Forge app source of truth:

`qanalyzer-app/docs/user-guide` → this repo’s `docs/`

## Preview locally

```bash
bundle install
bundle exec jekyll serve
```

Open http://127.0.0.1:4000/

## Re-sync guide content

From `qanalyzer-app`:

```bash
# Dry-run
npm run docs:sync-github-pages

# Write into ../ai-testing-tool-github-io/docs/
npm run docs:sync-github-pages -- --apply
```

Then commit and push this repo when you are ready to publish.
