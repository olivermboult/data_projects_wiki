---
title: Annotations — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending annotations in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Annotations

**Annotations** are inline markers that expand a small panel containing arbitrary Markdown when clicked or focused. They’re useful for providing optional clarifications, footnotes, or short asides without cluttering the main content.

---

## Annotation Design Standards

!!! success "Dos"
    - **Do** use annotations for optional clarifications and small side notes.
    - **Do** keep annotation content concise but allow formatted text, code, and images where helpful.
    - **Do** ensure markers are discoverable and numbered or iconified consistently across a page.

!!! failure "Don'ts"
    - **Don’t** hide critical warnings behind annotations — annotations should be optional, not mandatory instructions.
    - **Don’t** overuse annotations on dense content — many markers make pages harder to scan.

---

## Using Annotations

Annotations require the `annotate` class on the outer block that contains the inline markers. Markers are placed inline (for example `(1)`) and the content for each marker is provided in a subsequent ordered list.

### Basic inline annotation

Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! I can contain `code`, **formatting**, and images.

```md
Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! I can contain `code`, **formatting**, and images.

```

This renders the numbered marker in the paragraph; clicking or focusing it opens the annotation content.

### Nested annotations

When `pymdownx.superfences` is enabled you can nest annotations by adding `annotate` to nested list items.

Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! (1)
    { .annotate }

    1. :woman_raising_hand: I'm nested inside the annotation.

```md
Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! (1)
    { .annotate }

    1. :woman_raising_hand: I'm nested inside the annotation.

```

### Annotations inside admonitions, tabs and other blocks

Add `{ .annotate }` to the outermost block (admonition, content tab, blockquote, etc.).

Admonition with annotations:

!!! note annotate "Title (1)"

    This paragraph references (1) and is annotated.

1. :man_raising_hand: Annotation content for the admonition.

```md
!!! note annotate "Title (1)"

    This paragraph references (1) and is annotated.

1. :man_raising_hand: Annotation content for the admonition.

```

Content tabs with annotations use the same pattern — add `annotate` to the tab block that contains markers.

### Arbitrary elements / HTML wrapper

For elements not supported by attribute lists, wrap content in HTML and apply the `annotate` class (requires `md_in_html`):

<div class="annotate" markdown>

> A quoted sentence with a marker (1).

</div>

1. :man_raising_hand: Annotation content for the HTML-wrapped block.

```html
<div class="annotate" markdown>

> A quoted sentence with a marker (1).

</div>

1. :man_raising_hand: Annotation content for the HTML-wrapped block.

```

---

## Setting Up Annotations

Within the `mkdocs.yml` file, enable:

- attr_list             (attribute lists for `{ .annotate }`)
- md_in_html            (allows markdown inside HTML blocks)
- pymdownx.superfences  (strongly recommended to support nesting of annotations)

```yaml
markdown_extensions:
  - attr_list      
  - md_in_html       
  - pymdownx.superfences
```

Optional: change the annotation marker/icon used by the theme via `theme.icon.annotation` in `mkdocs.yml`:

```yaml
theme:
  icon:
    annotation: material/arrow-right-circle
```

Notes:
- Annotations were introduced in Material for MkDocs v9.2.0 and may be experimental in some older versions.
- Annotations currently do not work in scrollable data tables.

---

??? quote "References"
    - [Material for MkDocs — Annotations reference](https://squidfunk.github.io/mkdocs-material/reference/annotations/)
