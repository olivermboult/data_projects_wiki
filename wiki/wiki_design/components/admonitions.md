---
title: Admonitions (Callouts) — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending admonitions in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
--- 

# Admonitions (Callouts) 

**Admonitions** (also called **callouts**) are styled blocks used to highlight side content without significantly interrupting the document flow. Material for MkDocs provides multiple built‑in admonition types, supports nesting arbitrary content inside, and supports collapsible (expandable) admonitions when the Details extension is enabled.

---

## Admonition Design Standards

!!! success "Dos"
    - **Do** use admonitions for side content that should stand out without breaking the main narrative flow.
    - **Do** keep non-collapsible admonitions short (roughly 1–5 lines) and use collapsible blocks for longer explanations.
    - **Do** standardise type usage (e.g., `warning` for caution, `danger` for destructive actions) so readers learn the semantics quickly. 
    - **Do** use SuperFences when you want nested code blocks inside admonitions.

!!! failure "Don'ts"
    - **Don’t** hide critical warnings inside collapsible blocks — collapsible is best for optional detail.
    - **Don’t** stack many admonitions back-to-back; consider headings or refactoring into narrative content. 
    - **Don’t** overuse custom variants — add new types only if they add clear meaning beyond the built-ins. 
    - **Don’t** use SVG icons with inline `fill` attributes when using mask-image based icons — they can fail to render as expected.

---

## Using Admonitions

### Basic Built-in Admonitions

Admonitions start with `!!!` followed by a type qualifier (e.g. `note`, `warning`). The content follows on the next line, indented by **four spaces**.

Material for MkDocs supports these admonition types (the fallback type for unknown qualifiers is `note`).

- `note`
- `abstract`
- `info`
- `tip`
- `success`
- `question`
- `warning`
- `failure`
- `danger`
- `bug`
- `example`
- `quote`

These examples show the admonitions in action!

!!! note "note"
    General supporting information.

    ```md
    !!! note "note"
        General supporting information.
    ```

!!! abstract "abstract"
    TL;DR / Overview / Summary.

    ```md
    !!! abstract "abstract"
        TL;DR / Overview / Summary.
    ```

!!! info "info"
    Neutral informational content.

    ```md
    !!! info "info"
        Neutral informational content.
    ```

!!! tip "tip"
    Best-practice hint.

    ```md
    !!! tip "tip"
        Best-practice hint.
    ```

!!! success "success"
    Confirmed good outcome.

    ```md
    !!! success "success"
        Confirmed good outcome.
    ```

!!! question "question"
    Prompt / Consideration / Open question.

    ```md
    !!! question "question"
        Prompt / Consideration / Open question.
    ```

!!! warning "warning"
    Caution — something might go wrong.

    ```md
    !!! warning "warning"
        Caution — something might go wrong.
    ```

!!! failure "failure"
    Known failure.

    ```md
    !!! failure "failure"
        Known failure.
    ```

!!! danger "danger"
    High risk / destructive operations.

    ```md
    !!! danger "danger"
        High risk / destructive operations.
    ```

!!! bug "bug"
    Known defect or workaround.

    ```md
    !!! bug "bug"
        Known defect or workaround.
    ```

!!! example "example"
    Worked example or recipe.

    ```md
    !!! example "example"
        Worked example or recipe.
    ```

!!! quote "quote"
    Quoted guidance or excerpt.

    ```md
    !!! quote "quote"
        Quoted guidance or excerpt.
    ```

### Customising Built-in Admonitions

**Customised Title**

By default the title equals the type qualifier in Title Case, but it can overriden by adding a quoted string after the type qualifier. The title supports Markdown (links, formatting, etc.). 

!!! warning "Read this *before* deploying"
    Titles can include *formatting*, `inline code`, and links.

    ```md
    !!! warning "Read this *before* deploying"
        Titles can include *formatting*, `inline code`, and links.
    ```

**Removing the Title Row (non-collapsible only)**

The icon/title row can be omitted entirely by providing an empty quoted title (`""`). This does **not** work for collapsible blocks.

!!! info ""
    This admonition has no title row.

    ```md
    !!! info ""
        This admonition has no title row.
    ```

**Collapsible Admonitions (Details)**

When the Details extension is enabled (`pymdownx.details`), starting an admonition with `???` makes it collapsible (and expandable). Adding a `+` (`???+`) renders it expanded by default.

Collapsed by default

??? note "Click to expand"
    This starts collapsed.

    ```md
    ??? note "Click to expand"
        This starts collapsed.
    ```

Expanded by default

???+ tip "Expanded by default"
    This starts expanded.

    ```md
    ???+ tip "Expanded by default"
        This starts expanded.
    ```

**Nesting Admonitions (and why SuperFences matters)**

