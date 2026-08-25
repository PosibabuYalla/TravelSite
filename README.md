# Explore — Travel & Experience

A responsive, single-page travel/tour landing site built with plain HTML and CSS (no JavaScript, no build tools, no frameworks). It presents a fictional destination ("Mountain Paradise") with a hero booking widget, an about section, top attractions, things to do, a photo gallery, travel info, tour packages, and traveler testimonials.

## Project Structure

```
TravelSite/
├── index.html   # All page markup and content
├── style.css    # Base styles: layout, colors, typography, components
├── media.css    # Responsive rules only (tablet / mobile / small mobile breakpoints)
└── README.md    # This file
```

## How to View

No build step is required. Just open `index.html` directly in a browser, or serve the folder with any static file server, e.g.:

```
npx serve .
```

## Styling Architecture

- `style.css` — resets, CSS variables (colors, radius, container width), and all component/section styles (header, hero, booking box, attraction cards, gallery, packages, testimonials, footer).
- `media.css` — all `@media` breakpoints, kept in a separate file so responsive overrides don't get mixed in with base styles:
  - `max-width: 900px` — tablet layout (stacked grids, mobile nav toggle button shown)
  - `max-width: 600px` — mobile layout (single-column grids, mobile nav menu, resized hero/type)
  - `max-width: 380px` — small mobile fine-tuning (hero heading size, feature icon spacing)

`index.html` links both stylesheets in `<head>`, in this order:

```html
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="media.css">
```

## Fonts

Loaded from Google Fonts via `<link>` tags in `<head>`:
- **DM Sans** (400/500/600/700) — body text
- **Playfair Display** (600/700) — headings/logo

## Images

No local image assets are used — all images are loaded from free, open, no-API-key-required sources at page-load time.

| Source | Used for | Notes |
|---|---|---|
| [Picsum Photos](https://picsum.photos) | Destination/scenery photography (hero background, about, attractions, gallery, packages) | Real stock photography, served via seeded URLs (`/seed/<name>/<width>/<height>`) so each placement stays visually consistent across reloads. Images are generic stock photography — not guaranteed to literally match their caption (e.g. "Hidden Temple"). |
| [Pravatar](https://i.pravatar.cc) | Testimonial reviewer avatars | Real headshot placeholders, served via `?img=<id>`. |

### Full list of image URLs used

**Hero background** — `style.css`, `.hero` rule:
- `https://picsum.photos/seed/mountain-destination/1800/900`

**About section** — "Mountain Lake":
- `https://picsum.photos/seed/mountain-lake/900/700`

**Top Attractions**:
- Emerald Lake — `https://picsum.photos/seed/emerald-lake/700/450`
- Sunset Point — `https://picsum.photos/seed/sunset-point/700/450`
- Hidden Temple — `https://picsum.photos/seed/hidden-temple/700/450`
- Waterfall Trail — `https://picsum.photos/seed/waterfall-trail/700/450`

**Gallery**:
- Mountain — `https://picsum.photos/seed/gallery-mountain/800/900`
- Forest — `https://picsum.photos/seed/gallery-forest/600/500`
- Lake — `https://picsum.photos/seed/gallery-lake/600/500`
- Adventure — `https://picsum.photos/seed/gallery-adventure/700/900`
- Village — `https://picsum.photos/seed/gallery-village/600/500`
- Valley — `https://picsum.photos/seed/gallery-valley/600/500`

**Popular Packages**:
- Mountain Escape — `https://picsum.photos/seed/mountain-escape/800/500`
- Family Vacation — `https://picsum.photos/seed/family-vacation/800/500`
- Adventure Tour — `https://picsum.photos/seed/adventure-tour/800/500`

**Testimonials (avatars)**:
- Alex Morgan — `https://i.pravatar.cc/100?img=32`
- Sarah Wilson — `https://i.pravatar.cc/100?img=47`
- James Carter — `https://i.pravatar.cc/100?img=13`

### Replacing with your own images

To swap in real destination photos or hand-picked stock photos, replace the `src` (or the `url(...)` in `style.css` for the hero) with your own image path or URL — no other markup changes are needed, since every `<img>` and background image is a single self-contained reference.

## Page Sections

1. **Header / Nav** — logo, section links, language selector, "Plan Your Trip" CTA, mobile menu button (menu open/close needs JS or a `:target`/checkbox-based CSS toggle to function — currently only styled, not wired up, since the project intentionally ships without JavaScript).
2. **Hero** — headline, description, booking summary widget, trust badges.
3. **About** — destination intro with feature highlights.
4. **Top Attractions** — 4-card grid of points of interest.
5. **Things to Do** — 5-column activity strip (hiking, relaxing, camping, photography, local culture).
6. **Gallery** — filterable-looking tabbed image grid (tab filtering is visual only — no JS wired up).
7. **Travel Information** — best time to visit, getting around, travel tips.
8. **Popular Packages** — 3 tour package cards with pricing.
9. **Testimonials** — 3 traveler reviews with avatar, name, and country.
10. **Footer** — brand blurb, socials, sitemap columns, contact info, copyright.

## Notes

- This project deliberately contains **no JavaScript**. The mobile menu button and gallery filter tabs are present in the markup/CSS for visual completeness but are not functionally wired up.
- All content (destinations, prices, reviews) is placeholder/sample copy for demo purposes.
