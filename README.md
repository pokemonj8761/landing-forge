<div align="center">

<br/>

<img alt="landing-forge" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=42&duration=2400&pause=900&color=A78BFA&center=true&vCenter=true&width=900&height=80&lines=landing-forge"/>

**Beautiful landing pages from one YAML file. Or one AI prompt.**
_Built-in analytics · A/B testing · SEO · animations · multilingual._

<br/>

### 🖥️ Visual builder app

[<img src="https://img.shields.io/badge/Download%20for%20macOS-000000?style=for-the-badge&logo=apple&logoColor=white" height="40"/>](https://github.com/kasimmj/landing-forge/releases/latest/download/landing-forge-macos.dmg)
[<img src="https://img.shields.io/badge/Download%20for%20Windows-0078D7?style=for-the-badge&logo=windows&logoColor=white" height="40"/>](https://github.com/kasimmj/landing-forge/releases/latest/download/landing-forge-setup.exe)
[<img src="https://img.shields.io/badge/Web%20Builder-A78BFA?style=for-the-badge&logo=safari&logoColor=white" height="40"/>](https://landing-forge.kasimmj.com)

### Or YAML + CLI

```bash
npx landing-forge new --from landing.yaml
```

<br/>

<p>
<img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white"/>
<img src="https://img.shields.io/badge/AI-A78BFA?style=for-the-badge"/>
<img src="https://img.shields.io/badge/MIT-000000?style=for-the-badge"/>
</p>

<p>
<img src="https://img.shields.io/github/stars/kasimmj/landing-forge?style=social"/>
<img src="https://img.shields.io/github/forks/kasimmj/landing-forge?style=social"/>
</p>

</div>

---

## 🚀 What it does

Most landing page builders are either:
- ❌ **Locked-in SaaS** (Webflow, Unbounce) — you don't own the code
- ❌ **Page templates** — beautiful but rigid

`landing-forge` is different: **you describe the page once, it generates production code, you own everything.**

Three ways to describe:
1. 📝 **YAML config** (precise, version-controlled)
2. 🤖 **AI prompt** (fast, conversational)
3. 🎨 **Visual builder** (no code at all)

All three produce the **same kind of output** — a clean Next.js project ready to deploy.

---

## 📝 YAML example

```yaml
# landing.yaml
brand:
  name: "MyProduct"
  logo: ./assets/logo.svg
  primary: "#8A2BE2"

sections:
  - type: hero
    headline: "Ship faster. Sleep better."
    sub: "The fastest way to deploy your AI agents to production."
    cta:
      label: "Get started — it's free"
      href: "/signup"
    image: ./assets/hero.png
    layout: split-right    # or split-left, center, full-bleed

  - type: features
    style: alternating
    items:
      - icon: ⚡
        title: "Instant deploy"
        body: "From git push to production in 30 seconds."
      - icon: 🛡️
        title: "Secure by default"
        body: "SSL, auth, rate limits all wired."
      - icon: 📊
        title: "Built-in analytics"
        body: "See what works without third-party tools."

  - type: testimonials
    style: marquee
    items:
      - quote: "We shipped 3x faster after switching."
        author: "Alice"
        role: "CTO, ExampleCo"
        avatar: ./assets/alice.jpg

  - type: pricing
    plans:
      - name: Free
        price: "$0"
        features: [10 deploys/mo, Community support]
      - name: Pro
        price: "$29/mo"
        highlighted: true
        features: [Unlimited deploys, Email support, Analytics]

  - type: faq
    items:
      - q: "Do I need a credit card to start?"
        a: "No. Free tier doesn't require any payment info."

  - type: cta-final
    headline: "Ready to ship?"
    cta: "Start free trial"

seo:
  title: "MyProduct — Ship faster"
  description: "Deploy your AI agents to production in 30 seconds."
  og_image: ./assets/og.png

analytics:
  plausible:
    domain: myproduct.com
```

Then:

```bash
npx landing-forge new --from landing.yaml
# → builds Next.js project in ./my-landing-page
# → starts preview at localhost:3000
```

---

## 🎨 Visual Builder (no code)

```
╭─────────────────────────────────────────────────────────────────╮
│   🛠️  landing-forge Studio                          ─  ☐  ✕    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   📐 Sections (drag to reorder)         🖥️ Live Preview         │
│   ┌─────────────────────┐    ┌────────────────────────────────┐│
│   │ ☰ Hero              │    │  ╭──────────────────────────╮  ││
│   │ ☰ Features          │    │  │  ✨ Ship faster.         │  ││
│   │ ☰ Testimonials      │    │  │  Sleep better.            │  ││
│   │ ☰ Pricing           │    │  │  ┌─────────────────┐     │  ││
│   │ ☰ FAQ               │    │  │  │  Get started ➜  │     │  ││
│   │ ☰ CTA Final         │    │  │  └─────────────────┘     │  ││
│   │                     │    │  ╰──────────────────────────╯  ││
│   │ + Add section ▾     │    │  ─────────────────────────────  ││
│   └─────────────────────┘    │  ⚡ Features                    ││
│                              │   ╭─────╮ ╭─────╮ ╭─────╮      ││
│   🎨 Properties (Hero)       │   │ ⚡  │ │ 🛡️  │ │ 📊  │      ││
│   ┌─────────────────────┐    │   ╰─────╯ ╰─────╯ ╰─────╯      ││
│   │ Headline:           │    │  ─────────────────────────────  ││
│   │ [Ship faster...]    │    │  Pricing                       ││
│   │ Layout: split-right │    │  ┌──────┐ ┌──────┐ ┌──────┐    ││
│   │ Image: [Upload]     │    │  │ Free │ │ Pro  │ │ Team │    ││
│   │ Animation: fade-up  │    │  └──────┘ └──────┘ └──────┘    ││
│   └─────────────────────┘    └────────────────────────────────┘│
│                                                                 │
│   [💾 Save]  [🚀 Deploy]  [📦 Export YAML]  [🤖 AI Improve]    │
╰─────────────────────────────────────────────────────────────────╯
```

Features:
- 🖱️ **Drag-and-drop** to reorder sections
- 🎨 **Inline editing** — click any text to edit
- 📐 **Layout variants** — every section has 3-6 alternatives
- 🎭 **Theme themes** — switch entire visual style in one click
- 📱 **Mobile / Tablet / Desktop** preview tabs
- 🚀 **One-click deploy** to Vercel, Netlify, or any host
- 🔄 **Bi-directional** — YAML ↔ Visual, both stay in sync

---

## 🤖 AI Prompt mode

For when you want to skip the YAML:

```bash
npx landing-forge new --prompt "
Landing page for a Flutter app that helps Iraqi students study.
Modern dark theme. Showcase features, screenshots, pricing.
Arabic + English. Include WhatsApp contact button.
"
```

In 30 seconds, you get:
- Full YAML config (you can edit later)
- Generated copy in Arabic + English
- Suggested color palette
- Selected layouts that match the vibe
- Stock images (or generates new with FLUX)
- Working Next.js project deployed to a preview URL

---

## 🧪 A/B Testing built in

```yaml
sections:
  - type: hero
    variants:
      - headline: "Ship faster. Sleep better."
        weight: 50
      - headline: "Deploy AI agents in 30 seconds"
        weight: 50

analytics:
  ab_test:
    metric: "cta_click"
    sample_size: 1000
    auto_winner: true
```

After 1000 visits, landing-forge auto-promotes the winning variant. No external tool needed.

---

## 📊 Built-in privacy-friendly analytics

- 🔒 No cookies
- 🇪🇺 GDPR-friendly out of the box
- 📊 Standard metrics: pageviews, bounce rate, CTA clicks
- 🎯 Conversion funnels
- 🌍 Visitor map
- 📤 CSV export

Hosted at `/dashboard` on your generated site. No third-party analytics needed.

---

## 🌍 Multilingual

Set `locales: [en, ar]` in your config → landing-forge:
- Generates separate `/en` and `/ar` routes
- Auto-detects user language from browser
- Provides language switcher
- Translates copy via Claude/GPT (you review)
- Mirrors layouts for RTL Arabic

---

## 🎨 30+ Section Templates

Each section type has multiple variants:

- **Hero** — Split / Centered / Full-bleed / Video-bg / 3D-canvas
- **Features** — Grid / Alternating / Tabs / Bento / Carousel
- **Testimonials** — Marquee / Grid / Single-spotlight / Video / Logo-wall
- **Pricing** — 3-tier / 4-tier / Comparison / Calculator / Annual-toggle
- **FAQ** — Accordion / Two-column / Searchable / Categorized
- **Footer** — Mega / Minimal / Newsletter-CTA / Social-grid
- **About** — Founder-letter / Timeline / Mission / Stats / Press
- **Contact** — Form / Map / Multi-office / Calendly-embed
- **Gallery** — Masonry / Carousel / Before-after / Lightbox

---

## 🚀 Deploy

```bash
cd my-landing-page

# Vercel
npm run deploy:vercel

# Netlify
npm run deploy:netlify

# Cloudflare Pages
npm run deploy:cf

# Self-host (Docker)
docker build -t my-landing .
docker run -p 80:3000 my-landing
```

---

## 📜 License

MIT.

---

<div align="center">

**Star ⭐ to ship landing pages 10x faster.**

</div>
