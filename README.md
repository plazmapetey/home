# Plazma Petey's Extraordinary Science Shows

Static brochure website for **Plazma Petey's Extraordinary Science Shows** — a science entertainment business offering custom shows for birthday parties and school assemblies within 30 miles of Fremont, CA.

**Live domain:** `plazmapetey.com` (also owns `plasmapetey.com` — redirects via Netlify)  
**Deploy target:** Netlify  
**Stack:** Plain HTML / CSS / JS — no frameworks, no build step

---

## Business Details

| | |
|---|---|
| **Service** | Custom science shows for birthday parties & school assemblies |
| **Service area** | Within 30 miles of Fremont, CA |
| **Flat rate** | $1,000 (supplies $500 · business $200 · travel & setup $200 · performance $100) |
| **Gratuities** | Welcome |
| **Performer** | Award-winning edu-tainer, 5 years performing, 10+ years STEM education, 100+ shows, Edu-tainer of the Year ×3 |

---

## Project Goals

1. **Convert visitors to bookings** — every section funnels toward the contact form
2. **Rank locally** — SEO-optimised for: `science birthday party Fremont`, `kids science show Bay Area`, `school assembly science Palo Alto`
3. **Build trust** — transparent pricing breakdown, credentials, testimonials
4. **Fast & accessible** — no JS frameworks, mobile-first CSS, semantic HTML, ARIA labels throughout

---

## File Structure

```
/
├── index.html          # Single-page site — all sections
├── styles.css          # Mobile-first stylesheet, CSS variables, Space Grotesk font
├── script.js           # (to be created) nav toggle, FAQ accordion, form UX, footer year
├── robots.txt          # Allow all crawlers, points to sitemap
├── sitemap.xml         # Single URL sitemap for plazmapetey.com
├── netlify.toml        # Publish config + 301 redirect from plasmapetey.com
└── assets/
    ├── images/         # Hero image, OG image, performer photo (to be added)
    └── icons/          # Favicon, apple-touch-icon (to be added)
```

### index.html sections (in order)

| Section | ID | Notes |
|---|---|---|
| Sticky nav | — | Hamburger on mobile, links + CTA on desktop |
| Hero | `#hero` | H1, subhead, two CTAs, "100+ shows" badge |
| About | `#about` | Photo placeholder, bio, stats grid |
| What I Offer | `#what-i-offer` | Three cards: birthday, school assembly, custom |
| Pricing | `#pricing` | Full $1,000 breakdown on dark background |
| Service Area | `#service-area` | Map placeholder, city list |
| Testimonials | `#testimonials` | 3 placeholder quotes — replace with real ones |
| FAQ | `#faq` | 6 accordion items — answers are placeholders |
| Contact | `#contact` | Netlify form, honeypot, all booking fields |
| Footer | — | Brand, nav links, service area, copyright |

### What still needs real content

- **Performer photo** → replace `about-image-placeholder` div with `<img>`
- **OG image** → `assets/images/og-image.jpg` (1200×630px)
- **Testimonials** → swap placeholder text with real quotes + names
- **FAQ answers** → replace placeholder text with real answers
- **Contact/phone** → add to JSON-LD `LocalBusiness` and footer if desired
- **Favicon** → add `<link rel="icon">` in `<head>` and drop files in `assets/icons/`

---

## Local Preview

No build step needed — open directly in a browser:

```bash
# Option 1: Python (built-in on macOS/Linux)
python3 -m http.server 8000
# then open http://localhost:8000

# Option 2: Node (if installed)
npx serve .
# then open the URL shown in terminal

# Option 3: VS Code
# Install the "Live Server" extension, right-click index.html → Open with Live Server
```

> Note: the Netlify form submission (`data-netlify="true"`) only works when deployed to Netlify — it will silently fail locally.

---

## Deploy to Netlify

### First deploy (via Netlify UI)

1. Push this repo to GitHub (or GitLab / Bitbucket)
2. Log in to [netlify.com](https://netlify.com) → **Add new site → Import an existing project**
3. Connect the repo — Netlify will detect `netlify.toml` automatically
4. Build settings will be pre-filled (no build command, publish dir = `.`)
5. Click **Deploy site**

### Domain setup

1. In Netlify site settings → **Domain management** → add `plazmapetey.com` as primary
2. Add `plasmapetey.com` as a domain alias
3. The redirect rule in `netlify.toml` will then 301 all `plasmapetey.com` traffic to `plazmapetey.com`
4. Enable **HTTPS** (Netlify provisions a free Let's Encrypt cert automatically)

### Subsequent deploys

Push to the connected branch — Netlify auto-deploys on every push.

---

## Style Notes (for future edits)

- **Font:** Space Grotesk (Google Fonts) — one font, weights 400/500/600/700
- **All design tokens** are CSS variables in the `:root` block at the top of `styles.css`
- **Color palette:** dark navy `#0d1b2a` · electric blue `#1a56db` · emerald `#059669` · amber `#f59e0b`
- **Breakpoints (mobile-first):** 540 · 640 · 768 · 960 · 1024px
- To change the brand color, update `--color-primary` in `styles.css` — it cascades everywhere
