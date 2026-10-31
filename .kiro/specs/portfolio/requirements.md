# Requirements: One-Page Personal Portfolio

## Introduction
A single static `index.html` personal portfolio with inline styles. It has no framework, build step, backend or JavaScript. It must work well on a phone.

## Requirements

### R1: Single-file delivery
**User story:** As the owner, I want one self-contained file so I can host it anywhere.
- R1.1 The deliverable is exactly one file: `index.html`.
- R1.2 All CSS is in a single inline `<style>` block in the `<head>`. No external stylesheets, fonts, images or scripts are loaded.
- R1.3 All content is written directly in the HTML markup.

### R2: Hard constraints
- R2.1 No JavaScript of any kind: no `<script>` tags, no inline event handlers, no `javascript:` URLs.
- R2.2 No framework, no build step, no backend, no form that posts to a server.

### R3: Content
- R3.1 Header shows the owner's name and a one-line role.
- R3.2 Exactly three projects. Each has a title, one sentence, and one link.
- R3.3 Footer shows three contact links: email (`mailto:`), GitHub, LinkedIn.

### R4: Layout
- R4.1 Order top to bottom: header, three project cards, footer.
- R4.2 Uses semantic elements (`header`, `main`, `article`, `footer`).

### R5: Visual style
- R5.1 Dark background.
- R5.2 One accent colour, used for links and highlights only.
- R5.3 Generous spacing between and inside sections.
- R5.4 Text contrast meets WCAG AA (4.5:1 for body text).

### R6: Mobile support
- R6.1 Includes a viewport meta tag.
- R6.2 Readable with no horizontal scrolling at 320px width.
- R6.3 Links and tap targets are at least 44px tall.
- R6.4 Project cards stack in one column on narrow screens and may sit in a grid on wider screens, using CSS only.

### R7: Accessibility and quality
- R7.1 `<html lang="en">`, a `<title>` and a meta description.
- R7.2 Visible focus styles on links.
- R7.3 External links use `rel="noopener noreferrer"`.

## Content (confirmed)
- Name: Stephanie Comendador
- Role: CEO, Software Engineer
- Everything else is a clearly marked placeholder, to be replaced later:
  - Three projects: "Project One/Two/Three", a placeholder sentence, and a `#` or `https://example.com` link each
  - Email: `hello@example.com`
  - GitHub: `https://github.com/your-username`
  - LinkedIn: `https://linkedin.com/in/your-username`

## Palette (confirmed)
Crimson Velvet `#8B0E1A`, Midnight Charcoal `#2C2828`, Burgundy Wine `#6D1A28`, Burnt Amber `#9A5C2A`, Vintage Cream `#E8D8C8`. See design.md for how each is used.
