# MBisAfrican — Web Design Reference
**Attach this file to any web, page, or SPA build prompt for brand consistency.**

---

## 1. Brand Context

MBisAfrican (Maison Blanche is African) is a premium market-entry platform helping African and minority-owned brands access the U.S. market. It is not a passive directory — it is a structured, curated, high-standard ecosystem.

The brand personality is **commanding, culturally rooted, precise, and alive**. It carries authority without being cold, and warmth without being casual. Every design decision must reflect a brand that operates at the highest standard — not a lean team trying to look premium, but a premium brand with a lean team.

**Archetype tension to keep in mind:** The Ruler (primary) — structure, authority, legacy — punctuated by The Outlaw — bold, disruptive, unapologetic. The Ruler builds the foundation; the Outlaw provides the edge.

> **Design implication of the Outlaw edge:** This archetype tension is a creative license, not just a personality note. It gives explicit permission for asymmetric layouts, bold typographic sizing, unexpected section rhythm, and confident negative space. A design that only expresses the Ruler — safe, symmetric, restrained — is an incomplete representation of this brand. Let the Outlaw show.

---

## 2. Theme & Mood

- **Always light theme overall.** White is the default background. No dark mode. Dark sections are permitted as deliberate, powerful moments — not as a dominant layout pattern across the page.
- **Mood:** Powerful, warm, precise, culturally alive. Never cold. Never generic. Never cluttered.
- **Reference feel:** Editorial precision of a premium global business publication, warmed by African creative energy and texture.
- **Not this:** Western luxury imitation. Generic SaaS clean. Startup minimal. African brands presented apologetically.

---

## 3. Colour System

Use CSS custom properties. These are non-negotiable — do not substitute or approximate.

```css
:root {
  --color-red:       #FC490B; /* Signal Red — primary action */
  --color-blue:      #103190; /* Authority Blue — primary structure */
  --color-gold:      #FAB909; /* Gold — accent, badges, celebration */
  --color-tan:       #C9A077; /* Sahara Tan — cultural warmth, texture */
  --color-grey:      #E8E8E8; /* Cloud Grey — breathing room, dividers */
  --color-white:     #FFFFFF; /* Primary background — always pure white */
}
```

### Colour Usage Rules

| Colour | Web Role |
|---|---|
| **Signal Red `#FC490B`** | CTA buttons, hover states, left-edge accent bars, highlighted keywords, active nav indicators. Punches — never floods. Avoid as full-section background fills. |
| **Authority Blue `#103190`** | Primary headline colour, nav backgrounds, section backgrounds for professional/formal sections, footer, email header areas, hero sections. The visual anchor of the brand. |
| **Gold `#FAB909`** | Vendor badges, approval tags, price labels, milestone callouts, decorative accents. Use with restraint — it should feel special. Never use as body text on white — contrast is insufficient. |
| **Sahara Tan `#C9A077`** | Quote section backgrounds, cultural content overlays, subtle texture washes. The most human colour — use it to soften sections that need warmth. Pairs well with Authority Blue text on top. |
| **Cloud Grey `#E8E8E8`** | Alternate section backgrounds, subtle dividers, secondary content areas. Its job is to rest the eye and sharpen contrast for the power colours. Never a headline colour. |
| **White `#FFFFFF`** | Default background for all pages and components. Always pure white — never cream or off-white. |

### Colour Deployment Pattern

A typical page section hierarchy:
1. White background sections (default)
2. Cloud Grey background sections (breathing room, separation)
3. Sahara Tan background sections (cultural/quote content)
4. Authority Blue background sections (formal, footer, hero)

Signal Red and Gold never dominate a section — they appear as accents, CTAs, and highlights within these backgrounds.

### Authority Blue as a Hero Background

Authority Blue is a valid and powerful hero background. Using it at the top of a page — with white type and a Signal Red CTA — creates the commanding first impression this brand demands. This is not a violation of the light-theme rule. The brand is light overall; individual sections can be full Authority Blue when authority is the goal. What the light-theme rule prohibits is a page where darkness is the dominant atmosphere — not a single strong opening.

