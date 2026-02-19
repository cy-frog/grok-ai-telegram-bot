# Grok AI Telegram Bot Docs Site

Production-ready static docs/marketing website for a community Grok bot in Telegram.

Live site:
- `https://cy-frog.github.io/grok-ai-telegram-bot/`
- Russian version: `https://cy-frog.github.io/grok-ai-telegram-bot/ru/`

Primary bot link:
- `https://t.me/grok_ai_telegram_bot`

Channel link:
- `https://t.me/cyber_frog_ai`

## What This Project Is
This repository contains a fully static multi-page website focused on:
- Product onboarding (`Start Here`)
- Trust pages (`Status`, `Pricing`, `Privacy`, `FAQ`, `Changelog`)
- Editorial long-form article (`musk-durov-grok-telegram.html`)
- Visual product proof via real screenshots (`assets/evidence/`)
- EN/RU localization with dedicated page paths

No framework, no build step, no backend. Plain HTML + CSS + small inline JS for carousel behavior.

## Key Features
- Neon-themed responsive UI optimized for mobile and desktop
- Fixed CTA to open the Telegram bot
- Product-proof screenshot carousel on homepage
- Structured trust content (pricing/status/privacy/changelog)
- SEO-ready setup:
  - canonical + hreflang
  - page-level meta descriptions
  - `robots.txt`
  - `sitemap.xml`
  - `site.webmanifest`
  - JSON-LD where relevant

## Project Structure
```txt
.
├── index.html
├── how-it-works.html
├── status.html
├── pricing.html
├── privacy.html
├── faq.html
├── changelog.html
├── musk-durov-grok-telegram.html
├── ru/
│   ├── index.html
│   ├── how-it-works.html
│   ├── status.html
│   ├── pricing.html
│   ├── privacy.html
│   ├── faq.html
│   ├── changelog.html
│   └── musk-durov-grok-telegram.html
├── assets/
│   ├── styles.css
│   ├── brand/        # logos + favicons + app icons
│   ├── evidence/     # product screenshots
│   └── article/      # article evidence assets
├── robots.txt
├── sitemap.xml
└── site.webmanifest
```

## Local Development
Use any static server from repo root.

Example (Python):
```bash
python -m http.server 8080
```

Then open:
- `http://localhost:8080/`
- `http://localhost:8080/ru/`

## Content Rules
- Keep EN and RU page parity (same page set and navigation depth).
- Update both language versions for structural changes.
- Keep links absolute where required for SEO metadata, relative for internal navigation.
- Do not use placeholder screenshots in `assets/evidence/` or `assets/article/`.

## Brand/Favicon Pipeline
Brand icons are generated from the latest `assets/brand/cyberfrog-logo-latest.*`.
Current generated targets:
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png`
- `android-chrome-192x192.png`
- `android-chrome-512x512.png`

When logo changes, regenerate all icon assets before release.

## SEO & Indexing Checklist
Before publish:
1. Verify unique `<title>` and `<meta name="description">` per page.
2. Verify canonical URL per page (EN/RU correct).
3. Verify `hreflang` cross-links on both language versions.
4. Update `sitemap.xml` if new pages are added.
5. Confirm `robots.txt` allows target pages.
6. Check no accidental English-only content remains in `ru/`.

## Deployment
Designed for GitHub Pages static hosting.

Recommended flow:
1. Commit changes to main branch.
2. Publish via GitHub Pages.
3. Smoke-test:
   - Home EN/RU
   - CTA links
   - Favicons
   - Mobile nav readability
   - Carousel controls

## Roadmap Ideas
- Add Lighthouse CI checks
- Add automated HTML link checker
- Add screenshot diff regression checks for critical pages
- Add structured data for article pages in RU version
