---
title: Copilot Prompt Templates
description: Ready-to-use prompts for asking Copilot to create wiki pages following the formatting rules and design guidelines.
---

# Copilot Prompt Templates

Use these prompt templates when asking Copilot to create new wiki pages. They reference the formatting rules, brand guidelines, and templates to ensure consistent, professional output.

---

## How to Use These Prompts

1. **Choose the prompt template** that matches your page type
2. **Replace [placeholder text]** with your specific content
3. **Customize** as needed for your use case
4. **Paste into Copilot chat**

Each template includes reference to the relevant documentation so Copilot can follow the rules.

---

## Generic Page Creation Prompt

**Use this for:** Any page type where there's a specific template

```
Create a new wiki page following the Data Projects Wiki formatting rules.

Page details:
- Title: [Your Page Title]
- Type: [standard/component/guide/overview/faq/glossary]
- Topic: [What is this page about?]
- Audience: [Who is reading this?]

Guidelines to follow:
1. Use the [page type] template from wiki_design/page_templates/
2. Reference WIKI_FORMATTING_GUIDE.md for all formatting rules
3. Follow color and design standards in wiki_design/BRAND_GUIDELINES.md
4. Include YAML front matter with title and description
5. Use proper heading hierarchy (one # per page)
6. Use relative links for internal pages (../path/page.md)
7. Include code blocks with language hints where applicable
8. Use admonition types from Quick Reference

Structure the page as: [briefly describe structure]

Include these sections: [list sections]
```

---

## Standard Page Template

**Use this for:** General content pages, explanations, documentation

```
Create a new standard wiki page about [topic name].

Follow the standard_page template from wiki_design/page_templates/standard_page.md

Page structure:
- YAML front matter with title and description (60-160 characters)
- H1 heading: [Page Title]
- Introduction: [1-2 sentences about what the page covers]
- 2-3 main sections (H2) covering [key topics]
- Include helpful admonitions using the types from QUICK_REFERENCE.md
- "See Also" section with related pages
- Optional "Further Reading" collapsible section

Content requirements:
- Use relative links for internal pages
- Include [specific details/concepts to cover]
- Use admonition type [success/note/warning] for [specific content]
- Keep writing clear and concise

Follow all standards in WIKI_FORMATTING_GUIDE.md and use colors from BRAND_GUIDELINES.md
```

---

## Component Reference Prompt

**Use this for:** Technical documentation, feature references, component guides

```
Create a component reference page for [component/feature name].

Use the component_reference template from wiki_design/page_templates/component_reference.md

Content requirements:
- Clear 1-sentence definition of what [component] is
- Design Standards section with "Dos" and "Don'ts" admonitions
- Basic usage examples with Markdown syntax
- [Number] of variants with descriptions
- Advanced usage section covering [specific features]
- Browser/theme support checklist
- See Also section linking to related components

Specific features to document:
- [Feature 1]: [Description]
- [Feature 2]: [Description]
- [Feature 3]: [Description]

Include code examples for:
- Basic usage
- Each variant
- Advanced features

Follow WIKI_FORMATTING_GUIDE.md and reference colors from BRAND_GUIDELINES.md
```

---

## Procedural Guide Prompt

**Use this for:** Step-by-step instructions, how-to guides, tutorials

```
Create a procedural guide: "How to [action/task]"

Use the procedural_guide template from wiki_design/page_templates/procedural_guide.md

Content requirements:
- Clear introduction explaining the goal and audience
- Prerequisites section listing [required items/knowledge]
- Step-by-step instructions with [number] main steps
- Code/command examples for each step where applicable
- Verification checklist to confirm success
- Troubleshooting section covering [common issues]:
  - Issue 1: [description]
  - Issue 2: [description]
- Alternative approaches for [specific scenarios]
- Next steps/related guides

Writing style:
- Use imperative verbs (Do, Create, Run, etc.)
- Keep steps clear and concise
- Include helpful tips in tip admonitions
- Warning admonitions for potential problems

Follow all standards in WIKI_FORMATTING_GUIDE.md
```

---

## Overview/Landing Page Prompt

**Use this for:** Topic area introductions, landing pages, concept overviews

```
Create an overview page for [topic area].

Use the overview_page template from wiki_design/page_templates/overview_page.md

Page structure:
- Brief definition and why it matters
- Key concepts section with [concept 1], [concept 2], [concept 3]
- Benefits section covering [benefit 1], [benefit 2], [benefit 3]
- "How to Get Started" table directing users to [guide type] guides
- Key Topics section with 3-4 major areas:
  - [Topic 1]: [1-2 sentences] → Link to detail page
  - [Topic 2]: [1-2 sentences] → Link to detail page
  - [Topic 3]: [1-2 sentences] → Link to detail page
- Quick Reference table with [structure type]
- Best Practices: Do's and Don'ts admonitions
- Recommended learning path from beginner to advanced
- FAQ section with [number] common questions

Navigation goals:
- Help new users get started quickly
- Guide experienced users to relevant resources
- Show how different topics connect

Follow WIKI_FORMATTING_GUIDE.md and BRAND_GUIDELINES.md
```