### Gradients

Gradients are permitted when derived from the brand palette and used with restraint. Acceptable uses include a subtle Signal Red-to-Authority Blue gradient on a hero overlay, a Sahara Tan-to-white fade as a section wash, or a soft Authority Blue-to-transparent overlay on photography. What is prohibited: rainbow gradients, gradients pulling in any colour outside the defined palette (no teal, purple, or warm grey), and gradients used as primary backgrounds for full content sections. A gradient should feel like a finish, not a foundation.

---

## 4. Typography

Import from Google Fonts:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Nunito+Sans:wdth,wght@125,400;125,500;125,700&family=Barlow+Condensed:wght@600&display=swap" rel="stylesheet">
```

### Type System

| Role | Font | Weight | Notes |
|---|---|---|---|
| **Headlines / Display** | Nunito Sans Expanded | Bold (700) | Wide, warm, brand-native — matches the logo wordmark |
| **Subheadlines** | Barlow Condensed | SemiBold (600) | Tight axis contrast against headlines; always subordinate |
| **Body / Paragraphs** | Nunito Sans | Regular (400) | Non-expanded for readability at length |
| **Labels / Tags / Badges** | Barlow Condensed | SemiBold (600) | All-caps, letter-spacing: 0.08–0.12em |
| **Nav / UI Elements** | Nunito Sans | Medium (500) | Non-expanded; clean and functional |

```css
:root {
  --font-display:    'Nunito Sans', sans-serif; /* wdth: 125 (Expanded) */
  --font-condensed:  'Barlow Condensed', sans-serif;
  --font-body:       'Nunito Sans', sans-serif; /* wdth: normal */
}
```

### Typography Rules

- **Headline size must be unapologetic.** Large and commanding — never timid. On desktop, primary headlines should not drop below 48px. On mobile, not below 32px.
- **Subheadline tracking:** Add `letter-spacing: 0.02em` to Barlow Condensed subheadlines to open the condensed letterforms slightly.
- **Label style:** Barlow Condensed SemiBold, all-caps, `letter-spacing: 0.10em`, small size (11–13px). Use for category tags, section markers, vendor badges.
- **Body line height:** Minimum `1.6` — text needs room to breathe.
- **Never use script or handwritten fonts.** Never mix more than two font families. Never use system fonts as fallbacks without the brand fonts loading first.
- **No font outside this system should appear on any MBisAfrican asset.**

### Type Scale (Suggested)

```css
/* Desktop */
--text-display:   clamp(48px, 5vw, 80px);   /* Hero headlines */
--text-h1:        clamp(36px, 4vw, 60px);
--text-h2:        clamp(28px, 3vw, 44px);
--text-sub:       clamp(18px, 2vw, 26px);   /* Barlow Condensed */
--text-body:      16px;
--text-label:     12px;
```

---

## 5. Mobile Responsiveness — Non-Negotiable

This is a primary requirement on every project. MBisAfrican's vendors and clients are predominantly mobile-first African users. Every design decision must work on a 375px screen before it works on a 1440px screen.

### Requirements

- **Mobile-first CSS.** Write base styles for small screens; scale up with `min-width` breakpoints.
- **Breakpoints:**
  ```css
  /* Mobile: default (375px+) */
  /* Tablet: min-width 768px */
  /* Desktop: min-width 1024px */
  /* Wide: min-width 1280px */
  ```
- **No horizontal scroll** on any viewport. Test at 375px, 414px, and 390px.
- **Touch targets** must be minimum 44×44px (buttons, nav items, links, form inputs).
- **Navigation:** Hamburger/drawer menu on mobile. Never rely on hover states for critical interactions.
- **Images:** Always use `max-width: 100%`. Use `object-fit: cover` for image containers. Lazy load below-the-fold images.
- **Typography:** Use `clamp()` for fluid type sizing. Never let headlines overflow on narrow screens.
- **CTA buttons:** Full-width on mobile (`width: 100%`), inline/fixed-width on desktop.
- **Spacing:** Use relative units (`rem`, `%`, `clamp`) not fixed `px` for layout spacing.
- **Forms:** Stack labels above inputs on mobile. Inputs must be minimum 48px tall for comfortable touch.

---

## 6. Layout & Spacing Principles

- **Strong typographic hierarchy.** If everything is loud, nothing is heard. Headlines dominate. Subheadlines are clearly subordinate. Body text is comfortable. Labels are small but legible.
- **Generous white space** gives content authority. Never clutter. Empty space is a design choice, not a mistake.
- **Red accent bar:** A Signal Red left or bottom edge accent element is the fastest visual shorthand for "this is MBisAfrican." Use it consistently on informational content cards — but apply with judgment in dense card grids where repetition would dilute the effect. Occasional restraint makes the bar more powerful when it appears.
- **Grid discipline:** Elements align intentionally. Nothing placed arbitrarily.
- **Maximum content width:** `1200px` centered, with `padding: 0 24px` on mobile and `padding: 0 48px` on desktop.
- **Section padding:** Minimum `80px` vertical padding on desktop, `48px` on mobile.

---

## 7. UI Component Guidelines

### Buttons

```
Primary CTA:    Background: Signal Red (#FC490B) | Text: White | No border
Secondary CTA:  Background: Transparent | Border: 2px Authority Blue | Text: Authority Blue
Hover (Primary): Darken Red slightly or shift to Authority Blue
Font:           Nunito Sans Medium | All-caps or sentence case — pick one and hold it
Border-radius:  0px–4px maximum. No pill shapes — they undermine authority.
```

### Navigation

- Background: White (default) or Authority Blue (on hero/dark sections)
- Logo: Always visible, always full-colour version on white, white version on blue backgrounds
- Active link indicator: Signal Red underline or left-bar accent
- Mobile: Slide-in drawer from right, Authority Blue background, white text

### Cards (Vendor / Product / Feature)

- White background, subtle border or shadow
- Left-edge Signal Red accent bar (3–4px) — standard on content cards; use judgment in high-density grid layouts
- Headline: Nunito Sans Expanded Bold
- Label/category: Barlow Condensed SemiBold all-caps
- Image: Always `object-fit: cover`, consistent aspect ratio across card grid

### Section Headers

- Label (small, Barlow Condensed all-caps, Signal Red or Authority Blue) above the headline
- Headline: Nunito Sans Expanded Bold
- Subhead: Barlow Condensed SemiBold
- Optional: thin Signal Red line beneath the label

### Badges & Tags

- Gold (`#FAB909`) background for approval/premium badges
- Barlow Condensed SemiBold, all-caps, tight tracking
- Border-radius: 2–4px maximum

---

## 8. Imagery Direction

- **No generic stock photography.** Real African businesses, real people, real products.
- **Product shots:** Clean, high-contrast, well-lit, intentional backgrounds (white or brand colours).
- **People:** Confident, real, directional — not handshake-and-smile stock.
- **Gifting/hampers:** Styled, aspirational, overhead or close-up detail shots.
- **Cultural content:** Vibrant, high-resolution, celebratory — colour and texture must speak.
- **Overlays:** When placing text over images, use a semi-transparent Authority Blue (`#103190`) or Sahara Tan (`#C9A077`) overlay — never a plain dark scrim.
- **Image must always look like it belongs to MBisAfrican** — remove the logo mentally; the image should still feel on-brand.

### When Photography Is Unavailable

Real vendor photography is the standard. When it is not available — for placeholder builds, demo pages, or early-stage layouts — use one of the following instead of sourcing generic stock:

- **Full brand-colour sections:** A full-bleed Authority Blue or Sahara Tan section with strong typography and a Signal Red CTA is more on-brand than a placeholder image with a dark scrim.
- **Graphic/pattern treatments:** Geometric patterns or texture overlays derived from the brand palette (red, blue, gold, tan on white or grey) maintain the visual standard without photography.
- **AI-generated imagery:** Acceptable as a temporary stand-in if the output is high quality, confidently composed, and matches the imagery direction above. Must be replaced with real photography before any public-facing launch.

---

## 9. Animation & Interaction

- **Restrained but present.** The brand is alive — but not hyperactive.
- **Page load:** Staggered fade-in/translate-up on hero headline and subheadline. Subtle — 300–500ms, `ease-out`.
- **Scroll reveals:** Sections and cards fade in as they enter the viewport. Use `IntersectionObserver`.
- **Hover states:** CTA buttons shift colour. Cards lift slightly (`transform: translateY(-4px)`, subtle shadow increase). Nav links show Red underline.
- **No jarring transitions.** No bouncing. No spinning. No attention-seeking animations on body text.
- **Respect `prefers-reduced-motion`:**
  ```css
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; }
  }
  ```

---

## 10. Logo Usage

- **Full-colour logo** on white or very light neutral backgrounds (default for all pages).
- **White logo version** on Authority Blue (`#103190`) backgrounds (nav, footer, hero on blue).
- **Clear space:** Always maintain a margin of at least the height of the 'a' character on all sides.
- **Never:** Stretch, distort, recolour, place on busy photographic backgrounds without a clean overlay, or recreate manually.
- **Consistent placement:** Bottom-right or top-left — pick one position per asset type and hold it permanently.

---

## 11. What to Avoid — Design Non-Negotiables

| ❌ Never Do This |
|---|
| Dark theme as the dominant atmosphere across a full page |
| Script, handwritten, or playful fonts |
| Multiple font families beyond the defined system |
| Generic stock photography or illustrations |
| Pill-shaped buttons |
| Purple, teal, or any colour outside the defined palette |
| Gradients pulling in colours outside the brand palette |
| Busy layouts with competing visual elements |
| Low-contrast text (especially Gold on white, or thin text on images) |
| Heavy or decorative drop shadows |
| Horizontal scroll on any viewport |
| Designs that could belong to any other brand — visual identity must be unmistakable |

---

## 12. Brand Voice in UI Copy

Copy on buttons, labels, headlines, and empty states should match the brand voice:

- **Commanding:** Statements, not suggestions. "Apply to the Marketplace" not "Click here to maybe apply."
- **Precise:** No filler words. Every word earns its place.
- **Culturally fluent:** Speaks the language of African entrepreneurship — ambitious, proud, forward-moving.
- **Alive:** Rhythm in the writing. Short, declarative sentences that breathe.

**Avoid:** "Super excited to...", "Just wanted to...", "As a company, we believe...", generic CTA text like "Learn More" with no context, overuse of exclamation marks.

---

## 13. Quick Reference Card

| Property | Value |
|---|---|
| Theme | Light overall; Authority Blue sections permitted as deliberate moments |
| Primary BG | `#FFFFFF` |
| Headline font | Nunito Sans Expanded Bold |
| Subheadline font | Barlow Condensed SemiBold |
| Body font | Nunito Sans Regular |
| Primary action colour | `#FC490B` Signal Red |
| Primary structure colour | `#103190` Authority Blue |
| Accent | `#FAB909` Gold |
| Warmth | `#C9A077` Sahara Tan |
| Breathing room | `#E8E8E8` Cloud Grey |
| Mobile breakpoint | 375px base, 768px tablet, 1024px desktop |
| Max content width | 1200px |
| Body line height | 1.6 minimum |
| Button radius | 0–4px maximum |
| Red accent bar | Standard on content cards; use with judgment in dense grids |
| Gradients | Permitted when palette-derived and restrained |

---

*MBisAfrican Web Design Reference — Internal Use · Attach to every web build prompt · Version 1.1 · 2026*
