# Margin Notes — DecodeLabs Frontend Project 1: Static Webpage Design

A single-page static website for a fictional second-hand bookshop and reading room, built with HTML and CSS only.

## Project structure

```
margin-notes/
├── index.html            # Page structure (semantic HTML5)
├── css/
│   └── styles.css        # The only stylesheet (no inline styles)
├── images/
│   ├── shelf-hero.avif / .webp
│   ├── shelf-fiction.avif / .webp
│   ├── shelf-history.avif / .webp
│   ├── shelf-poetry.avif / .webp
│   ├── shelf-science.avif / .webp
│   ├── shelf-children.avif / .webp
│   ├── shelf-urdu.avif / .webp
│   └── reading-room.avif / .webp
└── README.md
```

## How to run

Open `index.html` in any modern browser. No build step or server is needed.
(Optional: in VS Code, right-click `index.html` → "Open with Live Server".)

## 1. Information architecture (sitemap, defined first)

```
Home (index.html)
├── Hero ............ what the shop is + main call to action
├── Shelves ......... six categories (Fiction, History, Poetry,
│                     Science and nature, Children's books, Urdu and Hindi)
├── Reading room .... description + opening hours
└── Visit ........... address, selling books, Friday list signup
    Footer .......... contact details
```

Main navigation has 3 items (rule: fewer than 5) and the structure is 2 levels deep (rule: fewer than 3). No catch-all links such as "Quick links" or "Resources".

## 2. Requirements checklist (from the training kit)

| Requirement | How this project meets it |
|---|---|
| **IA:** logical sitemap first | See section 1 above. |
| **HTML:** semantic tags | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<address>`, `<dl>`, `<footer>`. No "div soup". |
| **HTML:** one `<h1>` | Exactly one `<h1>` (hero). Headings go h1 → h2 → h3 with no skipped levels. |
| **CSS:** external file only | All styling lives in `css/styles.css`. Zero `style=""` attributes. |
| **CSS:** DRY / BEM | Reusable blocks such as `.button` with `.button--primary` and `.button--secondary` modifiers, `.card`, `.section`, `.signup`. Colors, fonts and spacing are CSS variables in `:root`. |
| **CSS:** no IDs for styling | The stylesheet uses class selectors only. IDs in the HTML exist only for anchor links, `aria-labelledby` and the form `label for=`. |
| **Layout:** Grid for macro | Grid builds the hero, the shelves card grid, the reading room, the visit section and the footer. |
| **Layout:** Flexbox for micro | Flexbox aligns the header, nav, logo, buttons, card body/meta, hours rows and the signup row. |
| **Assets:** AVIF/WebP | Every image uses `<picture>` with an AVIF source and a WebP fallback. |
| **Assets:** explicit dimensions | Every `<img>` has `width` and `height`, so the browser reserves space and there is no layout shift (CLS). Below-the-fold images use `loading="lazy"`. |
| **A11y:** alt text | Every image has a descriptive `alt`. |
| **A11y:** contrast > 4.5:1 | Body text ≈15:1, secondary text ≈7:1, white on green buttons ≈10:1. The gold accent is used only for decorative lines, never for text. |
| **A11y:** labels | The email field has a visible `<label>`. Skip link, visible keyboard focus, `aria-label` on the nav, reduced-motion support. |
| **Responsive** | 3 columns on desktop, 2 on tablet, 1 on mobile. |

## 3. Quality gate — how to validate

1. **W3C HTML:** upload `index.html` at https://validator.w3.org/#validate_by_upload
2. **W3C CSS:** upload `css/styles.css` at https://jigsaw.w3.org/css-validator/#validate_by_upload
3. **Lighthouse:** open the page in Chrome → DevTools (F12) → Lighthouse tab → check Performance, Accessibility, Best Practices and SEO → Analyze.

## Notes

- Font: Literata from Google Fonts, falling back to Georgia if offline.
- The bookshelf illustrations were generated for this project, so there are no licensing issues.
- The shop name, address, phone number and email are placeholders.
