---
title: Footnotes — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending footnotes in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Footnotes

**Footnotes** provide a lightweight way to attach citations or short asides without interrupting the main flow.

---

## Footnotes Design Standards

!!! success "Dos"
    - **Do** keep footnotes short and relevant; use them for references or short clarifications.
    - **Do** use footnotes sparingly — too many footnotes clutter the reading experience.

!!! failure "Don'ts"
    - **Don’t** hide essential instructions in footnotes.
    - **Don’t** use footnotes for long-form content; link to a section or appendix instead.

---

## Using Footnotes

Basic Markdown footnote syntax (requires the `footnotes` extension):

Here is a statement.[^1]

[^1]: This is the footnote text.

```md
Here is a statement.[^1]

[^1]: This is the footnote text.
```

Footnote markers are automatically numbered and rendered at the end of the page. Footnotes support inline Markdown formatting.

---

## Setting Up Footnotes

Enable the `footnotes` Markdown extension in `mkdocs.yml`:

```yaml
markdown_extensions:
  - footnotes
```

Notes:
- Footnotes are a Python Markdown extension; ensure your environment includes the relevant package (usually included with the Python Markdown distribution).

---

??? quote "References"
    - [Material for MkDocs — Footnotes reference](https://squidfunk.github.io/mkdocs-material/reference/footnotes/)
