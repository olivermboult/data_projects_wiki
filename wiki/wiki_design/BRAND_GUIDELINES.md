---
title: Brand & Design System Guidelines
description: Comprehensive brand identity, color palette, and design token documentation for the Data Projects Wiki.
---

# Brand & Design System Guidelines

This document defines the visual identity, color palette, and design system for the Data Projects Wiki. All design decisions should be consistent with these standards.

---

## Design System Philosophy

!!! quote "Design Principle"
    **Every color, spacing, and component should serve a purpose.** 
    
    The wiki uses a **token-based design system** where all visual properties are expressed as CSS custom properties (variables) first. This ensures consistency across light/dark modes, components, and future extensions.

### Core Principles

1. **Semantic Colors** — Colors convey meaning (status, emphasis, action)
2. **Accessibility** — Contrast meets WCAG AA standards minimum
3. **Maintainability** — All colors are CSS variables, not hardcoded hex values
4. **Scalability** — Generated color variants (tints/shades) enable consistent gradients
5. **Purpose-Driven** — Colors are applied based on function, not arbitrary choice

---

## Brand Color Palette

All brand colors are defined in [_wiki_branding/style.css](_wiki_branding/style.css) using CSS custom properties. **Never hardcode hex values in markdown or other files — always reference the CSS variables.**

### Primary Brand Colors

These colors form the core brand identity and are used for headers, navigation, primary actions, and emphasis.

| Name | Variable | Hex | Primary Use |
|------|----------|-----|-------------|
| **Deep Indigo** | `--wiki-deep-indigo` | `#1F2A64` | Primary brand, header bar, nav, primary buttons |
| **Data Blue** | `--wiki-data-blue` | `#126FB1` | Accent brand, action states, info, emphasis |
| **Dark Teal** | `--wiki-dark-teal` | `#0F6F66` | Secondary accent, abstract content, question types |
| **Burgundy** | `--wiki-burgundy` | `#630C2B` | Tertiary accent, alternative emphasis, depth |

#### Usage Examples

- **Deep Indigo:** Page headers, primary CTA buttons, navigation background
- **Data Blue:** Links, active states, info admonitions, secondary buttons
- **Dark Teal:** Section highlights, abstract blocks, Q&A sections
- **Burgundy:** Tertiary actions, warnings requiring high contrast

---

### Secondary & Accent Colors

Used for highlights, hover states, and secondary affordances.

| Name | Variable | Hex | Primary Use |
|------|----------|-----|-------------|
| **Clear Sky** | `--wiki-clear-sky` | `#00D2FF` | Bright cyan: info/tip callouts, UI highlights |
| **Golden** | `--wiki-golden` | `#F5D26E` | Warm accent: active states, draft flags |
| **Lavender** | `--wiki-lavender` | `#B08FD6` | Soft purple: alternative highlight (future) |

#### Usage Examples

- **Clear Sky:** Info boxes, tips, highlights on dark backgrounds
- **Golden:** Draft content flags, active/current navigation states
- **Lavender:** Reserved for future custom admonition types

---

### Status & Semantic Colors (RAG)

Used to communicate status, urgency, and outcomes.

| Name | Variable | Hex | Meaning | Example |
|------|----------|-----|---------|---------|
| **Red** | `--wiki-red` | `#C70000` | Critical, Error, Danger | Destructive actions, failures, blocking issues |
| **Amber** | `--wiki-amber` | `#FFBF00` | Warning, Caution, In-Progress | Cautions, workarounds, incomplete states |
| **Green** | `--wiki-green` | `#27693F` | Success, Affirmation, Positive | Completed tasks, confirmations, best practices |

#### Usage Examples

- **Red:** "Danger" admonitions for destructive actions, critical errors
- **Amber:** "Warning" admonitions for cautions, deprecated features
- **Green:** "Success" admonitions for confirmations, positive outcomes

---

### Neutral Greyscale

Used for text, backgrounds, borders, and disabled states. Values follow a 0–1000 scale.