---

## FAQ Page Prompt

**Use this for:** Frequently asked questions, Q&A pages

```
Create an FAQ page about [topic].

Use the faq template from wiki_design/page_templates/faq.md

Content requirements:
- Organize Q&A into [number] sections: [Section 1], [Section 2], etc.
- Include [number] Q&A pairs per section
- Questions phrased as actual questions (e.g., "How do I...?", "What is...?")
- Answers that are concise but complete (1-3 sentences + link if needed)
- Link to detailed guides for questions requiring more explanation

Sections to include:
- General Questions: [topic] basics and concepts
- Getting Started: How to [specific tasks]
- Common Issues: Problems and solutions
- How-To: Procedural questions
- Best Practices: Recommendations
- [Additional section]: [Topic]

For problem questions:
- Use "Symptoms:" to describe what user might see
- Provide solution steps or links to full troubleshooting guide

Follow WIKI_FORMATTING_GUIDE.md format and standards
```

---

## Glossary Entry Prompt

**Use this for:** Terminology pages, definitions, concept glossaries

```
Create a glossary page for [topic area] terminology.

Use the glossary_entry template from wiki_design/page_templates/glossary_entry.md

Content requirements:
- Alphabetically organized entries from A-Z
- For each entry include:
  - Definition: [Clear 1-2 sentence explanation]
  - Context: When/where this term is used
  - Example: [Brief usage example]
  - Related terms: [Links to related entries]
  - Learn more: [Link to detailed guide]
- Acronyms & Abbreviations table with [number] common acronyms
- Concepts & Patterns section covering [concept 1], [concept 2], etc.
- Common Phrases section with [phrase 1], [phrase 2], etc.

Terms to include:
- [Term 1]: [Definition]
- [Term 2]: [Definition]
- [Term 3]: [Definition]
[add more as needed]

Acronyms to include:
- [ACR1]: [Full Form] - [Definition]
- [ACR2]: [Full Form] - [Definition]
[add more as needed]

Use tables for acronyms and concepts.
Follow WIKI_FORMATTING_GUIDE.md
```

---

## Editing Existing Page Prompt

**Use this for:** Updating, expanding, or restructuring existing pages

```
Edit the existing wiki page at [path/to/page.md] to:

Changes needed:
1. [Description of change 1]
2. [Description of change 2]
3. [Description of change 3]

Requirements:
- Maintain the existing page structure/template
- Follow WIKI_FORMATTING_GUIDE.md formatting rules
- Use relative links for internal references
- Don't change the YAML front matter unless updating title/description
- Keep consistent with the page's original tone and audience

Additional instructions:
[Any specific requirements for this edit]

After editing:
- Verify heading hierarchy is correct
- Check all links are relative paths
- Ensure all code blocks have language hints
```

---

## Adding New Section to Page

**Use this for:** Expanding existing pages with new sections

```
Add a new section to [path/to/page.md] at [location: after [section name] / before [section name]]

New section details:
- Section title (H2): [Section Name]
- Purpose: [What this section covers]
- Content: [Brief description of what to include]
- Subsections (H3): [subsection 1], [subsection 2]
- Include: [Admonitions/examples/code blocks, etc.]

Content to cover:
- [Point 1]
- [Point 2]
- [Point 3]

Style requirements:
- Follow the page's existing tone and structure
- Use admonition types from QUICK_REFERENCE.md appropriately
- Include code examples where relevant
- Use relative links for internal pages

Reference materials:
- Page template: [relevant template]
- Formatting guide: WIKI_FORMATTING_GUIDE.md
```

---

## Batch Page Creation Prompt

**Use this for:** Creating multiple related pages at once

```
Create a set of related wiki pages for [topic area]:

Pages to create:

1. Overview Page: "[Topic Area] Overview"
   - Use overview_page template
   - Topics to cover: [topic 1], [topic 2], [topic 3]
   - Should link to: [guide 1], [guide 2], [guide 3]

2. Guide Page: "How to [task 1]"
   - Use procedural_guide template
   - Steps: [number] steps
   - Should cover: [specific content]

3. Reference Page: "[Component/Feature Name] Reference"
   - Use component_reference template
   - Should document: [features]
   - Include variants for: [variant 1], [variant 2]

4. FAQ Page: "[Topic] FAQ"
   - Use faq template
   - Answer questions about: [topic 1], [topic 2]

General requirements for all pages:
- Include proper YAML front matter
- Use relative links between pages
- Reference WIKI_FORMATTING_GUIDE.md
- Apply colors from BRAND_GUIDELINES.md
- Test in both light and dark modes

Cross-linking:
- Each page should reference the others in "See Also" sections
- Overview page should link to all specific guides
```

