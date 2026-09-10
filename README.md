# The Golden Collection — MM Mithaiwala 50th Anniversary

Single self-contained landing page (`index.html`, no build step) for MM
Mithaiwala's 50th-anniversary "Golden Collection" campaign.

## Before launch: swap in real photography

I could not pull real product photos out of this chat as files, so
`/assets` currently holds clearly-labeled placeholder SVGs (jaali-lattice
pattern + text callout) instead of stock or AI-generated food photography,
per the brief. Replace these before launch:

| Placeholder file (delete after swap)     | Replace with     | Used for |
|---|---|---|
| `assets/hero-placeholder.svg`            | `assets/hero.jpg`| Hero shot, and the Open Graph / Twitter share image |
| `assets/concept-placeholder.svg`         | `assets/concept.jpg` | "One box, two lives" section |
| `assets/tower-set-placeholder.svg`       | `assets/tower-set.jpg` | Panch Diya Tower card |
| `assets/octagon-box-placeholder.svg`     | `assets/octagon-box.jpg` | Teen Diya Box card |

Then in `index.html`, swap each `src="assets/*-placeholder.svg"` for the
matching real `.jpg`, and update the two `og:image` / `twitter:image` meta
tags in `<head>` to point at `assets/hero.jpg`.

`assets/logo.svg` is a real (not placeholder) vector wordmark I built for
this brief — a line-art lantern glyph plus "50 / Years of MM Mithaiwala /
The Golden Collection" — swap it only if you have official brand artwork.

**Image sizing:** when you add the real JPGs, compress them for mobile —
hero/concept around 1600px wide, product shots around 1000px wide, saved
at ~70–80% quality (Squoosh or similar). All four are full-bleed/cropped
via `object-fit: cover`, so exact aspect ratio isn't critical, but hero is
roughly 5:6.3, concept 4:3, tower-set portrait, octagon-box square.

## Placeholder content also flagged in the page itself

- Both set prices (₹2,999 / ₹1,799) are marked "placeholder price" inline.
- "50,000+ customers served" and "120+ varieties made" in the Story stat
  row are marked with `*` and a footnote — replace with real figures.

## Notes on decisions made where the brief was ambiguous

- **No hamburger/mobile nav menu.** Since this is a short, scroll-first
  page mostly opened from Instagram bio links, I hid the desktop nav
  links under 720px rather than add a mobile menu — the hero's two CTAs
  and in-page order already get mobile visitors where they need to go.
- **Stat-row numbers** (customers served, varieties made) aren't in the
  brief, so they're placeholder figures flagged the same way as pricing.
- **Coupon redeem field** uppercases input for display but doesn't
  validate against a real code list (there's no backend to check
  against) — it always builds and opens the discount URL with whatever
  code is entered, which matches "functional coupon-redeem input that
  builds this URL on submit."
- **Jaali/arch motif** is implemented as reusable inline SVG frames
  (hero image, concept image, set-card image clip-paths) and a repeating
  diamond-lattice CSS divider between sections, rather than one-off
  decoration, so it reads as a consistent design device site-wide.
