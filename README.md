# 3FX Suite — Official Website & Showcase

This directory contains the complete, standalone static website and interactive showcase for **3FX** — the Studio-Grade Web Audio DSP & Mixer for Google Chrome.

This folder is **100% self-contained**: all styles, scripts, SVGs, images, and configuration files live entirely within this directory with zero external project dependencies. It is ready to be branched off or copied into its own independent GitHub repository.

---

## 📁 Repository Structure

```
site/
├── index.html              # Entry landing page with direct links to Showcase & Chrome Web Store
├── extension.json          # Extension metadata, version, and Chrome Web Store URL configuration
├── README.md               # Documentation and deployment instructions
├── package.json            # Standalone package definition with preview scripts
├── assets/                 # Shared brand icons, SVGs, and favicon
│   ├── favicon.svg
│   ├── icon-16.png
│   ├── icon-32.png
│   ├── icon-48.png
│   └── icon-128.png
└── 3fx/
    ├── index.html          # Deep interactive DSP showcase & audio workstation console
    ├── extension.json      # Showcase-local extension configuration
    └── assets/             # Showcase-local brand icons & favicon
        ├── favicon.svg
        ├── icon-16.png
        ├── icon-32.png
        ├── icon-48.png
        └── icon-128.png
```

---

## ⚙️ Updating the Extension Store Link

To update the Chrome Web Store URL (or add Firefox / Edge / GitHub URLs), update `links.chromeWebStore` (and `links.extensionPage`) in `extension.json`:

```json
{
  "name": "3FX Mixer",
  "version": "1.0.0",
  "links": {
    "extensionPage": "https://chromewebstore.google.com/detail/3fx-audio-suite/YOUR_EXTENSION_ID",
    "chromeWebStore": "https://chromewebstore.google.com/detail/3fx-audio-suite/YOUR_EXTENSION_ID",
    "github": "https://github.com/your-username/3fx"
  }
}
```

Both `site/index.html` and `site/3fx/index.html` automatically and dynamically bind all CTA download buttons (`[data-extension-link="chromeWebStore"]` and `[data-extension-link="github"]`) directly from this file when served over HTTP/HTTPS.

---

## 🚀 Running Locally

You can preview the site using any static HTTP server:

### Option 1: Using Node / npx
```bash
# From within the site directory:
npx serve .
```

### Option 2: Using Python 3
```bash
python -m http.server 3000
```

### Option 3: Using npm
```bash
npm install
npm start
```

Then visit:
- Landing Page: `http://localhost:3000/`
- Interactive Showcase: `http://localhost:3000/3fx/`

---

## 🌐 Deploying as a Standalone Repository

You can branch or move this folder into a standalone git repo:

```bash
# Branching off from root of project into a standalone branch or repo:
git subtree push --prefix site origin gh-pages
# Or copy folder contents to a new git repository:
git init
git add .
git commit -m "Initial commit: 3FX standalone website & showcase"
```

Compatible with 1-click zero-config deployment on:
- **GitHub Pages** (Publish directory: `/` or `/site`)
- **Cloudflare Pages**
- **Vercel**
- **Netlify**
