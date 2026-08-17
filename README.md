# BulkSKU for WooCommerce — Validation Landing Page

A dependency-free static landing page to validate demand for BulkSKU before building the plugin.

## What this is

A GitHub Pages-hosted page that:
- Explains the product honestly (planned MVP, not shipping yet)
- Has an interactive local demo (no network calls, mock data)
- Shows $39 one-time pricing
- Has a CTA that is explicitly disabled until a real checkout URL is set

## Repository structure

```
index.html                    ← entire site (single file, no dependencies)
.github/
  workflows/
    deploy-pages.yml          ← GitHub Actions Pages deployment (not active yet)
README.md
```

## Before you publish

1. **Get a Lemon Squeezy checkout URL** for a $39 product.
2. In `index.html`, find the line:
   ```js
   const CHECKOUT_URL = null;
   ```
   Replace `null` with your verified URL in quotes:
   ```js
   const CHECKOUT_URL = "https://your-store.lemonsqueezy.com/buy/your-product-id";
   ```
3. **Enable GitHub Pages** in repo Settings → Pages → Source: GitHub Actions.
4. Push to `main`. The workflow deploys automatically.

## Development

No build step. Open `index.html` directly in a browser:

```sh
open index.html
# or
npx serve .
```

## Mock catalogue (demo only)

The interactive demo uses a hard-coded product list in `index.html` (search for `MOCK_CATALOGUE`).
It does not make network requests. All validation is local to the browser.

## License

© BulkSKU. All rights reserved. This repository contains the validation landing page only.
No plugin source code is included.
