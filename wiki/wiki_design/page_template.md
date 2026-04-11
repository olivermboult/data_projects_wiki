---
# Example front matter — copy to top of every new page and edit values
title: Page Title
subtitle: One-line supporting subtitle (optional)
description: Short description for search and social cards (optional)
icon: material/emoticon-happy
status: draft
---

# Page template — Use this structure for new wiki pages

This template provides a consistent structure and examples for interactive and accessible pages across the wiki. Copy this file when creating a new page and replace the sample content.

---

## 1. Purpose (one short paragraph)
Briefly explain the page's purpose and who should read it.

---

## 2. Quick links / TL;DR
- Link to the most important actions or related pages
- Link to API, templates or notebooks if relevant

---

## 3. Design summary
- Short bullets describing key constraints, status and owners.

---

## 4. Guidance / Content (primary body)
Write the main content in logical subsections. Use these patterns to keep pages interactive and consistent:

- Admonitions (call-outs):

!!! note "When to use"
    Use `!!! note`, `!!! tip`, `!!! warning`, or `!!! failure` for important short callouts.

- Tabs for alternative views (code, diagram, explanation):

=== "Explanation"

    Narrative or short explanation here.

=== "Code"

    ```html
    <!-- Example code block -->
    ```

- Code blocks: use triple backticks and a language tag for syntax highlighting.

```python
# Example
print("hello")
```

- Images: use relative paths under `wiki/_assets` or the component `images.md` guidance.

---

## 5. Examples / Copy-paste snippets
Provide minimal working examples (HTML, Markdown or code) users can copy.

```html
<div class="hero hero--indigo hero--md" markdown="1">
  <div class="hero__inner">
    <h1 class="hero__title">Example</h1>
    <p class="hero__subtitle">Short subtitle text</p>
  </div>
</div>
```

---

## 6. Accessibility & testing notes
- Provide keyboard instructions for interactive widgets.
- Provide ARIA guidance where needed.
- Link to the audit checklist (e.g., color contrast, header structure).

---

## 7. Owners and governance
- **Owner**: name / team
- **Reviewer**: name / team
- **Last reviewed**: YYYY-MM-DD

---

## 8. References
- Link to components: [Components index](components/index.md)
- Link to tokens and styles: [Style tokens and CSS](../_assets/styles/style.css)
