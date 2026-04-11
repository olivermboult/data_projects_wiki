---
title: Images — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending images in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Images

**Images** illustrate concepts and should be used thoughtfully to support text.

---

## Image Design Standards

!!! success "Dos"
    - **Do** use descriptive alt text for all images.
    - **Do** optimise images for web (compress, use appropriate formats like WebP when possible).
    - **Do** provide captions or surrounding text that explains the image's purpose.

!!! failure "Don'ts"
    - **Don’t** rely on images as the only way to convey information.
    - **Don’t** include overly large images that slow page loads.

---

## Using images

Markdown image syntax:

```md
![Diagram showing data flow](assets/images/data-flow.png)
```

For responsive images, consider serving multiple sizes and using HTML `picture`/`srcset` where needed. Material supports local `assets` and custom `docs_overrides` folders for images.

To add captions, put the image in a figure with a caption in HTML or use surrounding text.

---

## Setting Up Images

No special Markdown extensions are required for basic images. For responsive or advanced workflows you can:

- Use an image processing pipeline (build step) to generate sizes/formats.
- Use `extra_css` to set max-width and responsive behavior, for example:

```css
.md-typeset img {
  max-width: 100%;
  height: auto;
}
```

Notes:
- Store images under `wiki/wiki_design/assets/images` (or your chosen `docs` assets directory) and reference paths relative to pages.

---

??? quote "References"
    - [Material for MkDocs — Images reference](https://squidfunk.github.io/mkdocs-material/reference/images/)
