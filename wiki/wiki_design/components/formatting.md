---
title: Formatting — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending formatting in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Formatting

Consistent **formatting** improves readability and sets expectations across documentation.

---

## Design Standards

!!! success "Dos"
    - **Do** use headings to structure content and keep paragraphs short.
    - **Do** prefer active voice and imperative verbs for procedural instructions.
    - **Do** use code formatting for identifiers and command fragments.

!!! failure "Don'ts"
    - **Don’t** overuse emphasis (bold/italic) — reserve for meaningful emphasis.
    - **Don’t** rely on case differences alone to convey important distinctions.

---

## Using Formatting

### Basic Built-in Formatting

Common Markdown patterns:

- Inline code: ``Use `git pull` to fetch changes.``
- Code blocks: fenced with ``` and language hint for syntax highlighting.
- Links: `[label](url)` or reference-style links for repeated destinations.
- Emphasis: `*italic*` for subtle emphasis, `**bold**` for stronger emphasis.

### Advanced Formatting

**Highlighting changes**

When Critic is enabled, Critic Markup can be used, which adds the ability to highlight suggested changes, as well as add inline comments to a document:

Text can be {--deleted--} and replacement text {++added++}. This can also be
combined into {~~one~>a single~~} operation. {==Highlighting==} is also
possible {>>and comments can be added inline<<}.

{==

Formatting can also be applied to blocks by putting the opening and closing
tags on separate lines and adding new lines between the tags and the content.

==}

```md
    Text can be {--deleted--} and replacement text {++added ++}. This can also be
    combined into {~~one~>a single~~} operation.    {==Highlighting==} is also
    possible {>>and comments can be added inline<<}.

    {==

    Formatting can also be applied to blocks by putting the     opening and closing
    tags on separate lines and adding new lines between the     tags and the content.
    ==}
```

**Highlighting Text**

When Caret, Mark & Tilde are enabled, text can be highlighted with a simple syntax, which is more convenient that directly using the corresponding `mark`, `ins` and `del` HTML tags:

- ==This was marked (highlight)==
- ^^This was inserted (underline)^^
- ~~This was deleted (strikethrough)~~

```md
- ==This was marked (highlight)==
- ^^This was inserted (underline)^^
- ~~This was deleted (strikethrough)~~
```

**Subscript & Superscript**

When Caret & Tilde are enabled, text can be sub- and superscripted with a simple syntax, which is more convenient than directly using the corresponding `sub` and `sup` HTML tags:

- H~2~O
- A^T^A

```md

- H~2~O
- A^T^A

```

**Keyboard Keys**

When Keys is enabled, keyboard keys can be rendered with a simple syntax. 

++ctrl+alt+del++

```md
++ctrl+alt+del++
```

---

## Setting Up Formatting

Most formatting works out-of-the-box with Markdown. Consider enabling helpful extensions in `mkdocs.yml` (details above):

```yaml
markdown_extensions:
  - pymdownx.critic
  - pymdownx.caret
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.tilde
```

---

??? quote "References"
    - [Material for MkDocs — Formatting reference](https://squidfunk.github.io/mkdocs-material/reference/formatting/)
