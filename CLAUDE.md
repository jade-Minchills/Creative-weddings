# Wedding Website Project — CLAUDE.md

## Project overview
A one-page marketing/landing site for **Forever Pages**, a digital wedding website service targeting engaged couples (mid-20s to mid-30s).

Single file: `index.html` — no build step, deploys as-is.

## Stack
- Plain HTML + CSS + vanilla JS
- Tailwind CSS via CDN (utility classes used selectively)
- Google Fonts via CDN: Great Vibes (script), Cormorant Garamond (display), DM Sans (body)
- No frameworks, no bundler

## Brand
- **Name:** Forever Pages
- **Tagline:** Your perfect digital wedding, beautifully crafted
- **Palette:**
  - Blush pink: `#F4A7B9` / mid `#E8879E` / light `#FBE8EE`
  - Sage green: `#B2C9AD` / mid `#7BA874` / light `#EBF3E9`
  - Champagne: `#F5E6C8` / mid `#C4A040` / light `#FDF6E9`
  - Background: `#FAFAFA`, text: `#2A2A2A`, muted: `#7A7A7A`

## Sections (in order)
1. Hero — floating petal canvas, rotated Unsplash photo frames, names, tagline, CTAs, stats
2. Why Go Digital — 4 benefit cards
3. Features Grid — 8 feature cards, strict 4-col desktop / 2-col mobile
4. QR Code — split layout with CSS-rendered QR mockup
5. Pricing — Basic £99 / Standard £199 (featured) / Premium £349
6. Demo Preview — laptop + phone device mockups
7. Testimonials — 3 couple cards
8. Blog Preview — 3 article cards
9. Final CTA — email capture + trust badges
10. Footer

## Design decisions & constraints
- **No pill/badge components in the hero** — user flagged these as a generic AI-website cliché
- **No "The modern way to share your special day" copy** — removed, considered AI-slop
- Features grid must be a strict 4×2 (not auto-fill) to stay balanced
- Hero photo frames: 4 Unsplash wedding photos, absolute-positioned left/right, rotated like polaroids, hidden below 1100px viewport
- Floating petals: canvas-based, 36 pastel ellipses drifting down
- Navbar: transparent → frosted glass on scroll
- All sections use Intersection Observer fade-up reveals with stagger delays (.d1–.d5)
- CSS variables defined in `:root` — always use vars, never hardcoded hex except in SVG fills

## Unsplash photo IDs used
- Hero left tall: `photo-1519741497674-611481863552` (ceremony)
- Hero left small: `photo-1465495976277-4387d4b0b4c6` (flowers)
- Hero right tall: `photo-1583939003579-730e3918a45a` (bride)
- Hero right small: `photo-1511285560929-80b456fea0bc` (rings)

## South African localisation
The main site (index.html) targets South Africa:
- Domain: `forever-pages.co.za`
- Testimonial locations: Cape Town, Johannesburg, Durban
- Pricing in ZAR
- Footer: "Made with love in South Africa."

## Demo site
`demo/index.html` — fully interactive one-page wedding invitation. Mobile responsive.
- Envelope hero: click/scroll opens flap (3D rotateX), letter slides out, scrolls to invitation card
- Parallax venue section (JS translateY on scroll)
- Vertical timeline (Intersection Observer, left/right alternating)
- Bridal party 3+3 CSS flip cards (hover rotateY 180deg)
- Wedding quiz (4 questions, JS scored, result reveal)
- Song request list (append on enter/click)
- Live countdown timer to 14 June 2025
- Event schedule + Google Maps iframe + RSVP form with success state
- 7-image gallery grid with lightbox (keyboard nav, click-outside close)
- CSS QR code block (11×11 JS-rendered pixel grid)
- Closing section with poem + footer attribution

## Pricing (ZAR, one-time)
| Package  | Price   |
|----------|---------|
| Basic    | R2,299  |
| Standard | R4,699  |
| Premium  | R8,199  |
