# capcard-template

Starter template for publishing a Capability Card at:

`/.well-known/capability-card.json`

This template is designed for:

- GitHub Pages
- Vercel
- any static site host

## What You Do

1. Use this template repo.
2. Edit `capcard.config.json`.
3. Optionally add an LLM provider API key as a GitHub secret.
4. Run the `Update Capability Card` GitHub Action.
5. Deploy the repo with GitHub Pages or Vercel.

## Config

Edit:

```json
{
  "openapi_url": "./example-openapi.yaml",
  "provider": "deterministic"
}
```

Provider values:

- `deterministic`
- `auto`
- `anthropic`
- `openai`
- `gemini`

`deterministic` works with no API key.

The template includes `example-openapi.yaml`, so it succeeds immediately before you swap in your real API or MCP spec.

`auto` will use whichever of these GitHub secrets is available:

- `ANTHROPIC_API_KEY`
- `OPENAI_API_KEY`
- `GEMINI_API_KEY`

## GitHub Pages

1. Open `Settings`
2. Open `Pages`
3. Set source to `Deploy from a branch`
4. Select `main` and `/ (root)`
5. Save

After the workflow runs, your card will be live at:

```text
https://<your-domain>/.well-known/capability-card.json
```

## Vercel

1. Import this repo into Vercel.
2. Deploy it as a static site.
3. Optionally connect a custom domain.

The generated `.well-known/capability-card.json` file is already in the repo root, so Vercel can serve it directly.

## Files

- `capcard.config.json` - your source spec and provider choice
- `.github/workflows/update-capability-card.yml` - regenerates the card
- `index.html` - simple landing page
- `.nojekyll` - required for GitHub Pages to preserve `.well-known/`

## Canonical capcard Repo

`https://github.com/Capability-Index/capcard`
