# ai-testing-tool.github.io

Public user guide for **Testing tool** (Marketplace: AI Testing Tool), published at [https://ai-testing-tool.github.io/](https://ai-testing-tool.github.io/).

GitHub Pages publishes the **`docs/`** folder on `main` with the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme (`remote_theme`). Site chrome lives under `docs/`:

- `_config.yml` — theme + site settings
- `_data/navigation.yml` — masthead + sidebar
- `assets/img/logo.png` — masthead logo

Guide markdown is synced from `qanalyzer-app/docs/user-guide/` (do not edit guide pages here long-term).

## Preview locally

```bash
bundle install
bundle exec jekyll serve --source docs
```

Open http://127.0.0.1:4000/

## Publishing

1. From `qanalyzer-app`: `npm run docs:sync-github-pages -- --apply`
2. Commit and push this repo’s `main` to publish.
