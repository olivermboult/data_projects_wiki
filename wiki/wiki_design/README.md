---
title: Wiki Formatting Rules & Templates
description: Complete reference system for creating consistent, professional wiki pages. Includes formatting rules, brand guidelines, page templates, and quick references.
---

# Wiki Formatting Rules & Templates

Welcome! This section contains all the rules, templates, and references you need to create professional, consistent wiki pages. Use these resources as a guide and as prompts for Copilot.

---

## Quick Start

**Need to create a new wiki page?** Follow these three steps:

1. **Choose your template** based on page type (see [Page Type Guide](#page-types) below)
2. **Follow the formatting rules** in [WIKI_FORMATTING_GUIDE.md](../WIKI_FORMATTING_GUIDE.md)
3. **Check the quick reference** in [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) while writing

---

## Documentation Overview

### 📋 [Wiki Formatting Guide](../WIKI_FORMATTING_GUIDE.md)
**Comprehensive rules and standards for all wiki pages**

- Core formatting rules (structure, content, components)
- Component usage guide (admonitions, code blocks, tables, images)
- Typography and heading standards
- Color and visual standards
- Checklist for new pages

👉 **Use this when:** You need detailed guidance on any formatting question

---

### 🎨 [Brand & Design System Guidelines](./BRAND_GUIDELINES.md)
**Complete color palette, design tokens, and visual identity**

- Brand color palette (primary, secondary, status colors)
- Design token documentation
- CSS variable reference
- Accessibility & contrast standards
- Customization guidelines

👉 **Use this when:** You need to understand colors, brand identity, or design decisions

---

### 📄 Page Templates
**Ready-to-use templates for different page types**

| Template | Best For | Link |
|----------|----------|------|
| **Standard Page** | General content pages | [standard_page.md](./page_templates/standard_page.md) |
| **Component Reference** | Technical documentation | [component_reference.md](./page_templates/component_reference.md) |
| **Procedural Guide** | Step-by-step instructions | [procedural_guide.md](./page_templates/procedural_guide.md) |
| **Overview/Landing** | Topic introductions | [overview_page.md](./page_templates/overview_page.md) |
| **FAQ** | Frequently asked questions | [faq.md](./page_templates/faq.md) |
| **Glossary Entry** | Terminology and definitions | [glossary_entry.md](./page_templates/glossary_entry.md) |

!!! tip "How to Use Templates"
    1. Copy the template file
    2. Replace placeholder text with your content
    3. Follow the structure and design standards
    4. Preview in both light and dark modes

---

### ⚡ [Quick Reference Card](./QUICK_REFERENCE.md)
**One-page cheat sheet for Markdown syntax and formatting**

- YAML front matter template
- Markdown syntax reference table
- Admonition types at a glance
- Color token quick lookup
- Common patterns and snippets
- Pre-publishing checklist

👉 **Use this when:** You need quick syntax reminders while writing

---

### 📚 [Component Library](./components/)
**Detailed guides for each wiki component**

Browse these pages for in-depth examples:
- [Admonitions (Callouts)](./components/admonitions.md)
- [Formatting](./components/formatting.md)
- [Code Blocks](./components/code_blocks.md)
- [Buttons](./components/buttons.md)
- [Tables](./components/data_tables.md)
- [Images](./components/images.md)
- [And more...](./components/)

👉 **Use this when:** You need detailed examples of a specific component

---

## How to Use These Resources

### Scenario 1: Creating a New Page from Scratch

1. **Determine page type** — Is it a guide? Reference? FAQ?
2. **Use the appropriate template** — Copy one from [page_templates/](./page_templates/)
3. **Follow WIKI_FORMATTING_GUIDE** — Reference detailed rules as needed
4. **Use QUICK_REFERENCE** — Check syntax while writing
5. **Check Brand Guidelines** — Verify color and design standards

### Scenario 2: Working with Copilot

When asking Copilot to create or edit a wiki page:

```
Create a new wiki page following the Wiki Formatting Guide.
Use the [Template Name] template from wiki_design/page_templates/
Include [specific component types] following these standards:
- Use relative links (../path/page.md)
- Follow the admonition types in the Quick Reference
- Use CSS color variables from Brand Guidelines
```

### Scenario 3: Questions While Writing

| Question | Where to Look |
|----------|---------------|
| "What's the YAML syntax?" | [Quick Reference](./QUICK_REFERENCE.md) → YAML section |
| "How do I use admonitions?" | [Component Library](./components/admonitions.md) |
| "What colors should I use?" | [Brand Guidelines](./BRAND_GUIDELINES.md) |
| "How should I structure this page?" | Choose appropriate [template](./page_templates/) |
| "What's the rule about...?" | [Formatting Guide](../WIKI_FORMATTING_GUIDE.md) |

---

## Page Types & Templates

### 📝 Standard Page
General content pages with multiple sections. Good for explanations, guides, and documentation.

- Use when: Explaining a concept, covering a topic
- Template: [standard_page.md](./page_templates/standard_page.md)
- Example structure: Introduction → Sections → See Also

**Copilot prompt:**
```
Create a new standard wiki page about [topic] using the standard_page template.
```

---

### ⚙️ Component Reference
Detailed technical documentation of a feature or component. Includes design standards, usage examples, and customization.

- Use when: Documenting a feature, component, or technical reference
- Template: [component_reference.md](./page_templates/component_reference.md)
- Example structure: Intro → Design Standards → Usage → Examples → Setup

**Copilot prompt:**
```
Create a component reference for [component/feature] using the component_reference template.
Follow the design standards in the template.
```

---

### 📖 Procedural Guide
Step-by-step instructions with prerequisites, verification steps, and troubleshooting.

- Use when: Teaching how to complete a task
- Template: [procedural_guide.md](./page_templates/procedural_guide.md)
- Example structure: Prerequisites → Steps → Verification → Troubleshooting

**Copilot prompt:**
```
Create a how-to guide for [task] using the procedural_guide template.
Include troubleshooting section for common issues.
```

---

### 🌟 Overview/Landing Page
Introduction to a topic area with learning paths, quick links, and resource index.

- Use when: Introducing a topic or creating a landing page
- Template: [overview_page.md](./page_templates/overview_page.md)
- Example structure: Overview → Why it Matters → Quick Links → Learning Path

**Copilot prompt:**
```
Create an overview page for [topic area] using the overview_page template.
Include learning paths for beginner to advanced.
```

---

### ❓ FAQ
Frequently asked questions organized by category with quick answers and links to details.

- Use when: Collecting common questions and answers
- Template: [faq.md](./page_templates/faq.md)
- Example structure: Categories → Q&A pairs → Links to detailed docs

**Copilot prompt:**
```
Create an FAQ page for [topic] using the faq template.
Include troubleshooting and getting started sections.
```

---

### 📚 Glossary
Definitions and terminology for a topic area, organized alphabetically.

- Use when: Defining key terms and concepts
- Template: [glossary_entry.md](./page_templates/glossary_entry.md)
- Example structure: A-Z entries → Acronyms → Related resources

**Copilot prompt:**
```
Create a glossary page for [topic area] using the glossary_entry template.
Include acronyms and related concept definitions.
```

---

## Design Standards Summary

### Essential Rules

!!! success "Always Do"
    - Include YAML front matter with `title` and `description`
    - Use one `#` heading per page
    - Follow proper heading hierarchy (`##`, `###`)
    - Use relative links for internal pages (`../path/page.md`)
    - Include alt text for images
    - Use CSS variables for colors (never hardcode hex)
    - Test in both light and dark modes

!!! failure "Never Do"
    - Skip YAML front matter
    - Use multiple `#` headings
    - Skip heading levels
    - Use absolute URLs for internal links
    - Hardcode colors in markdown
    - Overuse emphasis or capitals
    - Hide critical warnings in collapsible blocks

---

## Color Palette at a Glance

### Primary Brand Colors
- **Deep Indigo** (`#1F2A64`) — Headers, navigation, primary buttons
- **Data Blue** (`#126FB1`) — Links, action states, info
- **Dark Teal** (`#0F6F66`) — Secondary accent, emphasis
- **Burgundy** (`#630C2B`) — Tertiary accent, alternative emphasis

### Status Colors (RAG)
- **Red** (`#C70000`) — Danger, errors, critical
- **Amber** (`#FFBF00`) — Warning, caution, in-progress
- **Green** (`#27693F`) — Success, affirmation, positive

📖 Full details in [Brand Guidelines](./BRAND_GUIDELINES.md)

---

## Admonition Quick Reference

```markdown
!!! note      → General info
!!! info      → Neutral info
!!! tip       → Best practice
!!! success   → Positive outcome
!!! question  → Prompt/question
!!! warning   → Caution
!!! danger    → Critical action
!!! failure   → What NOT to do
!!! bug       → Known issue
!!! example   → Example/demo
!!! abstract  → Summary/TL;DR
!!! quote     → Blockquote
```

Use `???` instead of `!!!` for collapsible blocks.

---

## Getting Help

### If You Need To...

| Task | Resource |
|------|----------|
| Start a new page | Choose a [template](./page_templates/) |
| Check Markdown syntax | See [Quick Reference](./QUICK_REFERENCE.md) |
| Understand a formatting rule | Check [Formatting Guide](../WIKI_FORMATTING_GUIDE.md) |
| Choose colors | Read [Brand Guidelines](./BRAND_GUIDELINES.md) |
| See detailed component examples | Browse [Component Library](./components/) |
| Create consistent pages | Reference all docs together |

---

## Checklist: Before Publishing

- [ ] YAML front matter present (title, description)
- [ ] Proper heading hierarchy (one `#`, then `##`, `###`)
- [ ] All internal links are relative (`../path/page.md`)
- [ ] All code blocks have language hints
- [ ] All images have alt text
- [ ] No hardcoded colors — using CSS variables
- [ ] Admonition types match their purpose
- [ ] Emphasis (bold/italic) used sparingly
- [ ] Content is clear and concise
- [ ] Grammar and spelling are correct
- [ ] Tested in light AND dark modes

---

## Tips for Success

### Writing with Consistency

1. **Pick a template** — Start with the right structure
2. **Follow the guide** — Ref [WIKI_FORMATTING_GUIDE](../WIKI_FORMATTING_GUIDE.md) for standards
3. **Use the checklist** — Verify before publishing
4. **Preview both modes** — Check light and dark rendering

### Working with Copilot

Include clear instructions:

```
Create a new [page type] wiki page about [topic].
Use the [Template Name] template from wiki_design/page_templates/
Follow the Wiki Formatting Guide standards:
- Include [specific components]
- Use relative links for internal pages
- Apply brand colors from Brand Guidelines
```

Copilot can reference these documents to maintain consistency.

---

## Document Map

```
wiki_design/
├── QUICK_REFERENCE.md               ← One-page syntax cheat sheet
├── BRAND_GUIDELINES.md              ← Colors, design system, tokens
├── page_templates/                  ← Ready-to-use templates
│   ├── standard_page.md
│   ├── component_reference.md
│   ├── procedural_guide.md
│   ├── overview_page.md
│   ├── faq.md
│   └── glossary_entry.md
├── components/                      ← Detailed component guides
│   ├── admonitions.md
│   ├── formatting.md
│   ├── code_blocks.md
│   ├── buttons.md
│   ├── data_tables.md
│   ├── images.md
│   └── [more components...]
└── _wiki_branding/
    └── style.css                    ← CSS variables & design tokens

../WIKI_FORMATTING_GUIDE.md          ← Comprehensive rules & standards
```

---

## Start Here

1. **First time creating a page?** → Start with a [template](./page_templates/)
2. **Need a quick syntax reminder?** → Check [Quick Reference](./QUICK_REFERENCE.md)
3. **Want detailed rules?** → Read [Formatting Guide](../WIKI_FORMATTING_GUIDE.md)
4. **Need color/design info?** → See [Brand Guidelines](./BRAND_GUIDELINES.md)
5. **Want component examples?** → Explore [Component Library](./components/)

---

!!! abstract "Summary"
    This documentation system provides **rules**, **templates**, and **references** to help you create professional wiki pages. Everything is designed to be used with Copilot for consistent, high-quality output.
    
    **Key Resources:**
    - 📋 [Formatting Guide](../WIKI_FORMATTING_GUIDE.md) — Comprehensive rules
    - 🎨 [Brand Guidelines](./BRAND_GUIDELINES.md) — Colors & design
    - 📄 [Page Templates](./page_templates/) — Ready-to-use structures
    - ⚡ [Quick Reference](./QUICK_REFERENCE.md) — Syntax cheat sheet
    
    Questions? Check the resource that matches your need in the table above.