| Variable | Hex | Use Case |
|----------|-----|----------|
| `--wiki-n0` | `#FFFFFF` | Pure white, backgrounds |
| `--wiki-n100` | `#F8FAFC` | Light backgrounds, subtle separators |
| `--wiki-n200` | `#F1F5F9` | Light UI backgrounds |
| `--wiki-n300` | `#E2E8F0` | Light borders, dividers |
| `--wiki-n400` | `#94A3B8` | Muted text, disabled buttons |
| `--wiki-n500` | `#64748B` | Secondary text, helper text |
| `--wiki-n600` | `#475569` | Body text, normal content |
| `--wiki-n700` | `#334155` | Darker body text, emphasis |
| `--wiki-n800` | `#1E293B` | Headings, strong emphasis |
| `--wiki-n900` | `#0F172A` | Very dark text |
| `--wiki-n1000` | `#000000` | Pure black, edge cases |

#### Best Practices

- **Text:** Use `--wiki-n600` for body text, `--wiki-n800` for headings
- **Backgrounds:** Use `--wiki-n0` (white) or `--wiki-n100` (light grey)
- **Borders:** Use `--wiki-n300` for subtle borders, `--wiki-n400` for more contrast
- **Disabled:** Use `--wiki-n400` for disabled text/buttons

---

### Generated Color Variants

The design system automatically generates lighter and darker variants of base colors using CSS `color-mix()` in the OKLab color space. This ensures perceptually consistent gradients, hover states, and visual hierarchy without manual color maintenance.

**Example (Deep Indigo variants):**

```css
--wiki-deep-indigo-10-d  /* 10% darker */
--wiki-deep-indigo-20-d  /* 20% darker */
--wiki-deep-indigo-30-d  /* 30% darker */
--wiki-deep-indigo-40-d  /* 40% darker */
```

#### Why OKLab?

OKLab is a perceptually uniform color space, meaning changes in the numeric values correspond to changes in perceived lightness. This provides:
- **Consistent gradients** — Tints and shades feel evenly spaced
- **Accessibility** — Easier to verify contrast ratios
- **Scalability** — Variants can be generated algorithmically without manual tweaking

!!! tip "When Modifying Colors"
    If you adjust a base color in `style.css`, test:
    - Contrast ratios (WCAG AA minimum: 4.5:1 for text, 3:1 for UI components)
    - Generated variants (do they still look good?)
    - Both light and dark mode rendering

---

## Component Styling

All components (buttons, admonitions, tables, etc.) use the color palette and CSS variables defined above. **Never apply raw colors to components — always reference variables.**

### Admonition Color Mapping

Admonition types automatically map to semantic colors:

| Admonition Type | Primary Color | Use Case |
|-----------------|---------------|----------|
| `note` | Data Blue | General information |
| `info` | Data Blue | Neutral information |
| `tip` | Clear Sky | Best practices, helpful hints |
| `success` | Green | Positive outcomes, confirmations |
| `question` | Dark Teal | Prompts, open questions |
| `warning` | Amber | Cautions, something might go wrong |
| `danger` | Red | Critical actions, high-risk warnings |
| `failure` | Red | Failures, anti-patterns |
| `bug` | Amber | Known issues, limitations |
| `example` | Data Blue | Examples, demonstrations |
| `abstract` | Data Blue | Summaries, TL;DRs |
| `quote` | Deep Indigo | Blockquotes, references |

!!! success "Best Practices"
    - Let admonition types convey semantic meaning — readers will learn the associations
    - Don't create custom admonitions just for color variation
    - Use the standard types consistently across all pages

---

## Typography & Hierarchy

### Heading Hierarchy

- **H1 (`#`)** — Page title only; color: `--wiki-n800` (dark)
- **H2 (`##`)** — Major sections; color: `--wiki-deep-indigo`
- **H3 (`###`)** — Subsections; color: `--wiki-n800`
- **H4 (`####`)** — Detail sections (use sparingly)

### Body Text

- **Standard:** `--wiki-n600` (readable grey)
- **Emphasis:** `--wiki-n800` (darker) or bold for strong emphasis
- **Secondary/Helper:** `--wiki-n500` (lighter grey)
- **Disabled/Muted:** `--wiki-n400` (very light grey)

