---
title: Wiki Formatting Guide
description: Comprehensive rules, standards, and best practices for creating consistent, professional wiki pages using the Data Projects Wiki design system.
---

# Wiki Formatting Guide

This guide consolidates all formatting rules, design standards, and best practices for creating new wiki pages. It's designed for both human reference and as a basis for Copilot prompts.

---

## Quick Links

- **[Page Templates](wiki_design/page_templates/)** — Ready-to-use templates for different page types
- **[Quick Reference Card](#quick-reference)** — Markdown syntax cheat sheet
- **[Brand & Design Tokens](wiki_design/brand_guidelines.md)** — Color palette and design system
- **[Component Library](wiki_design/components/)** — Detailed component guides

---

## Core Formatting Rules

### Document Structure

!!! success "Structure Standards"
    - **Always start with YAML front matter:** Include `title`, `description` (60–160 characters)
    - **Use heading hierarchy:** Start with `# Title`, use `##`, `###` for sections (never skip levels)
    - **Keep sections focused:** One idea per section; break up large sections with subsections
    - **Use horizontal rules:** Add `---` between major sections to improve scannability

!!! failure "What Not To Do"
    - **Don't** start with content before YAML front matter
    - **Don't** use multiple `#` headings on one page
    - **Don't** skip heading levels (e.g., `# Title` → `### Subsection`)
    - **Don't** create walls of text — break up with headings and whitespace

---

### Content Formatting

#### Emphasis

| Use Case | Syntax | Example |
|----------|--------|---------|
| Subtle emphasis | `*text*` | This is *optional* |
| Strong emphasis | `**text**` | This is **required** |
| Code/identifier | `` `text` `` | Use `git pull` to fetch |
| Don't overuse emphasis — it weakens impact. Reserve for key concepts. | — | — |

#### Lists

**Unordered lists** use `-` with consistent indentation:

```md
- First item
- Second item
  - Nested item (indent by 2 spaces)
  - Another nested
- Third item
```

**Ordered lists** use `1.` and increment naturally:

```md
1. First step
2. Second step
   1. Substep (indent by 3 spaces)
   2. Another substep
3. Third step
```

!!! tip "List Best Practices"
    - Keep list items concise (1–2 lines each)
    - Use unordered lists for non-sequential items
    - Use ordered lists for procedures or ranked content
    - Nest no more than 3 levels deep

#### Links

**Inline links:**
```md
[link text](https://example.com)
```

**Reference-style links** (for repeated URLs):
```md
[link text][ref]

[ref]: https://example.com
```

!!! success "Link Best Practices"
    - Use descriptive link text (not "click here")
    - Prefer relative URLs for internal pages: `[Page Name](../path/page.md)`
    - Keep URLs concise and meaningful

---

### Component Usage

#### Admonitions (Callouts)

Use admonitions for side content that doesn't break the main narrative. All types use the same syntax:

```md
!!! type "Optional Title"
    Content goes here, indented by 4 spaces.
    Multiple paragraphs are supported.
```

**When to use each type:**

| Type | Purpose | Example |
|------|---------|---------|
| `note` | General information | "This feature requires version 2.0+" |
| `abstract` | TL;DR, summary, overview | Overview of the section |
| `info` | Neutral information | "See the reference for details" |
| `tip` | Best practice, helpful hint | "Use quotes to avoid escaping" |
| `success` | Positive outcome, confirmation | "Installation complete" |
| `question` | Prompt, consideration, open question | "What would you do instead?" |
| `warning` | Caution, something might go wrong | "This will overwrite existing files" |
| `failure` | Failure, destructive action | "Don'ts and anti-patterns" |
| `danger` | Critical, high risk | "This will delete all data" |
| `bug` | Known issue, limitation | "Not supported in Python 2.7" |
| `example` | Example, demonstration | "Example query:" |
| `quote` | Blockquote, reference | Attributed quote |

!!! success "Admonition Design Standards"
    - **Do** use for side content without breaking the narrative
    - **Do** keep non-collapsible blocks short (1–5 lines)
    - **Do** standardize type usage so readers learn semantics
    - **Do** use `!!!` for important info, `???` for collapsible/optional detail

!!! failure "What Not To Do"
    - **Don't** hide critical warnings in collapsible blocks
    - **Don't** stack many admonitions back-to-back
    - **Don't** overuse custom variants — add only if they add clear meaning

**Collapsible admonitions** use `???` instead of `!!!`:

```md
??? tip "Click to expand"
    This content is hidden until the user clicks.
```

#### Code Blocks

Always include a language hint for syntax highlighting:

```md
    ```language
    code here
    ```
```

**With title (filename context):**

```md
    ```python title="example.py"
    def hello():
        print("Hello, World!")
    ```
```

**With line numbers:**

```md
    ```python linenums="1"
    def hello():
        print("Hello, World!")
    ```
```

**With highlighted lines:**

```md
    ```python hl_lines="2"
    def hello():
        print("Hello, World!")  # <-- This line is highlighted
    ```
```

!!! success "Code Block Best Practices"
    - **Always** include a language hint (e.g., `python`, `bash`, `yaml`)
    - **Do** add `title="filename"` for context
    - **Do** use `hl_lines` for emphasis on key lines
    - **Do** keep blocks under 30–40 lines (link to source for longer code)

!!! failure "What Not To Do"
    - **Don't** use code blocks for output unless it's clearly a code/config example
    - **Don't** include huge file dumps — link to sources instead
    - **Don't** rely on syntax highlighting alone; use comments for clarity

#### Tables

Tables are supported in standard Markdown:

```md
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |
```

!!! tip "Table Best Practices"
    - Keep columns narrow; use at most 4–5 columns
    - Use for structured, tabular data only
    - For lists, prefer bulleted or numbered lists instead

#### Images

```md
![Alt text describing the image](path/to/image.png)
```

!!! tip "Image Best Practices"
    - Always include descriptive alt text
    - Use relative paths: `../images/filename.png`
    - Keep image file sizes reasonable (optimize before adding)
    - Use PNG for diagrams/screenshots, JPG for photos

#### Footnotes

Use square brackets with a caret for footnote markers:

```md
This is a statement with a footnote[^1].

[^1]: This is the footnote content.
```

---

## Typography Standards

### Headings

- **Page title:** Use `#` (top-level heading)
- **Sections:** Use `##` 
- **Subsections:** Use `###`
- **Details:** Use `####` (rarely needed)

!!! failure "What Not To Do"
    - **Don't** use more than one `#` per page
    - **Don't** skip heading levels
    - **Don't** use headings for styling (e.g., to make text larger) — use emphasis instead

### Inline Code vs. Text

- Use inline code (`` `backticks` ``) for:
  - Function/method names: `` `get_user()` ``
  - Variable names: `` `count` ``
  - Command-line tools: `` `git` ``
  - File paths: `` `src/utils/helpers.py` ``
  - Config keys: `` `apiKey` ``

- Don't use backticks for:
  - Concepts or general terminology
  - UI labels (use **bold** instead): **File** menu, **Save** button
  - Names of products/services (unless referring to code)

---

## Color & Visual Standards

### Brand Colors

The wiki uses a cohesive color system defined in [style.css](_wiki_branding/style.css). All colors are expressed as CSS variables:

#### Primary Palette

- **Deep Indigo** (`--wiki-deep-indigo: #1F2A64`) — Primary brand, headers, primary buttons
- **Data Blue** (`--wiki-data-blue: #126FB1`) — Accent, action states, emphasis
- **Dark Teal** (`--wiki-dark-teal: #0F6F66`) — Secondary accent, variety
- **Burgundy** (`--wiki-burgundy: #630C2B`) — Tertiary accent, depth

#### Secondary Palette

- **Clear Sky** (`--wiki-clear-sky: #00D2FF`) — Info/tip highlights
- **Golden** (`--wiki-golden: #F5D26E`) — Active states, draft flags
- **Lavender** (`--wiki-lavender: #B08FD6`) — Alternative highlight (future use)

#### Status Colors (RAG)

- **Red** (`--wiki-red: #C70000`) — Errors, dangers, failures
- **Amber** (`--wiki-amber: #FFBF00`) — Warnings, cautions, in-progress
- **Green** (`--wiki-green: #27693F`) — Success, affirmations, positive outcomes

#### Neutral Greyscale

- **White to Black:** `--wiki-n0` through `--wiki-n1000`
- Used for text, backgrounds, borders, disabled states

!!! tip "Color Usage Rules"
    - Don't hardcode hex values — always reference CSS variables
    - Use colors consistently (e.g., always `danger` admonitions for destructive actions)
    - Test contrast for accessibility when choosing colors
    - Prefer semantic admonition types over raw colors

---

## Page Template Usage

For common page types, use the templates in [wiki_design/page_templates/](wiki_design/page_templates/):

- **Standard Page** — General content pages
- **Component Reference** — Technical documentation of a feature/component
- **Procedural Guide** — Step-by-step instructions
- **Overview/Landing** — Introduction to a topic area
- **FAQ** — Frequently asked questions
- **Glossary Entry** — Definitions and terminology

Each template includes:
- Suggested structure
- Placeholder sections
- Pre-filled admonitions with design standards
- Examples of proper formatting

---

## Quick Reference

### YAML Front Matter Template

```yaml
---
title: Page Title (60–80 characters)
description: Brief description for metadata and search (60–160 characters).
---
```

### Common Markdown Snippets

| Element | Syntax |
|---------|--------|
| Heading 1 | `# Title` |
| Heading 2 | `## Section` |
| Bold | `**text**` |
| Italic | `*text*` |
| Inline code | `` `code` `` |
| Link | `[text](url)` |
| Unordered list | `- item` |
| Ordered list | `1. item` |
| Admonition | `!!! type "Title"` / content |
| Collapsible block | `??? type "Title"` / content |
| Code block | ` ```language` / code / ` ``` ` |
| Table | `\| col1 \| col2 \|` |
| Horizontal rule | `---` |
| Image | `![alt](path)` |
| Footnote | `text[^1]` / `[^1]: note` |

---

## Checklist for New Pages

Before publishing a new page, verify:

- [ ] **YAML front matter** is present with `title` and `description`
- [ ] **Heading hierarchy** is correct (one `#`, then `##`, `###` as needed)
- [ ] **Links** use relative paths (e.g., `../path/page.md`)
- [ ] **Code blocks** have language hints and titles (where applicable)
- [ ] **Admonitions** follow design standards (correct type, short non-critical, etc.)
- [ ] **Alt text** is present on all images
- [ ] **Emphasis** is used sparingly and meaningfully
- [ ] **Whitespace** is used to break up content (not walls of text)
- [ ] **Grammar and spelling** are correct

---

## Getting Help

- **Design Questions:** See [wiki_design/components/](wiki_design/components/)
- **Brand/Color Questions:** See [Brand Guidelines](wiki_design/brand_guidelines.md)
- **Style Examples:** Check existing pages or templates
- **Accessibility:** Verify heading hierarchy, contrast, and semantic HTML

---

!!! abstract "How to Use This Guide with Copilot"
    Save a bookmark or remember: "Follow the Wiki Formatting Guide at `WIKI_FORMATTING_GUIDE.md`" 
    
    When asking Copilot to create a new page, reference this guide:
    > "Create a new wiki page following the Wiki Formatting Guide. Use the [Component Reference template](wiki_design/page_templates/component_reference.md) and include [info admonitions] for tips."
    
    Copilot can then refer to this document to ensure consistency.
