# NeuralAds Marketing Site

Single-file static site for NeuralAds. No build step. Deploy anywhere.

## Preview locally

```bash
# Option 1 — Python's built-in server
cd website
python -m http.server 8000
# → open http://localhost:8000

# Option 2 — just open the file
open index.html
```

## Edit the content

Everything is in `index.html`. Search and replace these placeholders before going live:

| Placeholder | Replace with |
|---|---|
| `hello@neuralads.ai` | Your real contact email (appears in 3 places) |
| `NeuralAds` | Your final company/product name if different |
| Foundational Research section | Add or remove citations as needed |
| Stats in hero (86, 12, 5min, 8) | Update with your real numbers |

## Deploy

### GitHub Pages (free, easiest)

```bash
git init
git add .
git commit -m "Initial site"
git remote add origin git@github.com:YOUR_USERNAME/neuralads-site.git
git push -u origin main

# Then in GitHub repo Settings → Pages:
#   Source: Deploy from branch
#   Branch: main / root
# Your site goes live at https://YOUR_USERNAME.github.io/neuralads-site/
```

### Vercel (free, custom domain easy)

```bash
npm i -g vercel
vercel
# Follow prompts. Done in 30 seconds.
```

### Netlify (drag and drop)

1. Go to https://app.netlify.com/drop
2. Drag the `website` folder onto it
3. Done

### Cloudflare Pages (fastest globally)

1. Connect your GitHub repo at https://pages.cloudflare.com
2. Build command: leave empty
3. Build output directory: `website`
4. Deploy

## Structure

```
website/
├── index.html          ← all the content + styling + JS
└── README.md           ← this file
```

The site uses:
- **Tailwind CSS via CDN** (no build step, no node_modules)
- **Inter + JetBrains Mono** from Google Fonts
- **Inline SVG icons** (no icon library)
- **IntersectionObserver** for scroll-reveal animations

Loads in <500ms on most connections. ~30KB total.

## Sections

1. **Hero** — tagline, sub, CTAs, stat strip
2. **Problem** — 3 cards (surveys lie / focus groups slow / A/B burns budget)
3. **How it works** — 3 stages with code/screenshot demos
4. **The science** — TRIBE explanation + research citations
5. **What you get** — Executive vs Full Brief comparison
6. **Who it's for** — 4 audience segments
7. **Platforms** — pill chips of supported platforms
8. **Contact** — email CTA + 3-step process
9. **Footer**

## Custom domain

After deploying to any of the above:
1. Buy domain (e.g. `neuralads.ai`) on Namecheap / Cloudflare / Porkbun
2. Add DNS records pointing to your host
3. Most hosts support free auto-HTTPS via Let's Encrypt

## Updating

Just edit `index.html`, push to GitHub, Pages/Vercel/Netlify auto-deploy on push.
