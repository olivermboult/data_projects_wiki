
# Page references

!!! draft
    This page is still being created, some of the details maybe incorrect or formatted incorrectly.

This section of the documentation explains how to set up a page, and showcases all available assets that can be used directly from within Markdown files.

=== "title"

    Each page has a designated title, which is used in the navigation sidebar,
    for social cards and in other places.

    While MkDocs attempts to automatically determine the title, the title can
    also be explicitly set with the front matter `title` property:

    ```md
    ---
    title: Lorem ipsum dolor sit amet
    ---
    ```

=== "subtitle"

    Each page can define a subtitle, which is rendered below the title as part
    of the navigation sidebar.

    ```md
    ---
    subtitle: Nullam urna elit, malesuada eget finibus ut, ac tortor
    ---
    ```

=== "description"

    A Markdown file can include a description that is added to meta tags and
    used for social cards.

    ```md
    ---
    description: Nullam urna elit, malesuada eget finibus ut, ac tortor.
    ---
    ```

=== "icon"

    An icon can be assigned to each page and rendered in the navigation sidebar.

    ```md
    ---
    icon: material/emoticon-happy
    ---
    ```

=== "status"

    A status can be assigned to each page and displayed in the navigation
    sidebar.

    First, define statuses in `mkdocs.yml`:

    ```yml
    extra:
      status:
        deprecated: Will be removed soon
        new: Recently added
        happy: Happy
    ```

    Then apply it in a page:

    ```md
    ---
    status: new
    ---
    ```

=== "template"

    If you're using a theme override, you can assign a custom template:

    ```md
    ---
    template: custom.html
    ---
    ```

??? quote "References"
- [Material for MkDocs — References](https://squidfunk.github.io/mkdocs-material/reference/)