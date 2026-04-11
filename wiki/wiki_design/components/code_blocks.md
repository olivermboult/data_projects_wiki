---
title: Code Blocks — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending code blocks in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Code blocks

**Code blocks** are core to technical documentation. Material for MkDocs supports build-time highlighting (Pygments) and runtime highlighters, copy/select buttons, annotations and more.

---

## Code Blocks Design Standards

!!! success "Dos"
    - **Do** include a language hint after the opening fence for accurate highlighting.
    - **Do** add a `title="filename"` when showing source files to give context to readers.
    - **Do** use annotations for explanatory notes tied to specific lines, not for essential information.

!!! failure "Don'ts"
    - **Don’t** rely on color alone — include language and clear comments for readers.
    - **Don’t** paste extremely large files verbatim; link to sources or use snippets when appropriate.

---

## Using Code Blocks

Basic fenced block with language:

```py
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

```md
    ```py
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
```

Add a title (useful when showing filenames):

```py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

```md
    ```py title="bubble_sort.py"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
```

Line numbers (start from `1` or another number):

```py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

```md
    ```py linenums="1"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
```

Highlight specific lines using `hl_lines`:

```py hl_lines="2 3"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

```md
    ```py hl_lines="2 3"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
```

Code annotations (place numbered markers inside language comments and provide the numbered list below the block):

```yaml
theme:
  features:
    - content.code.annotate #(1)
```

1. :man_raising_hand: Annotations can contain Markdown and images.


```md
    ```yaml
    theme:
      features:
        - content.code.annotate #(1)
    ```

    1. :man_raising_hand: Annotations can contain Markdown and images.
```

---

## Configuration / Setup

Enable recommended Markdown extensions in `mkdocs.yml`:

```yaml
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
```

Enable theme features for copy/select/annotations in `mkdocs.yml`:

```yaml
theme:
  name: material
  features:
    - content.code.copy    # shows copy button on code blocks 
    - content.code.select  # shows select button to highlight line ranges
    - content.code.annotate # enables code annotations
```

---

**Code Blocks Colours**

You can tweak the theme’s syntax colours via CSS variables (for example `--md-code-hl-string-color`) or add an extra stylesheet to override specifics.

To increase the width of annotation tooltips, add to your extra CSS:

```css
/* 
  Code (base) - Affects: inline code + code blocks base background/foreground. 
*/
  --md-code-fg-color: var(--wiki-tea-green-95-l);               /* Code text */
  --md-code-bg-color: var(--wiki-indigo-code-background);       /* Code block & inline code background */

/*
  Code highlighting tokens - Affects: token colors in highlighted code blocks.
*/
  --md-code-hl-color: hsl(from var(--wiki-mustard) h s l / 0.22);   /* Highlighted line background / emphasis */
  --md-code-hl-number-color: var(--wiki-red);                       /* Numbers */
  --md-code-hl-special-color: var(--wiki-mexican-pink-20-l);        /* Special tokens (decorators, special names) */
  --md-code-hl-function-color: var(--wiki-persian-green-20-l);      /* Function names */
  --md-code-hl-constant-color: var(--wiki-bleu-20-l);               /* Constants */
  --md-code-hl-keyword-color: var(--wiki-bleu-20-l);                /* Keywords (if/else/return) */
  --md-code-hl-string-color: var(--wiki-emerald-20-l);              /* Strings */
  --md-code-hl-name-color: var(--md-code-fg-color);                 /* General “name” tokens default to code fg */
  --md-code-hl-operator-color: var(--md-default-fg-color--light);   /* Operators */
  --md-code-hl-punctuation-color: var(--md-default-fg-color--light);/* Punctuation */
  --md-code-hl-comment-color: var(--wiki-indigo-50-l);              /* Comments (muted) */
  --md-code-hl-generic-color: var(--md-default-fg-color--light);    /* Generic tokens */
  --md-code-hl-variable-color: var(--md-default-fg-color--light);   /* Variables */

```

---

??? quote "References"
    - [Material for MkDocs — Code blocks reference](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/)
