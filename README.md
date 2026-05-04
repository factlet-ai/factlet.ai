# factlet.ai

The website for the [Factlet Protocol](https://github.com/factlet-ai). Hosted on Cloudflare Pages.

## Pages

- `index.html` — landing page
- `protocol.html` — v0.1 specification
- `getting-started.html` — three copy-paste prompts to try the protocol in any LLM
- `styles.css` — shared stylesheet

## Architecture

Plain HTML + CSS, no build step, no JavaScript. Cloudflare Pages serves the directory root directly.

For Phase 2 (proper docs site), candidates: Astro, Hugo, VitePress, MkDocs Material.

## Deploy

Pushes to `main` auto-deploy via the Cloudflare Pages git integration.

## License

MIT