Admonitions can be nested by indenting an inner admonition inside an outer admonition. Material strongly recommends SuperFences (`pymdownx.superfences`) so that fenced blocks (like code fences) can be nested reliably inside admonitions.

!!! note "Outer note"
    Outer content.

    !!! info "Inner info"
        Inner content with nested code:

        ```sql
        SELECT COUNT(*) AS row_count
        FROM my_table;
        ```

```md
!!! note "Outer note"
    Outer content.

    !!! info "Inner info"
        Inner content with nested code:

        ```sql
        SELECT COUNT(*) AS row_count
        FROM my_table;
        ```
```

**Inline Admonitions (sidebars)**

Admonitions can be rendered as **inline blocks**, aligned either to the right using `inline end` or to the left using `inline`. Inline admonitions must be declared **before** the content block they should sit beside; if there isn’t enough room (e.g., on mobile), they expand to full width.

Inline end (right)

!!! info inline end "Inline end (right)"
    A short side note aligned right.

This paragraph should flow next to the inline admonition (if there’s space).

```md
!!! info inline end "Inline end (right)"
    A short side note aligned right.

This paragraph should flow next to the inline admonition (if there’s space).
```

Inline (left)

!!! tip inline "Inline (left)"
    A short hint aligned left.

This paragraph should wrap beside the admonition (if there’s space).

```md
!!! tip inline "Inline (left)"
    A short hint aligned left.

This paragraph should wrap beside the admonition (if there’s space).
```

---

## Creating Custom Admonitions

Within Material, custom admonitions can be created as variants to be used throughout the wiki. Note this should be done only if the built-in admonitions arent suitable. The custom admonition is created in the `style.css` file with the following code.

```css
.md-typeset .admonition.VARIANT_NAME,
.md-typeset details.VARIANT_NAME {
  border-color: #COLOUR !important;
}

.md-typeset .VARIANT_NAME > .admonition-title,
.md-typeset .VARIANT_NAME > summary {
  background-color: #COLOUR !important;
  color: #COLOUR !important;
}

.md-typeset .VARIANT_NAME > .admonition-title::before,
.md-typeset .VARIANT_NAME > summary::before {
  background-color: #COLOUR;
  -webkit-mask-image: #ICON;
  mask-image: #ICON;
}

.md-typeset .quote > summary::after {                                                      
  color: #COLOUR !important;                                                   
}

.md-typeset details[class] {                                                            
  box-shadow: none !important;                                                           
}

```

!!! draft "draft"
    A draft page or section

    ```md
    !!! draft "draft"
        A draft page or section
    ```

---

## Setting Up Admonitions

Within the `mkdocs.yml` file, enable:

- `admonition` (core syntax)
- `pymdownx.details` (collapsible admonitions via `???` / `???+`)
- `pymdownx.superfences` (strongly recommended to support nesting fenced blocks like code inside admonitions)

Material’s reference configuration shows these extensions together for full functionality. 

```yaml
# mkdocs.yml
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
```

**Admonition Icons**

Each supported admonition type has a distinct icon. Material allows overriding the icon per type using `theme.icon.admonition` in the `mkdocs.yml` file and supports icon sets such as **Octicons** and **FontAwesome**.

```yaml
# mkdocs.yml
theme:                                          # Starts theme configuration block (Material options live under here)
    name: material                              # Selects the Material for MkDocs theme (enables Material features, palette, etc.
    icon:                                       # Theme icon overrides (lets you change icons used by the theme) 
        admonition:                             # Per-admonition-type icon mapping (built-in admonition types)
          note: octicons/tag-16                 # Icon used for !!! note admonitions 
          abstract: octicons/checklist-16       # Icon used for !!! abstract admonitions 
          info: octicons/info-16                # Icon used for !!! info admonitions
          tip: octicons/light-bulb-16           # Icon used for !!! tip admonitions 
          success: octicons/check-16            # Icon used for !!! success admonitions 
          question: octicons/question-16        # Icon used for !!! question admonitions 
          warning: octicons/alert-16            # Icon used for !!! warning admonitions 
          failure: octicons/x-16                # Icon used for !!! failure admonitions 
          danger: octicons/no-entry-16          # Icon used for !!! danger admonitions 
          bug: octicons/bug-16                  # Icon used for !!! bug admonitions 
          example: octicons/beaker-16           # Icon used for !!! example admonitions
          quote: octicons/quote-16              # Icon used for !!! quote admonitions 
```

---

??? quote "References"
    - [Material for MkDocs — Admonitions reference](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)
    - [Material for MkDocs — Customization / adding assets](https://squidfunk.github.io/mkdocs-material/customization/)
    - [MkDocs Material discussion on custom admonition icons and mask/fill considerations](https://github.com/squidfunk/mkdocs-material/discussions/2696)
