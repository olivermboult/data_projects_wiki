---
title: Grids (Cards) — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending grids in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Grids

Material for MkDocs provides **grid** components to arrange blocks into a clean, responsive rectangular layout. Use grids to present equally important items (cards, short lists, tabs, admonitions) side-by-side on wider screens while stacking on narrow viewports.

---

## Grids Design standards

!!! success "Dos"
    - **Do** use grids for collections of equally important items (e.g., quick links, feature cards, short summaries).
    - **Do** keep each grid item concise — a short title, single sentence, and a link or icon is ideal.
    - **Do** test grids at multiple viewport widths — on mobile they stack vertically, so ensure the first item communicates the main point.
    - **Do** prefer the list syntax for simple card sets and the block syntax when mixing grid items with other block elements.

!!! failure "Don'ts"
    - **Don’t** hide essential instructions or long-form content inside a grid card — use a dedicated page for lengthy material.
    - **Don’t** overload cards with large images or long paragraphs that break the visual rhythm.
    - **Don’t** rely on grids for access control or content hiding — they are presentational only.

---

## Using Grids

Grids come in two main flavours:

- **Card grids** — each item becomes a hover card (good for site index/feature lists). Two syntaxes: list (shortcut) and block (flexible).
- **Generic grids** — arrange arbitrary block elements (admonitions, tabs, lists, code blocks) into a grid.

### Card grid — list syntax (shortcut)

The list syntax is essentially a shortcut for card grids, and consists of a list wrapped by a div with both, the grid and cards classes:

<div class="grid cards" markdown>

 - :fontawesome-brands-html5: __HTML__ for content and structure
 - :fontawesome-brands-js: __JavaScript__ for interactivity
 - :fontawesome-brands-css3: __CSS__ for layout and visuals
 - :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?
 
</div>

```html
<div class="grid cards" markdown>

 - :fontawesome-brands-html5: __HTML__ for content and structure
 - :fontawesome-brands-js: __JavaScript__ for interactivity
 - :fontawesome-brands-css3: __CSS__ for layout and visuals
 - :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?

</div>
```

List items may contain arbitrary Markdown (headings, lists, links, icons) as long as the surrounding `div` includes `markdown`.

<div class="grid cards" markdown>

-   :material-clock-fast:{ .lg .middle } __Set up in 5 minutes__

    ---

    Install [`mkdocs-material`](#) with [`pip`](#) and get up
    and running in minutes

    [:octicons-arrow-right-24: Getting started](#)

-   :fontawesome-brands-markdown:{ .lg .middle } __It's just Markdown__

    ---

    Focus on your content and generate a responsive and searchable static site

    [:octicons-arrow-right-24: Reference](#)

-   :material-format-font:{ .lg .middle } __Made to measure__

    ---

    Change the colors, fonts, language, icons, logo and more with a few lines

    [:octicons-arrow-right-24: Customization](#)

-   :material-scale-balance:{ .lg .middle } __Open Source, MIT__

    ---

    Material for MkDocs is licensed under MIT and available on [GitHub]

    [:octicons-arrow-right-24: License](#)

</div>

```html
<div class="grid cards" markdown>

-   :material-clock-fast:{ .lg .middle } __Set up in 5 minutes__

    ---

    Install [`mkdocs-material`](#) with [`pip`](#) and get up
    and running in minutes

    [:octicons-arrow-right-24: Getting started](#)

-   :fontawesome-brands-markdown:{ .lg .middle } __It's just Markdown__

    ---

    Focus on your content and generate a responsive and searchable static site

    [:octicons-arrow-right-24: Reference](#)

-   :material-format-font:{ .lg .middle } __Made to measure__

    ---

    Change the colors, fonts, language, icons, logo and more with a few lines

    [:octicons-arrow-right-24: Customization](#)

-   :material-scale-balance:{ .lg .middle } __Open Source, MIT__

    ---

    Material for MkDocs is licensed under MIT and available on [GitHub]

    [:octicons-arrow-right-24: License](#)

</div>
```

### Card grid — block syntax

The block syntax allows for arranging cards in grids together with other elements, as explained in the section on generic grids. Just add the card class to any block element inside a grid:

<div class="grid" markdown>

:fontawesome-brands-html5: __HTML__ for content and structure
{ .card }

:fontawesome-brands-js: __JavaScript__ for interactivity
{ .card }

:fontawesome-brands-css3: __CSS__ for text running out of boxes
{ .card }

> :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?

</div>

```html
<div class="grid" markdown>

:fontawesome-brands-html5: __HTML__ for content and structure
{ .card }

:fontawesome-brands-js: __JavaScript__ for interactivity
{ .card }

:fontawesome-brands-css3: __CSS__ for text running out of boxes
{ .card }

> :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?

</div>
```

### Generic grids

Generic grids allow arranging arbitrary block elements in a rectangular shape — useful for mixing lists, tabs, admonitions and code blocks. Wrap the blocks in a `div` with the `grid` class and the `markdown` attribute when using Markdown content inside.

<div class="grid" markdown>

=== "Unordered list"

    * Item one
    * Item two
    * Item three

=== "Ordered list"

    1. First
    2. Second
    3. Third

!!! note "note"
    General supporting information.

</div>

```html
<div class="grid" markdown>

=== "Unordered list"

    * Item one
    * Item two
    * Item three

=== "Ordered list"

    1. First
    2. Second
    3. Third

!!! note "note"
    General supporting information.

</div>
```

### Responsive behaviour

If there isn't enough horizontal space, grid items will expand to the full available width and stack vertically (mobile behaviour). Grids adapt automatically; ensure important content appears in early items.

---

## Setting up grids

Grids rely on a couple of Markdown features. Add these to the `mkdocs.yml` to ensure grid syntax and Markdown-in-HTML work as expected:

```yaml
# mkdocs.yml
markdown_extensions:
  - attr_list
  - md_in_html
```

- **`attr_list`**: enables attribute lists like `{ .card }` used by the block syntax.
- **`md_in_html`**: allows Markdown inside raw HTML containers (required when wrapping lists/blocks in `<div class="grid" markdown>`).

Note: card grids and generic grids were introduced in Material for MkDocs v9.5.0; check the theme version if a syntax is unavailable.

---

??? quote "References"
    - [Material for MkDocs — Grids reference](https://squidfunk.github.io/mkdocs-material/reference/grids/)
    - [List syntax examples (card grids)](https://squidfunk.github.io/mkdocs-material/reference/grids/#using-card-grids)
