# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Deployment

Static files served via GitHub Pages. Push to the repo's default branch to deploy. The custom domain `white-noise-sounds.online` is set in `CNAME`.

No build step — edit HTML/CSS directly.

## Pages

| File | URL | Purpose |
|---|---|---|
| `index.html` | `/` | Main landing page with CTA to install the extension |
| `welcome.html` | `/welcome` | Post-install onboarding (opened automatically by `background.js` on first install) |
| `uninstall.html` | `/uninstall` | Farewell page (configured as uninstall URL in the Chrome Web Store) |

## Shared styles

`shared.css` is imported by all three pages. It defines the design token variables (`--bg`, `--fg`, `--accent`, `--muted`, `--line`, etc.) and their dark-mode overrides under the `.dark` class. Light/dark toggle is done in JS by toggling `.dark` on `<body id="page">` (or `<body>` for pages without the id).

Fonts: **Inter** (body) and **Source Serif 4** (headings/brand) loaded from Google Fonts.

## Content that mirrors the extension

The noise descriptions (`tip` text in the noise cards) and the track list must stay in sync with the data arrays in `extension/popup.js` (`NOISE` and `TRACKS` constants). When adding or removing a sound in the extension, update the landing page manually.
