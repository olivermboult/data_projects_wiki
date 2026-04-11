---
title: Wiki Branding Guidelines
description: Visual tokens, typography, imagery, spacing and interactive rules for the Data Platform wiki.
---

# Branding Guidelines — Data Platform Wiki

This page summarises the visual system and practical rules for creating consistent, accessible and attractive pages across the wiki. Use the `page-template.md` for structuring pages and this document for visual/interaction rules.

---

## Colours (tokens)
The wiki defines CSS variables in `wiki/_assets/styles/style.css`. Use these canonical tokens rather than hard-coded hex values.

Primary brand colours (examples):
- `--wiki-indigo`: #185B84 — primary brand
- `--wiki-bleu`: #0395FA — interactive accents
- `--wiki-midnight-green`: #00515C
- `--wiki-persian-green`: #1DAB98
- `--wiki-emerald`: #00D987
- `--wiki-mustard`: #FFDE83 — highlights
- `--wiki-mexican-pink`: #DC0D7F — strong emphasises

Admonition colour mapping (use `!!! note`, `!!! tip`, `!!! warning`, etc.):
- Note / neutral: `--wiki-ad-note` (indigo)
- Info: `--wiki-ad-info` (bleu)
- Tip / success: `--wiki-ad-tip` / `--wiki-ad-success` (persian/green)
- Failure / danger: `--wiki-ad-failure` / `--wiki-ad-danger` (red)

Accessibility:
- Use the CSS tokens which include light/dark variants; validate contrast (WCAG AA minimum for body text).

---

## Typography
- Primary site font: `wiki_font` (Silka) configured in `style.css` as `--md-text-font` and `--md-header-font`.
- Code font: `Roboto Mono` via `--md-code-font` for inline/code blocks.

Guidelines:
- Use headings in hierarchical order (H1 only once per page, H2 for main sections). The `page-template.md` enforces this pattern.
- Keep line length readable (60–85 characters) in prose paragraphs.

---

## Spacing & Layout
- Use default MkDocs Material container widths; avoid full-width content except for hero/banner patterns.
- Use consistent spacing for section dividers (`---`) to create clear separation.
- For grids, use the `grids.md` component guidance to structure examples and feature lists.

---

## Imagery & Icons
- Store images under `wiki/_assets/images` and link relatively.
- Use `hero` images for top-level pages only. Keep imagery simple, on-brand, and meaningful.
- Icons: prefer Material icon shortcodes (see `components/icons_emojis.md`).

Image accessibility:
- Provide `alt` text for all images.
- Avoid text embedded in images unless necessary; provide equivalent HTML/text where possible.

---

## Interactive patterns (best practices)
- Use tabs (`content_tabs.md`) for showing multiple representations (code / output / explanation).
- Use admonitions for short callouts (do/don'ts, quick tips).
- Keep code examples minimal and runnable where possible.
- Provide download links or copyable snippets for users to use directly.

---

## Component usage
Link to the component docs in `wiki/wiki_design/components` when referencing patterns (buttons, heros, lists, diagrams). Reuse examples from those files rather than inventing new variants.

---

## Accessibility and testing
- Run color-contrast checks for any custom palette additions.
- Verify keyboard navigation for interactive widgets (tabs, toggles).
- Ensure headings, lists and tables have proper semantic HTML when rendered.

---

## Quick checklist for new pages
- [ ] Use `page-template.md` front matter and structure.
- [ ] Set `title`, `description`, `icon` and `status` front matter.
- [ ] Add `Owner` and `Last reviewed` metadata.
- [ ] Use component docs for patterns and avoid custom styles unless necessary.
- [ ] Validate accessibility (contrast and keyboard)

---

## References & assets
- Stylesheet with tokens: `wiki/_assets/styles/style.css`
- Component reference: `wiki/wiki_design/components`
- Page template: `wiki/wiki_design/page-template.md`
