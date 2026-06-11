# Markdown basics

ZenNotes starts with ordinary markdown. The app adds keyboard-first workflows around it, but the source stays portable and readable everywhere.

## Headings

```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

Headings matter for more than styling:

- they show up in the **outline**
- they can be folded with `zc` and unfolded with `zo`
- long notes can be searched by heading with `Space p`

## Emphasis

*Italic* with single asterisks, **bold** with double, ***bold italic*** with triple, `inline code` with backticks, ~~strikethrough~~ with tildes, and ==highlight== with double equals.

## Paragraphs and line breaks

A blank line starts a new paragraph.
A single newline usually stays in the same paragraph.

Leave two trailing spaces when you really want a hard line break.  
Like this.
==Highlight==
## Lists

Unordered:

- Apples
- Bananas
  - Cavendish
  - Plantain
- Cherries

Ordered:

1. Draft the note
2. Refine the structure
3. Ship the change

## Links

- External: [ZenNotes](https://lumarylabs.com)
- Autolink: <https://lumarylabs.com>
- Wikilink: [[07 — Wiki Links and Tags]]
- Custom label: [[11 — Workspace, Search, and Views|workspace guide]]

## Blockquotes and dividers

> Markdown still does a lot with very little.
>
> ZenNotes just makes it faster to navigate and work with.

---

## Frontmatter

YAML frontmatter works fine at the top of a note:

```yaml
---
title: My Note
date: 2026-04-16
tags: [project, research]
priority: high
---
```

ZenNotes does not require frontmatter, but features like daily notes, tags, and task defaults can make use of it.

## Slash commands

ZenNotes also helps you write these structures faster:

- type `/` at the start of a line or after whitespace
- choose items like headings, bullets, numbered lists, tasks, callouts, code blocks, tables, math blocks, links, images, and dividers
- keep typing after `/` to filter the insert menu

That means markdown stays plain, but you do not have to remember every snippet from scratch.

## What to try in this note

- Put the cursor on a heading and fold it.
- Switch the note between **Edit**, **Split**, and **Preview**.
- Open the outline with `Space p`.
- Search for this note with `Space f`.

## What's next

Jump to [[02 — Code Blocks]] for syntax highlighting, [[06 — Callouts and Footnotes]] for richer block styles, or back to [[00 — Start Here]].

#demo #markdown
