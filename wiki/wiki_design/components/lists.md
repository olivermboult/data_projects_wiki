---
title: Lists — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending lists in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Lists

**Lists** improve scanability and organise related items. Choose the right list type for the content.

---

## List Design Standards

!!! success "Dos"
    - **Do** use unordered lists for collections of related items and ordered lists for steps or rank-ordered items.
    - **Do** keep list items short and parallel in structure.

!!! failure "Don'ts"
    - **Don’t** nest lists deeply — flatten or break into sub-sections when needed.
    - **Don’t** use lists for long paragraphs; use paragraphs or tables instead.

---

## Using Lists

Unordered list:

- Item one
- Item two
  - Subitem

```md
- Item one
- Item two
  - Subitem
```

Ordered list:

1. Step one
2. Step two

```md
1. Step one
2. Step two
```

Definition list (Markdown extension `def_list` or HTML):

Term
: Definition for the term.

```md
Term
: Definition for the term.
```

Attribute lists (`attr_list`) can be used to add classes or IDs to lists for styling or behaviour.

---

## Setting Up Admonitions

Most lists work without extra configuration. Consider enabling `attr_list` and `def_list` if you rely on list attributes or definition-style lists:

```yaml
markdown_extensions:
  - attr_list
  - def_list
```
---

??? quote "References"
    - [Material for MkDocs — Lists reference](https://squidfunk.github.io/mkdocs-material/reference/lists/)
