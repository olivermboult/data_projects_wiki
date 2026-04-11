---
title: Tooltips — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending tooltips in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Tooltips

**Tooltips** provide compact, on-hover contextual help for links, icons and other inline elements. Material for MkDocs can replace the native browser `title` rendering with a consistent, theme-aware tooltip when the feature is enabled.

---

## Tooltips Design standards

!!! success "Dos"
    - **Do** use tooltips for short clarifications (1–2 lines) such as definitions, short hints, or link previews.
    - **Do** prefer inline tooltip content that supplements rather than repeats the main text.
    - **Do** provide clear, plain-language tooltip — avoid long sentences or complex HTML.

!!! failure "Don'ts"
    - **Don’t** put critical instructions or essential information inside tooltips — some users cannot access hover interactions.
    - **Don’t** overload tooltips with links or large blocks of content.
    - **Don’t** rely on tooltips for accessibility-only content; ensure the same meaning is available in the document flow.

---

## Using Tooltips

### Basic Tooltips

Attribute lists can be used to add a `title` to icons or other inline elements:

:material-information-outline:{ title="Important information" }

```md
:material-information-outline:{ title="Important information" }
```

### Link tooltips (inline)

Linked tooltips allow the addition of a title for each link that appears as a tooltip on-hover

[Hover over me](https://example.com "I'm a tooltip link!")

```md
[Hover over me](https://example.com "I'm a tooltip link!")
```

### Link tooltips (reference style)

You can also add tooltips using reference-style links:

[Hover over me too][example]

[example]: https://example.com "I'm a tooltip link!"

```md
[Hover over me too][example]

[example]: https://example.com "I'm a tooltip link!"
```

### Abbreviations

Defining abbreviations will automatically show tooltip-like expansions for acronyms. Abbreviations can be defined by starting with a * and immediately followed by the term or acronym to be associated in square brackets:

The HTML specification is maintained by the W3C.

*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium

```md
The HTML specification is maintained by the W3C.

*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium
```

**Adding a glossary**

The Snippets extension can be used to implement a simple glossary by moving all abbreviations in a dedicated file, and auto-append this file to all pages with the following configuration:

=== "abbreviations.md"
    ```md
	    *[HTML]: Hyper Text Markup Language
        *[W3C]: World Wide Web Consortium
    ```

=== "mkdoc.yml"
	```yml
        markdown_extensions:
            - pymdownx.snippets:
                auto_append:
                    - glossary/abbreviations.md 
    ```
---

## Setting up tooltips

Enable the improved tooltips feature in `mkdocs.yml` and add required Markdown extensions for abbreviations and attribute lists:

```yaml
# mkdocs.yml
theme:
  features:
    - content.tooltips

markdown_extensions:
  - abbr
  - attr_list
  - pymdownx.snippets
```

- **`content.tooltips`**: replaces native `title` rendering with theme-styled tooltips.
- **`abbr`**: supports abbreviation definitions that expand into inline tooltip-like content.
- **`attr_list`**: allows adding `title` attributes on arbitrary elements (icons, spans, etc.).
- **`pymdownx.snippets`**: optional — useful to centralise glossary/abbreviation files and auto-append them to pages.

Note: improved tooltips require Material for MkDocs v9.5.0 or later.

---

??? quote "References"
    - [Material for MkDocs — Tooltips reference](https://squidfunk.github.io/mkdocs-material/reference/tooltips/)
    - [Python Markdown — Attribute Lists](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#attribute-lists)