---

## Style & Tone Refinement Prompt

**Use this for:** Improving existing content without major restructuring

```
Review and improve the wiki page at [path/to/page.md] for:

Style improvements:
- Simplify language while maintaining accuracy
- Make explanations more concise
- Strengthen emphasis where needed
- Improve clarity and readability

Structure improvements:
- Ensure proper heading hierarchy
- Break up long paragraphs
- Add section breaks with horizontal rules
- Improve whitespace and scanability

Content improvements:
- Add admonitions where helpful (see QUICK_REFERENCE.md)
- Include examples where beneficial
- Link to related pages
- Verify all links are relative paths

Guidelines to follow:
- Reference WIKI_FORMATTING_GUIDE.md
- Maintain consistent tone with existing pages
- Don't change YAML front matter
- Keep changes minimal if the page structure is already good

Specific areas to improve:
[List any specific sections or issues]
```

---

## Quick Tips for Effective Prompts

### Include Context

Always tell Copilot:
- What page type you're creating
- Which template to use
- What the page is about

### Reference the Documentation

Always include phrases like:
- "Follow WIKI_FORMATTING_GUIDE.md"
- "Use the [template name] from wiki_design/page_templates/"
- "Reference QUICK_REFERENCE.md for admonition types"

### Be Specific About Content

Tell Copilot exactly what to include:
- Number of sections
- Specific topics to cover
- Types of admonitions to use
- Code examples needed

### Specify Structure

Describe the page structure clearly:
- Section headings
- Subsections needed
- Tables, lists, or code blocks
- See Also/Further Reading format

### Quality Checkpoints

Include final verification steps:
```
Before finalizing:
- Verify YAML front matter is present
- Check heading hierarchy (1 #, then ##, ###)
- Ensure all internal links use relative paths
- Verify all code blocks have language hints
- Check image alt text
- Test admonition types match their purpose
```

---

## Common Customizations

### Add Company-Specific Content

```
Create [page type] about [topic].
Additionally, include information about [company/project specific details].
Include [company-specific best practices / terminology].
```

### Adjust Audience Level

```
Create [page type] for [audience level: beginner/intermediate/advanced].
Assume knowledge of: [prerequisite knowledge]
Explain using: [examples/analogies/code samples]
```

### Specify Length

```
Create [page type] keeping it [brief (1-2 sections) / detailed (4-5 sections) / comprehensive (6+ sections)].
```

### Add Specific Components

```
Include the following components:
- Code examples in [language1], [language2]
- Tables for [comparison/reference]
- [number] admonitions of type [type]
- Diagrams/visual references for [concept]
```

---

## Pro Tips

1. **Reference this document** in your prompt:
   > "Follow the prompt template at wiki_design/COPILOT_PROMPTS.md"

2. **Be iterative** — if the first version isn't quite right:
   > "Revise the page to [specific change] while keeping the rest the same"

3. **Ask for multiple versions**:
   > "Create 2 variants: one for beginners, one for advanced users"

4. **Link to output** — Tell Copilot where to save:
   > "Create this at wiki/path/to/new_page.md"

5. **Use existing pages as examples**:
   > "Follow the same style and structure as wiki_design/components/admonitions.md"

---

## Quick Reference for Common Page Types

| Page Type | Template | Key Prompt Elements |
|-----------|----------|-------------------|
| General Content | standard_page | Sections, introduction, see also |
| Technical Docs | component_reference | Examples, variants, design standards |
| Tutorials | procedural_guide | Steps, prerequisites, troubleshooting |
| Topic Intro | overview_page | Key concepts, learning path, resources |
| Q&A | faq | Questions, concise answers, categories |
| Definitions | glossary_entry | Alphabetical, context, related terms |

---

!!! success "Ready to Create?"
    Pick a template above, customize it for your page, and paste it into Copilot chat.
    
    Copilot will create professional wiki pages that follow all your formatting rules and design guidelines.

---

## See Also

- [Page Templates](./page_templates/)
- [Wiki Formatting Guide](../WIKI_FORMATTING_GUIDE.md)
- [Quick Reference](./QUICK_REFERENCE.md)
- [Brand Guidelines](./BRAND_GUIDELINES.md)
