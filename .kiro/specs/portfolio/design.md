# Design: One-Page Personal Portfolio

## Structure
```
index.html
└─ <html lang="en">
   ├─ <head>: charset, viewport, title, description, <style>
   └─ <body>
      ├─ <header>  h1 (name) + p (role)
      ├─ <main>    h2 "Projects" (visually subtle)
      │            └─ 3 × <article class="card">: h3, p, a
      └─ <footer>  nav of 3 links: Email, GitHub, LinkedIn
```

## Visual design
Palette supplied by the owner:

| Name | Hex |
|---|---|
| Crimson Velvet | `#8B0E1A` |
| Midnight Charcoal | `#2C2828` |
| Burgundy Wine | `#6D1A28` |
| Burnt Amber | `#9A5C2A` |
| Vintage Cream | `#E8D8C8` |

Token mapping:

| Token | Value | Purpose |
|---|---|---|
| `--bg` | Midnight Charcoal `#2C2828` | Page background |
| `--surface` | Burgundy Wine `#6D1A28` | Card background (cream text on it is about 8.3:1) |
| `--text` | Vintage Cream `#E8D8C8` | Body text (about 10:1 on bg) |
| `--muted` | Vintage Cream at about 75% opacity | Role, secondary text |
| `--accent` | Crimson Velvet `#8B0E1A` | The single accent: link buttons and highlights, always filled with cream text on top (about 6.9:1) |

Contrast note: Crimson (about 1.5:1) and Amber (about 2.7:1) fail AA as text on Charcoal. Neither is used as a text colour.

Burnt Amber is intentionally left out (owner decision), to keep to one accent.

- Typography: system font stack (`system-ui, -apple-system, "Segoe UI", Roboto, sans-serif`). No web fonts.
- Fluid headings with `clamp()`, for example the h1 at `clamp(2rem, 8vw, 3.5rem)`.
- Spacing: container `max-width: 960px`, side padding `1.5rem`, section padding `4rem` top and bottom, card padding `1.75rem`, grid gap `1.5rem`.

## Layout and responsiveness
- Mobile first. Cards are a single column by default.
- `@media (min-width: 720px)` switches the card container to `grid-template-columns: repeat(3, 1fr)`. Alternatively, `repeat(auto-fit, minmax(240px, 1fr))` avoids a breakpoint.
- Links get `display: inline-block; min-height: 44px; line-height: 44px` for tap targets.
- Footer links wrap with flexbox and `gap`.

## Interaction (CSS only)
- `a:hover` and `a:focus-visible` get an accent outline or underline.
- `.card:hover` gets an accent border colour, with a short `transition`.
- `prefers-reduced-motion` disables transitions.

## Accessibility
- Semantic landmarks, one `h1`, ordered headings.
- Link text is descriptive, for example "View project: Title →".
- External links use `target="_blank"` only if wanted. The default is to open in the same tab, with `rel="noopener noreferrer"` kept on all external links.

## Constraints check
No `<script>`, no external requests, no forms, no images. A single file with a single `<style>` block.

## Verification plan
- `grep -ci "<script\|onclick\|javascript:" index.html` returns 0.
- Check that the file has exactly one `<style>` and no `<link rel=stylesheet>`.
- Render at 320px and 1280px in a headless browser and check for horizontal overflow.
