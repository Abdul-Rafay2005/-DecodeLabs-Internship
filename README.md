# Arcova — Landing Page

A fully self-contained, single-file HTML landing page for **Arcova**, a fictional SaaS product platform. Built with semantic HTML5, vanilla CSS (custom properties + container queries), and vanilla JavaScript — zero dependencies, zero build step.

---

## Features

- **Splash / Loader** — animated logo pulse and progress bar on first load
- **Scroll progress bar** — fixed top indicator that tracks page position
- **Sticky header** — blurred glass-morphism nav that gains a shadow on scroll
- **Dark / Light mode** — toggle persisted to `localStorage`; respects the user's saved preference on return visits
- **Mobile navigation** — hamburger menu with animated open/close, dismissable via Escape key
- **Hero section** — responsive two-column layout with a floating animated metrics card and growth badge
- **Features / About section** — icon list + stats tiles with container-query-driven layout
- **Pricing section** — three-tier card grid with a monthly ↔ yearly billing toggle (20 % discount applied live)
- **Testimonials carousel** — infinitely scrolling track, pauses on hover, masked edges
- **FAQ accordion** — single-open accordion with smooth `max-height` animation
- **Contact form** — client-side validation with inline error messages and a toast confirmation
- **Footer** — four-column responsive grid with social links
- **Back-to-top button** — appears after 400 px scroll, smooth-scrolls to top
- **Scroll reveal** — `IntersectionObserver`-driven fade-in for all major sections
- **Full accessibility** — skip link, ARIA labels/roles, `aria-expanded`, `aria-invalid`, `focus-visible` outlines, `prefers-reduced-motion` support

---

## Tech Stack

| Layer | Choice |
|---|---|
| Markup | Semantic HTML5 |
| Styling | Vanilla CSS — custom properties, `clamp()`, container queries, CSS animations |
| Scripting | Vanilla JavaScript (ES2020+) |
| Fonts | Google Fonts — DM Serif Display + DM Sans |
| Dependencies | **None** |

---

## File Structure

```
index.html   ← entire project lives here (styles + markup + scripts)
README.md
```

---

## Getting Started

No build tools required. Just open the file in a browser:

```bash
# Option 1 — open directly
open index.html

# Option 2 — serve locally (avoids any browser file:// quirks)
npx serve .
# or
python -m http.server 8080
```

---

## Customisation

### Branding & Colors

All colours are defined as CSS custom properties at the top of the `<style>` block:

```css
:root {
  --mocha:       #A5856E;   /* primary accent */
  --blue:        #A0D4E0;   /* secondary accent */
  --bg:          #fffefb;   /* page background (light) */
  --ink:         #2a2118;   /* body text (light) */
  /* … */
}
```

Dark-mode overrides live in the `[data-theme="dark"]` block immediately below.

### Pricing

Each `.card-price` element carries `data-monthly` / `data-yearly` (and optional `-period`) attributes. Update those values to change displayed prices without touching the JS.

```html
<div class="card-price"
     data-monthly="$49"  data-monthly-period="/mo"
     data-yearly="$39"   data-yearly-period="/mo">
  $49 <span>/mo</span>
</div>
```

### Contact Details

Replace the email, phone, and office address in the `<address>` block inside `#contact`.

### Copy & Content

All section text is plain HTML — find and edit directly. No templating engine or CMS is involved.

---

## Accessibility

- Skip-to-content link at the top of `<body>`
- All interactive elements are keyboard-navigable
- `aria-expanded`, `aria-pressed`, `aria-invalid`, `aria-live`, and `aria-label` attributes throughout
- `prefers-reduced-motion` media query disables animations for users who prefer it
- Colour contrast meets WCAG 2.1 AA for both light and dark themes

---

## Browser Support

Targets evergreen browsers (Chrome 105+, Firefox 110+, Safari 16+, Edge 105+). Container queries and `clamp()` are used extensively — no polyfills are included.

---

## Contact

Built for **Arcova, Inc.**  
Email: Rafay@arcova.io  
Phone: +92 3152462949  
Office: Karachi, Pakistan  

© 2026 Arcova, Inc. All rights reserved.