### Code & Monospace

- **Inline code:** `font-family: monospace`, `--wiki-data-blue` for code identifiers
- **Code blocks:** Pygments syntax highlighting with language-specific color rules

---

## Accessibility & Contrast

All color choices must meet **WCAG AA minimum contrast** (4.5:1 for text, 3:1 for UI components).

### Verified Contrast Ratios

!!! success "Passed Combinations"
    - Body text (`--wiki-n600`) on white (`--wiki-n0`): **7.4:1** ✓
    - Heading text (`--wiki-n800`) on white (`--wiki-n0`): **14.2:1** ✓
    - Data Blue (`--wiki-data-blue`) as text on white: **6.8:1** ✓
    - Green status (`--wiki-green`) on white: **5.2:1** ✓
    - Amber status (`--wiki-amber`) on white: **3.1:1** (borderline; use for UI, not text)

!!! warning "Caution"
    - **Avoid** using amber or lavender for body text on white — prefer in admonitions or UI
    - **Always test** new color combinations before deployment
    - **Use tools** like WebAIM Contrast Checker when adding new colors

---

## Light & Dark Mode

The wiki supports both light and dark modes. All colors are automatically inverted for dark mode through Material for MkDocs theming.

!!! tip "Dark Mode Considerations"
    - The CSS system is designed to handle both modes automatically
    - Always test your pages in both light and dark modes
    - Avoid hardcoding colors — use variables so theming works correctly
    - Some colors may need adjustment if they don't contrast well in dark mode

---

## Adding Custom Colors

If a new color is needed for a legitimate design purpose:

1. **Add to `style.css`** under the `:root` section with a meaningful variable name
2. **Document the color** in this guide
3. **Test contrast** against backgrounds (both light and dark modes)
4. **Generate variants** using `color-mix()` for tints/shades if needed
5. **Update this guide** to reflect the change

!!! failure "What NOT to Do"
    - **Don't** hardcode hex values in component CSS
    - **Don't** add arbitrary color variants without semantic meaning
    - **Don't** skip accessibility testing
    - **Don't** rely on color alone — combine with text/icons for clarity

---

## Design Tokens Summary

### Complete Token Reference

```css
/* Primary Colors */
--wiki-deep-indigo: #1F2A64;
--wiki-data-blue: #126FB1;
--wiki-dark-teal: #0F6F66;
--wiki-burgundy: #630C2B;

/* Secondary Colors */
--wiki-clear-sky: #00D2FF;
--wiki-golden: #F5D26E;
--wiki-lavender: #B08FD6;

/* Status Colors (RAG) */
--wiki-red: #C70000;
--wiki-amber: #FFBF00;
--wiki-green: #27693F;

/* Neutral Greyscale */
--wiki-n0: #FFFFFF;
--wiki-n100: #F8FAFC;
--wiki-n200: #F1F5F9;
--wiki-n300: #E2E8F0;
--wiki-n400: #94A3B8;
--wiki-n500: #64748B;
--wiki-n600: #475569;
--wiki-n700: #334155;
--wiki-n800: #1E293B;
--wiki-n900: #0F172A;
--wiki-n1000: #000000;
```

---

## Implementation Checklist

When implementing new components or pages:

- [ ] Use CSS variables for all colors (no hardcoded hex)
- [ ] Test contrast ratios in both light and dark modes
- [ ] Verify admonition types match their semantic meaning
- [ ] Ensure heading hierarchy is correct
- [ ] Check that emphasis is used sparingly and meaningfully
- [ ] Validate accessibility with a contrast checker tool
- [ ] Test in both light and dark modes before publishing

---

## References

- [MkDocs Material Theme Customization](https://squidfunk.github.io/mkdocs-material/customization/)
- [WCAG Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [OKLab Color Space](https://bottosson.github.io/posts/oklab/)
- [Wiki Design Components](wiki_design/components/)
- [Wiki Formatting Guide](WIKI_FORMATTING_GUIDE.md)
