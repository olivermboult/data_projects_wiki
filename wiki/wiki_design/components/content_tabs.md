---
title: Content Tabs — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending content tabs in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---
# Content Tabs

**Content tabs** are styled blocks used to organise related pieces of content into compact tabbed panels. Material for MkDocs provides multiple built‑in content tab styles.

---

## Content Tabs Design standards

!!! success "Dos"
	- **Do** use tabs to group closely related content (e.g., different views of the same data, language variants of a code sample, or short reference lists).
	- **Do** keep each tab short — readers expect tab panes to be concise (roughly a few paragraphs or a short list).
	- **Do** include the most important information in the first/primary tab so mobile users (stacked layout) see it first.
	- **Do** label tabs clearly and succinctly; use plain language that describes the content (not implementation details).

!!! failure "Don'ts"
	- **Don’t** hide essential instructions or warnings inside a secondary tab; tabs are visual affordances and not discoverable by all users.
	- **Don’t** put very long documents inside tabs — consider headings or separate pages for long-form content.
	- **Don’t** rely on tabs for access control or to hide sensitive content — tabs are purely presentational.
	- **Don’t** use ambiguous tab labels such as `Info` or `More` without context.

---

## Using Content Tabs

### Basic Content Tabs

Content tabs start with `===` followed by the tab label in quotes. The content follows on the next line, indented by **four spaces**.

=== "Overview"
	This is the Overview tab. Use normal Markdown here.

	- Summary line 1
	- Summary line 2

=== "Details"
	This is the Details tab. Add more content here.

```md
=== "Overview"
	This is the Overview tab. Use normal Markdown here.

	- Summary line 1
	- Summary line 2

=== "Details"
	This is the Details tab. Add more content here.
```

---

### Embedded Content Tabs

When SuperFences is enabled, content tabs can contain arbitrary nested content, including further content tabs, and can be nested in other blocks like admonitions or blockquotes:

!!! example

    === "Unordered List"
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci

    === "Ordered List"
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci

```md
    !!! example

    === "Unordered List"
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci

    === "Ordered List"
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci
```

---

## Setting Up Admonitions

Within the `mkdocs.yml` file, enable:

- `pymdownx.tabbed` 
- `pymdownx.superfences` (strongly recommended when nesting fenced blocks inside tabs or when using nested tab groups.)
- `alternate_style`(the theme supports an alternate visual style for tabs — set this to `true` to use the theme’s alternate tab visuals)

Material’s reference configuration shows these extensions together for full functionality. 

```yaml
# mkdocs.yml
markdown_extensions:
  - pymdownx.tabbed:
      alternate_style: true
  - pymdownx.superfences
```

---

??? quote "References"
	- [Material for MkDocs — Content tabs reference](https://squidfunk.github.io/mkdocs-material/reference/content-tabs/)
	- [pymdownx.tabbed documentation](https://facelessuser.github.io/pymdown-extensions/extensions/tabbed/)

