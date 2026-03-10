# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static Astro site for the **River City AI & Dev User Group** — a developer community based in Grand Rapids, Michigan. Deployed to GitHub Pages at [rivercity-ai.dev](https://rivercity-ai.dev) via the workflow in `.github/workflows/deploy.yml`.

## Commands

```bash
npm install          # Install dependencies
npm run dev          # Dev server at http://localhost:4321
npm run build        # Build to ./dist/
npm run preview      # Preview the production build locally
```

## Architecture

Single-page static site (`output: 'static'`). No framework integrations — vanilla Astro with component-scoped styles.

```
src/
  layouts/Layout.astro   # Root HTML shell: design tokens, global CSS, fonts, theme toggle, scroll-reveal
  pages/index.astro      # Entire page content + all section styles (co-located <style> block)
  components/            # (empty — components are inlined in index.astro for now)
public/
  logo.png               # Site logo
  CNAME                  # Custom domain: rivercity-ai.dev (required for GitHub Pages)
```

**Layout.astro** owns:
- CSS custom properties (design tokens) for light/dark themes via `[data-theme]`
- Google Fonts (`Syne` display, `DM Sans` body)
- Theme toggle logic (persisted to `localStorage`)
- IntersectionObserver-based scroll-reveal (`.reveal` → `.reveal.visible`)

**index.astro** contains all page sections: Nav, Hero, About, Topics, Events, Community, Resources, Newsletter/Signup, Footer. Styles are co-located in a `<style>` block at the bottom of the file.

## Deployment

Pushes to `main` trigger the GitHub Actions workflow which runs `npm ci && npm run build` and deploys `./dist` to GitHub Pages. The `public/CNAME` file sets the custom domain to `rivercity-ai.dev`.

To use a custom domain, the repo's GitHub Pages settings must also have the custom domain configured and DNS must point to GitHub Pages.

## Design System

Color tokens (defined in `Layout.astro`):
- `--electric-blue`: `#1e9cff`
- `--deep-teal`: `#0d9488`
- `--amber`: `#f59e0b`
- `--neon-orange`: `#fb923c`

Button variants: `.btn-primary` (blue), `.btn-secondary` (ghost), `.btn-accent` (amber/orange gradient).
