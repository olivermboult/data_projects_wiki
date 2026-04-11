---
title: Data Tables — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending data tables in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Data Tables

Material for MkDocs provides well‑styled Markdown **data tables** for presenting structured data. Use data tables for medium-sized datasets where tabular layout improves scanability.

---

## Design Standards

!!! success "Dos"
    - **Do** keep tables concise and readable; prefer fewer columns and clear headings.
    - **Do** provide units, sorting hints or notes in column headers where appropriate.
    - **Do** use column alignment (left/center/right) to improve numeric readability.

!!! failure "Don'ts"
    - **Don’t** put large free-form text or long paragraphs inside table cells.
    - **Don’t** rely on tables for layout — use grids for layout needs.
    - **Don’t** place essential information only inside scrollable tables; surface critical items in the main content.

---

## Using Data Tables

### Basic Built-in Data Tables

| Method  | Description                         |
| ------- | ----------------------------------- |
| `GET`   | :material-check: Fetch resource    |
| `PUT`   | :material-check-all: Update        |
| `DELETE`| :material-close: Delete resource   |

```md
| Method  | Description                         |
| ------- | ----------------------------------- |
| `GET`   | :material-check: Fetch resource    |
| `PUT`   | :material-check-all: Update        |
| `DELETE`| :material-close: Delete resource   |
```

Column alignment uses the standard Markdown syntax (colons in the divider row):

| Left | Center | Right |
| :--- | :----: | ----: |
| a    | b      | 1     |

```md
| Left | Center | Right |
| :--- | :----: | ----: |
| a    | b      | 1     |
```

Notes:
- Tables accept arbitrary inline Markdown (inline code, emojis, icons).
- Data tables are often rendered as horizontally scrollable on narrow viewports — avoid hiding critical content in the horizontal overflow.

---

## Setting Up Data Tables

Ensure Markdown table support is enabled (this is usually on by default). In `mkdocs.yml`:

```yaml
markdown_extensions:
  - tables
```

---

??? quote "References"
    - [Material for MkDocs — Admonitions reference](https://squidfunk.github.io/mkdocs-material/reference/data-tables/)
    - [mkdocs-table-reader-plugin](https://timvink.github.io/mkdocs-table-reader-plugin/)
