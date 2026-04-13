---
title: Heros — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending heros in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Heros

**Hero banners** (or "heros") are large, attention-grabbing headers used to provide page context and highlight the most important information on a page. Use them sparingly — they are intended for top-level pages or sections that need prominent emphasis.

---

## Hero Design Standards

!!! success "Dos"
    - **Do** use a hero to communicate the primary purpose of the page with a short title and one-line subtitle.
    - **Do** keep titles concise (one short sentence or phrase) and subtitles to a single supporting sentence.
    - **Do** reserve large hero sizes (`hero--lg`) for high-level landing pages only.
    - **Do** provide a kicker (`hero__kicker`) when content needs a small contextual label (e.g., Draft, Published).

!!! failure "Don'ts"
    - **Don’t** place multiple heroes on the same page.
    - **Don’t** use long paragraphs or complex controls inside a hero — keep it lightweight.
    - **Don’t** rely on colour alone to convey status; combine with clear text (kicker) when relevant.

---

## Using Heros

Below are the current hero variants used across the design system. Each example shows the rendered hero and the HTML you can copy.

<div class="hero hero--deep-indigo hero--lg" markdown="1">
  <div class="hero__inner">
    <h1 class="hero__title">Data Platform Design</h1>
    <p class="hero__subtitle">Patterns, standards, and reusable components for delivery.</p>
  </div>
</div>

```html
<div class="hero hero--deep-indigo hero--lg" markdown="1">
  <div class="hero__inner">
    <h1 class="hero__title">Data Platform Design</h1>
    <p class="hero__subtitle">Patterns, standards, and reusable components for delivery.</p>
  </div>
</div>
```

<div class="hero hero--data-blue hero--md" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Draft</p>
    <h1 class="hero__title">Work in progress</h1>
    <p class="hero__subtitle">This page contains placeholders and needs review.</p>
  </div>
</div>

```html
<div class="hero hero--data-blue hero--md" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Draft</p>
    <h1 class="hero__title">Work in progress</h1>
    <p class="hero__subtitle">This page contains placeholders and needs review.</p>
  </div>
</div>
```

<div class="hero hero--dark-teal hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>

```html
<div class="hero hero--dark-teal hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>
```

<div class="hero hero--burgundy hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>

```html
<div class="hero hero--burgundy hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>
```

<div class="hero hero--clear-sky hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>

```html
<div class="hero hero--clear-sky hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>
```

<div class="hero hero--golden hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>

```html
<div class="hero hero--golden hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>
```

<div class="hero hero--lavender hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>

```html
<div class="hero hero--lavender hero--sm" markdown="1">
  <div class="hero__inner">
    <p class="hero__kicker">Published</p>
    <h1 class="hero__title">Production-ready pattern</h1>
    <p class="hero__subtitle">Validated and approved for reuse across projects.</p>
  </div>
</div>
```

---


## Setting Up Heros

Heros are simple HTML elements styled by the project's stylesheet. Ensure your `mkdocs.yml` includes the Material theme and your custom CSS where hero styles are defined (typically in `style.css`):

```yaml
# mkdocs.yml
theme:
  name: material
  custom_dir: wiki/wiki_design

extra_css:
  - styles/style.css
```

If you need custom hero colours or sizes, add variants in `styles/style.css` following the existing naming convention (e.g., `.hero--indigo`, `.hero--lg`).

---

??? quote "References"
    - [Material for MkDocs — Customisation guide](https://squidfunk.github.io/mkdocs-material/customization/)
