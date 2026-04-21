# SERPRANA — Website

One-page scrolling site for Kate / SERPRANA. Single-file HTML, no framework, no build step.

## Structure

```
site/
├── index.html       ← the entire site
└── assets/
    ├── hero.jpg             palapa group shot (hero)
    ├── hand-bowl.jpg        crystal bowl detail (Work section)
    ├── portrait.jpg         Kate outdoors in brown kimono (Meet Kate)
    ├── rooftop.jpg          wider rooftop session (Where We Meet)
    ├── kate-nature.jpg      alternate solo session shot (spare)
    ├── logo.png             dark ink logo for cream backgrounds
    └── logo-white.png       white logo for overlay on imagery
```

## Deploying

### Option 1 — GitHub Pages (free, simplest)

1. Create a new GitHub repo, e.g. `serprana-site`
2. Push the contents of this folder (not the folder itself) to the root
3. In Settings → Pages → Source, select `main` branch, root
4. Site lives at `https://<username>.github.io/serprana-site/`

For a custom domain (`serprana.com`): add a `CNAME` file at the repo root containing just the domain, then point the domain's DNS A records to GitHub Pages IPs.

### Option 2 — Netlify / Vercel / Cloudflare Pages (also free)

Drag-drop the folder or connect the GitHub repo. Zero config needed.

### Option 3 — Any traditional host

Upload `index.html` and the `assets/` folder to the web root. No server-side anything required.

## Sections in order

1. **Hero** — full-bleed palapa image, white logo top-left, soil-line headline, "SCROLL" indicator
2. **An Invitation** — centered quote, "This work isn't about becoming someone new…"
3. **The Work** — dark ink section with Kate's "I hold a space both deeply nurturing…" statement + hand-on-bowl image
4. **Energy Offerings** — four offerings (Sound Healing / Vibrational Alchemy Healing / Guided Medicine Journey / Herbal Consultation)
5. **Meet Kate** — half-image half-content split, bio + credentials list
6. **Soil Manifesto** — full-bleed centered quote, "Fertile soil doesn't make a seed grow…"
7. **Where We Meet** — rooftop image + finca copy
8. **Words From Clients** — three testimonial placeholders (fill in when Kate has them)
9. **Book** — dark WhatsApp CTA + phone fallback
10. **Footer** — brand, social, copyright

## Editing

Everything is in `index.html`. The CSS lives in the `<style>` block at the top; content is in the `<body>`. All design tokens are CSS custom properties at the top:

```css
:root {
  --cream:        #EFE5D2;
  --cream-deep:   #E5DAC4;
  --ink:          #2A1F14;
  --ink-soft:     #5A4631;
  --bronze:       #8B6F47;
  --font-display: 'Cormorant Garamond', …;
  --font-label:   'Inter', …;
}
```

### Replacing images

Drop a new JPG into `assets/` with the same filename, or edit the `src="assets/…"` attributes in the HTML.

### Adding testimonials

Find the `<section class="praise">` block. Replace each `<div class="praise__item">…</div>` with the real quote and client name.

### Changing the phone number or WhatsApp link

Search for `50765652565` — replace every occurrence. Five places:
- top nav CTA
- hero → mobile sheet
- book CTA button
- book phone fallback (`tel:` link)

### Instagram handle

Search for `edelstein_kate` in the footer and replace.

## Technical notes

- Fonts loaded from Google Fonts: Cormorant Garamond (display) + Inter (small caps labels only)
- Vanilla JS only — ~30 lines for nav scroll state, IntersectionObserver reveals, mobile menu toggle
- Respects `prefers-reduced-motion` for accessibility
- No analytics, no tracking, no external dependencies besides Google Fonts
- Mobile: breakpoint at 820px for grid changes, 700px for hero footer
- All images are JPEG, optimized and progressive

## What's not done yet

- Testimonials are placeholders — Kate needs to provide three real ones
- A treehouse-specific photo would strengthen the "Where We Meet" section (currently using the rooftop image)
- A tree illustration as a subtle background texture (discussed separately) is not yet implemented — the brand mark's mandala could play that role in Phase 2
- Favicon not set — add a `<link rel="icon">` once a 32×32 or SVG version of the logo is prepared

## Credits

Copy and brand direction developed through conversation with Kate. Soil line is hers. "To be a Life Force" is hers. Photography from Kate's library. Site built using her provided content as the source material.
