---
title: Buttons — MkDocs Material Component Guide
description: This page is a single, copy‑paste friendly reference for using, styling, and extending buttons in Material for MkDocs. It is designed to be kept in the component library as a regression test: if any example stops rendering correctly after theme/CSS changes, it’ll be notice immediately.
---

# Buttons

**Buttons** are interactive controls that trigger actions. Material for MkDocs styles plain HTML buttons and links when given the `md-button` class (and optional modifiers). Use buttons to present clear, single actions — not for navigation lists or long-form links.

---

## Button Design Standards

!!! success "Dos"
    - **Do** use buttons for single, clear actions (submit, open, copy).
    - **Do** prefer text that starts with a verb and is concise (e.g., "Save draft").
    - **Do** use a primary variant for the most important action on the page.
    - **Do** provide accessible labels and focus styles for keyboard users.

!!! failure "Don'ts"
    - **Don’t** use multiple primary buttons on the same screen.
    - **Don’t** overload buttons with complex content or long paragraphs.
    - **Don’t** rely on color alone — combine color with clear text and iconography.

---

## Using Buttons

Material styles elements with the `md-button` class. You can use either `<button>` or `<a>` elements depending on whether the control performs an in-page action or navigates.

### Basic Built-in Buttons

In order to render a link as a button, suffix it with curly braces and add the .md-button class selector to it. The button will receive the selected primary color and accent color if active. The link for the button should replace the `#`

[Subscribe to our newsletter](#){ .md-button }

```html
[Subscribe to our newsletter](#){ .md-button }
```

If you want to display a filled, primary button, add both the `.md-button` and the `.md-button--primary` CSS class selectors.

[Subscribe to our newsletter](#){ .md-button .md-button--primary }

```html
[Subscribe to our newsletter](#){ .md-button .md-button--primary }
```

Of course, icons can be added to all types of buttons by using the icon syntax together with any valid icon shortcode, which can be easily found with a few keystrokes through our icon search.

[Send :fontawesome-solid-paper-plane:](#){ .md-button }

```html
[Send :fontawesome-solid-paper-plane:](#){ .md-button }
```

---

## Creating Custom Buttons

Within Material, custom buttons can be created as variants to be used throughout the wiki. Note this should be done only if the built-in admonitions arent suitable. The custom admonition is created in the `style.css` file with the following code.

```css
.md-typeset .md-button.VARIANT_NAME,
.md-typeset a.md-button.VARIANT_NAME {
  background-color: #COLOUR !important;
  border-color: #COLOUR !important;
  color: #COLOUR !important;
}

.md-typeset .md-button.VARIANT_NAME:focus {
  box-shadow: #COLOUR !important;
}
```

---

## Setting Up Buttons

Buttons are styled by the Material theme itself; you normally don't need extra Markdown extensions. Ensure your `mkdocs.yml` includes the Material theme and any custom CSS:

```yaml
# mkdocs.yml
theme:
  name: material
  custom_dir: wiki/wiki_design 

extra_css:
  - styles/style.css
```

---

??? quote "References"
    - [Material for MkDocs — Buttons reference](https://squidfunk.github.io/mkdocs-material/reference/buttons/)
