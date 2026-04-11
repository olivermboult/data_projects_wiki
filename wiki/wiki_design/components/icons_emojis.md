---
title: Icons & Emojis — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending icons & emojis in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Icons & Emojis

**Icons** and **emojis** help convey meaning quickly — use them sparingly and consistently.

---

## Design Standards

!!! success "Dos"
    - **Do** use icons to reinforce meaning, not replace clear text.
    - **Do** prefer the theme’s icon shortcodes (Material, Octicons, Font Awesome) for consistency.
    - **Do** include accessible text when an icon conveys important information.

!!! failure "Don'ts"
    - **Don’t** overuse emojis in formal documentation.
    - **Don’t** rely on icons alone for semantic meaning; include text labels.

---

## Using Icons & Emojis

Material supports built-in icon shortcodes and emoji. Examples:

Inline icon shortcode (Material icons):

This is important :material-check:

```md
This is important :material-check:
```

Font Awesome example (if enabled):

Send :fontawesome-solid-paper-plane:

```md
Send :fontawesome-solid-paper-plane:
```

Emoji usage:

We shipped the feature 🎉

```md
We shipped the feature 🎉
```

To use an external icon set like Font Awesome, enable the CSS in `mkdocs.yml` and use the matching shortcode or HTML.

---

## Setting Up Icons & Emojis

Material ships with multiple icon sets. To override or add icons in `mkdocs.yml`:

```yaml
theme:
  icon:
    logo: material/rocket
    annotation: material/arrow-right-circle
```

To enable Font Awesome shortcodes, add the stylesheet via `extra_css` (or host locally):

```yaml
extra_css:
  - https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css
```

Notes:
- Shortcodes map to CSS class names under the hood; refer to the Material reference for the exact shortcode names.

---

??? quote "References"
    - [Material for MkDocs — Icons & Emojis reference](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/)
