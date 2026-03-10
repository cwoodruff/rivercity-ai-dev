# River City AI & Dev User Group Website

A modern, single-page static site built with [Astro](https://astro.build) for the **River City AI & Dev User Group** — Grand Rapids, Michigan's community for AI, web, mobile, Rust, .NET, and open-source developers.

---

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

---

## 🌐 Deploy to GitHub Pages

1. **Push to GitHub** — create a repo and push this project to the `main` branch.

2. **Enable GitHub Pages:**
   - Go to **Settings → Pages**
   - Source: **GitHub Actions**

3. **Update `astro.config.mjs`** with your repo info:
   ```js
   site: 'https://your-org.github.io',
   base: '/your-repo-name',  // omit if deploying to root domain
   ```

4. Push to `main` — the workflow in `.github/workflows/deploy.yml` will automatically build and deploy.

---

## 🎨 Design System

| Token | Value | Use |
|---|---|---|
| `--electric-blue` | `#1e9cff` | Primary CTAs, links, accents |
| `--deep-teal` | `#0d9488` | Secondary accents, badges |
| `--amber` | `#f59e0b` | Warm accents, CTAs |
| `--neon-orange` | `#fb923c` | Hover states, highlights |

**Fonts:** [Syne](https://fonts.google.com/specimen/Syne) (display/headings) + [DM Sans](https://fonts.google.com/specimen/DM+Sans) (body)

Themes: **Dark** (default) and **Light** — toggled via the 🌙/☀️ button in the nav, persisted to `localStorage`.

---

## 📁 Project Structure

```
river-city-ai/
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions deploy
├── public/
│   └── logo.png              # Group logo
├── src/
│   ├── layouts/
│   │   └── Layout.astro      # Base HTML shell, theme, fonts
│   └── pages/
│       └── index.astro       # Full single-page site
├── astro.config.mjs
└── package.json
```

---

## 📋 Page Sections

1. **Nav** — Sticky nav with theme toggle + mobile hamburger menu
2. **Hero** — Animated grid + orb background, logo, headline, CTAs, stats
3. **About** — Mission, values, stacked info cards
4. **Topics** — 9 tech focus areas (AI, Web, Mobile, Rust, .NET, OSS, Cloud, Security, Data)
5. **Events** — Featured upcoming event + past/upcoming event list
6. **Community** — Stats bar + persona grid (who attends)
7. **Resources** — Links to Discord, YouTube, Meetup, GitHub, Newsletter, LinkedIn
8. **Newsletter Signup** — Name, email, role, interest checkboxes with success state
9. **Footer** — Brand, social icons, nav columns

---

## ✏️ Customization

- **Events:** Edit the event data in the `#events` section of `index.astro`
- **Meetup link:** Replace `https://www.meetup.com` with your actual Meetup group URL
- **Discord/GitHub:** Update social links in the footer and resources section
- **Member count & stats:** Update the numbers in `hero-stats` and `community-stats`
- **Logo:** Replace `public/logo.png`

---

## 📄 License

MIT — use freely for the community.
