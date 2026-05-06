# factlet.ai

The website for the [Factlet Protocol](https://github.com/factlet-ai). Hosted on Cloudflare Pages (git-connected).

## Pages

- `index.html` — landing page
- `protocol.html` / `protocol/index.html` — v0.1 specification
- `getting-started.html` / `getting-started/index.html` — copy-paste prompts to try the protocol in any LLM
- `evals.html` / `evals/index.html` — open eval suite summary (links to github.com/factlet-ai/evals)
- `about/index.html` — about Nora and the Factlet Protocol

## Assets and config

- `styles.css` — shared stylesheet
- `favicon.svg` — site favicon
- `og-home.png`, `og-protocol.png`, `og-getting-started.png` — Open Graph social card images per page
- `docs/social-preview.png` — additional preview asset
- `llms.txt` — site summary in [llmstxt.org](https://llmstxt.org) format for LLM-discoverable indexing (the protocol's own audience)
- `_redirects` — Cloudflare redirect rules (non-trailing-slash → trailing-slash for directory pages)

## Architecture

Plain HTML + CSS, no build step. The only JavaScript is a small inline snippet in `getting-started/index.html` that wires the copy-to-clipboard buttons on the prompt boxes — no framework, no bundler, no external scripts. Cloudflare Pages serves the directory root directly.

For Phase 2 (proper docs site), candidates: Astro, Hugo, VitePress, MkDocs Material.

## Deploy

**Pushes to `main` auto-deploy via the Cloudflare Pages git integration** — verified working as of 2026-05-06. First push lands at `<commit-hash>.factlet-ai.pages.dev` for preview; the `main`-branch deploy serves at the production custom domain `factlet.ai`. Typical deploy time: ~30-60s.

History: this project was originally created as Direct Upload (Cloudflare's drag-and-drop deploy mode), which CANNOT be retroactively connected to Git. Migrated 2026-05-06 to a new git-connected Pages project with the `factlet.ai` custom domain attached. See `factlet-ai:f001` in [factlet-ai/factbook](https://github.com/factlet-ai/factbook) for the lesson learned.

For new Cloudflare Pages projects: ALWAYS choose "Connect to Git" at creation, never "Direct Upload" — the latter is one-way.

## License

MIT
