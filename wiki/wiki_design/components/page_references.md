
---
title: Page References — MkDocs Material Component Guide
description: This page describes front matter and page-level metadata used by Material for MkDocs, including title, subtitle, description, icon, status, and template.
---

# Page References

Material for MkDocs uses page-level metadata to control how pages appear in navigation, search results, social cards, and custom theme layouts.

---

## Design Standards

!!! success "Dos"
    - **Do** set a clear `title` for every page so navigation, search, and sharing are consistent.
    - **Do** use `subtitle` to add context to a page when it helps readers understand the content at a glance.
    - **Do** use `status` only when the page state is meaningful, such as `new`, `deprecated`, or `updated`.

!!! failure "Don'ts"
    - **Don’t** rely on the generated filename or heading alone for page metadata; explicit front matter is more reliable.
    - **Don’t** overuse icons or statuses; use them sparingly so the sidebar remains readable.
    - **Don’t** put important metadata only in the file name or directory structure; keep page metadata in front matter when you need consistent presentation.

---

## Page front matter

Material for MkDocs supports standard page metadata in YAML front matter. Add metadata at the top of the Markdown file, inside `---` markers.

### `title`

The page title is used by the navigation sidebar, the page header, and search results.

- MkDocs may infer a title from the first heading or filename if `title` is omitted.
- Explicit `title` values are more stable across theme changes and navigation structures.

```md
---
title: Page References
---
```

### `subtitle`

A subtitle appears below the title in the sidebar, helping readers understand the page purpose.

```md
---
subtitle: Front matter and metadata for Material pages
---
```

### `description`

The description is used for meta tags and social cards. It can also improve search previews.

```md
---
description: Add page metadata for navigation, search, and custom theme rendering.
---
```

### `icon`

Use `icon` to assign a Material icon to the page in the navigation sidebar.

```md
---
icon: material/emoticon-happy
---
```

- Icons should use the `material/` prefix and a valid Material icon name.
- Choose icons that visually match the page purpose without being distracting.

### `status`

Statuses are defined in `mkdocs.yml` and then referenced in page front matter.

```yaml
extra:
  status:
    new: Recently added
    deprecated: Will be removed soon
    beta: Experimental content
```

```md
---
status: new
---
```

- Status badges can be rendered in the navigation sidebar and page lists.
- Use meaningful status names that align with the documentation workflow.

### `template`

If you are using a custom theme override, `template` lets a page use a different Jinja template.

```md
---
template: custom.html
---
```

- `template` is only valid when the theme provides a matching template file.

---

## Best practices for page metadata

- Keep metadata concise and reader-focused.
- Use `title` and `description` to support search and social sharing.
- Avoid repeating the same copy in both the page title and subtitle.

### Example page metadata

```md
---
title: Page References
subtitle: Configure page metadata for Material for MkDocs
description: Reference the front matter values supported by Material for MkDocs and how they affect navigation, search, and theming.
icon: material/book-open
status: new
---
```

---

??? quote "References"
    - [Material for MkDocs — References](https://squidfunk.github.io/mkdocs-material/reference/)
    - [Material for MkDocs — Configuration reference](https://squidfunk.github.io/mkdocs-material/reference/configuration/)