---
title: Maths — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending mathematical notation in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Maths

!!! draft
    This page is still being created, some of the details maybe incorrect or formatted incorrectly.


**Mathematical notation** helps explain formulas and algorithms; render them clearly and accessibly.

---

## Design Standards

!!! success "Dos"
    - **Do** prefer short inline expressions for simple formulas and display math for larger equations.
    - **Do** provide a brief textual explanation of the equation when needed.

!!! failure "Don'ts"
    - **Don’t** rely solely on complex equations to explain concepts — include plain-language interpretation.

---

## Using Mathematical Notation

Material sites commonly use KaTeX for rendering math. Inline math example (LaTeX syntax): $e^{i\pi} + 1 = 0$.

Display Maths example:

$$
\int_{0}^{\infty} e^{-x} \,dx = 1
$$

When authoring:
- Use `$...$` for inline math and `$$...$$` for display math.
- Keep expressions readable and avoid deeply nested notations when possible.

---

## Setting Up Mathematical Notation

Enable a math extension and provide KaTeX resources. Example `mkdocs.yml` snippets:

```yaml
markdown_extensions:
  - pymdownx.arithmatex

extra_javascript:
  - https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.js

extra_css:
  - https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.css
```

Material may also provide tighter integration or recommend specific extension options; consult the reference for the current recommended configuration.

---

??? quote "References"
    - [Material for MkDocs — Maths reference](https://squidfunk.github.io/mkdocs-material/reference/math/)
