---
title: Wiki Formatting Quick Reference
description: One-page quick reference card for common Markdown syntax, admonitions, colors, and formatting rules used in the Data Projects Wiki.
---

# Wiki Formatting Quick Reference

Bookmark this page for quick access to common Markdown syntax, formatting rules, and design standards.

---

## YAML Front Matter

Every page must start with:

```yaml
---
title: Page Title (60–80 characters)
description: Brief summary for metadata (60–160 characters).
---
```

---

## Headings & Structure

```markdown
# Page Title (use once per page)
## Section Heading
### Subsection
#### Detail Heading (rare)

---
```

**Rule:** One `#` per page; use `##`, `###` for sections; never skip levels.

---

## Emphasis & Formatting

| Element | Syntax | Example |
|---------|--------|---------|
| Bold | `**text**` | **important** |
| Italic | `*text*` | *optional* |
| Inline code | `` `code` `` | `` `git pull` `` |
| Code block | ` ```language` / code / ` ``` ` | (see below) |
| Link | `[text](url)` | [Link](../page.md) |
| Image | `![alt](path)` | ![Logo](../logo.png) |
| Strikethrough | `~~text~~` | ~~old~~ |
| Highlight | `==text==` | ==important== |

---

## Code Blocks

```markdown
    ```python
    print("Hello")
    ```
```

**With title:** `` ```python title="filename.py" ``

**With line numbers:** `` ```python linenums="1" ``

**With highlights:** `` ```python hl_lines="2" ``

---

## Admonitions (Callouts)

```markdown
!!! type "Optional Title"
    Content here (indented 4 spaces).
    Multiple paragraphs supported.
```

**Collapsible:** Use `???` instead of `!!!`

### Types & When to Use

| Type | Use When |
|------|----------|
| `note` | General information |
| `tip` | Best practice, helpful hint |
| `success` | Positive outcome, confirmation |
| `info` | Neutral information |
| `question` | Question or prompt |
| `warning` | Caution, something might go wrong |
| `danger` | Critical action, high risk |
| `failure` | Anti-patterns, what NOT to do |
| `bug` | Known issue, limitation |
| `example` | Example or demonstration |
| `abstract` | Summary, TL;DR |
| `quote` | Blockquote or reference |

---

## Lists

### Unordered

```markdown
- Item 1
- Item 2
  - Nested item
- Item 3
```

### Ordered

```markdown
1. Step 1
2. Step 2
   1. Sub-step
3. Step 3
```

---

## Tables

```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |
```

---

## Links & References

```markdown
[Inline link](https://example.com)
[Relative link](../path/page.md)

[Reference link][ref]
[ref]: https://example.com
```

**Internal links should use relative paths starting with `../`**

---

## Colors & Design Tokens

**Never hardcode hex values.** Use CSS variables defined in `style.css`:

```css
/* Primary colors */
--wiki-deep-indigo: #1F2A64
--wiki-data-blue: #126FB1
--wiki-dark-teal: #0F6F66
--wiki-burgundy: #630C2B

/* Secondary colors */
--wiki-clear-sky: #00D2FF
--wiki-golden: #F5D26E
--wiki-lavender: #B08FD6

/* Status colors (RAG) */
--wiki-red: #C70000
--wiki-amber: #FFBF00
--wiki-green: #27693F

/* Neutral greyscale */
--wiki-n0 through --wiki-n1000 (white to black)
```

---

## Admonition Colors Automatically Applied

```markdown
!!! note         → Data Blue
!!! tip          → Clear Sky
!!! success      → Green
!!! warning      → Amber
!!! danger       → Red
!!! failure      → Red
!!! question     → Dark Teal
!!! example      → Data Blue
!!! abstract     → Data Blue
!!! quote        → Deep Indigo
```

---

## Buttons

```markdown
[Button Text](#){ .md-button }
[Primary Button](#){ .md-button .md-button--primary }
[Button with Icon :fontawesome-solid-icon:](#){ .md-button }
```

---

## Footnotes

```markdown
Text with a footnote[^1].

[^1]: Footnote content here.
```

---

## Horizontal Rules

```markdown
---
```

Use between major sections for scannability.

---

## Common Patterns

### See Also Section

```markdown
## See Also

- [Related Page 1](./page1.md)
- [Related Page 2](./page2.md)
```

### Further Reading

```markdown
??? quote "Further Reading"
    - [Resource 1](./resource1.md)
    - [Resource 2](./resource2.md)
```

### Checklist

```markdown
- [ ] Task 1
- [x] Task 2 (completed)
- [ ] Task 3
```

---

## Keyboard Shortcuts

```markdown
++ctrl+alt+del++
++cmd+k++
```

---

## Subscript & Superscript

```markdown
H~2~O
x^2^ + y^2^ = z^2^
```

---

## Design Standards Summary

### Structure

- ✓ YAML front matter with title & description
- ✓ Single `#` heading per page
- ✓ Proper heading hierarchy (`##`, `###`)
- ✓ Horizontal rules between sections
- ✓ Short, focused sections

### Content

- ✓ Clear, concise writing
- ✓ Use admonitions for side info
- ✓ Inline code for identifiers
- ✓ Relative links for internal pages
- ✓ Alt text for all images

### Formatting

- ✓ Emphasis used sparingly
- ✓ Lists for non-narrative content
- ✓ Code blocks with language hints
- ✓ Admonition types match their meaning
- ✓ Whitespace for readability

### Colors & Design

- ✓ Use CSS variables, never hardcoded hex
- ✓ Admonition types convey semantics
- ✓ Test in light & dark modes
- ✓ Verify WCAG AA contrast

---

## Page Templates

Use these templates for common page types:

| Type | Template |
|------|----------|
| General page | [standard_page.md](./page_templates/standard_page.md) |
| Component reference | [component_reference.md](./page_templates/component_reference.md) |
| How-to guide | [procedural_guide.md](./page_templates/procedural_guide.md) |
| Overview/landing | [overview_page.md](./page_templates/overview_page.md) |
| FAQ | [faq.md](./page_templates/faq.md) |
| Glossary | [glossary_entry.md](./page_templates/glossary_entry.md) |

---

## Pre-Publishing Checklist

- [ ] YAML front matter present
- [ ] Heading hierarchy correct
- [ ] Links use relative paths
- [ ] Code blocks have language hints
- [ ] Admonitions follow standards
- [ ] Alt text on all images
- [ ] No hardcoded colors
- [ ] Emphasis used sparingly
- [ ] Whitespace and breaks present
- [ ] Grammar and spelling correct

---

## Quick Help

| Need | Reference |
|------|-----------|
| Detailed rules & standards | [Wiki Formatting Guide](../WIKI_FORMATTING_GUIDE.md) |
| Colors & brand system | [Brand Guidelines](./BRAND_GUIDELINES.md) |
| Component examples | [Component Library](./components/) |
| Page structure | [Page Templates](./page_templates/) |
| Accessibility info | [WCAG Contrast Checker](https://webaim.org/resources/contrastchecker/) |
| Markdown help | [Markdown Guide](https://www.markdownguide.org/) |
| MkDocs Material | [Material for MkDocs Docs](https://squidfunk.github.io/mkdocs-material/) |

---

## Using This Guide with Copilot

When creating a new page with Copilot, reference this guide:

> "Create a new wiki page following the Wiki Formatting Guide. Use [template name] and include [admonition types]."

Copilot can access this quick reference to ensure consistent formatting and design.

---

!!! tip "Pro Tips"
    - Bookmark this page for quick reference
    - Use `++ctrl+f++` to search for syntax examples
    - Always preview in both light and dark modes
    - Test links and code blocks before publishing
