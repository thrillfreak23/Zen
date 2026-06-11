# Tables and task lists

## Tables

Plain GFM tables. Alignment is controlled with colons in the divider row.

| Feature    |  Support   | Notes                                                     |
| ---------- | :--------: | --------------------------------------------------------- |
| Headings   |     ✅     | Fold from the editor gutter and jump via the outline.     |
| Wiki links |     ✅     | `[[Title]]` resolves by note name.                        |
| Tags       |     ✅     | Written inline as `#like-this`.                           |
| Math       |     ✅     | KaTeX, inline and display.                                |
| Mermaid    |     ✅     | Rendered inside preview and split view.                   |
| Search     |     ✅     | Notes by title/path, vault text by fuzzy content search.  |
| Sync       | File-based | Use any sync tool that watches folders.                   |

Right-aligned numbers:

| Quarter |  Revenue |  Delta |
| ------: | -------: | -----: |
|      Q1 | $124,300 |  +4.2% |
|      Q2 | $131,980 |  +6.2% |
|      Q3 | $129,010 |  −2.3% |
|      Q4 | $152,407 | +18.1% |

## Task lists

Every checkbox survives on disk as normal markdown like `- [ ]` and `- [x]`.

## What ZenNotes task parsing supports

### Core checkboxes

- [ ] Open task
- [x] Completed task
- [X] Uppercase `X` also counts as completed

### Different list styles still count

- [ ] Bulleted task using `-`
+ [ ] Bulleted task using `+`
* [ ] Bulleted task using `*`
1. [ ] Ordered task using `1.`
2) [ ] Ordered task using `2)`
> - [ ] Blockquoted task lines are parsed too

### Nested tasks

- [ ] Weekly review
  - [ ] Clear inbox to zero
  - [ ] Triage [[10 — Ideas and Tasks]]
  - [x] Back up vault
  - [ ] Plan next week
    - [ ] Monday — design review
    - [ ] Tuesday — code-freeze prep
    - [x] Saturday — offline

### Metadata tokens on the task line

- [ ] Ship the onboarding checklist due:2026-04-18 !high #onboarding #docs
- [ ] Refresh demo screenshots due:2026-04-22 !med #demo #assets
- [ ] Clean up seed notes !low #maintenance
- [ ] Wait for design sign-off @waiting #design
- [ ] Review vault search UX due:2026-04-30 !high #search #ux

The parser understands these tokens:

| Token | Meaning | Example |
| ----- | ------- | ------- |
| `due:YYYY-MM-DD` | ISO due date used for grouping | `due:2026-04-22` |
| `!high` / `!med` / `!low` | Priority marker | `!high` |
| `@waiting` | Moves the task into the Waiting group | `@waiting` |
| `#tag` | Inline task tag, searchable in the Tasks view | `#design` |

### What the Tasks view does with them

- Tasks with no due date land in **Today**
- Tasks due today or already overdue also land in **Today**
- Tasks due in the future land in **Upcoming**
- Tasks with `@waiting` land in **Waiting**
- Checked tasks land in **Done**
- Overdue tasks contribute to the overdue count in the **Today** section

### Filtering and navigation

Press the sidebar **Tasks** row to scan every live note across **Inbox**, **Quick Notes**, and **Archive**. From there you can:

- filter by task content
- filter by note title
- filter by inline `#tags`
- filter by priority markers like `!high`
- press `Enter` or `o` to open the source note
- press `Space` or `x` to toggle the selected task without leaving the list

### Ignored on purpose

Tasks inside fenced code blocks are not parsed, so you can document task syntax safely:

```md
- [ ] This looks like a task
- [x] But code fences are ignored by the vault-wide task scanner
- [ ] That makes examples and snippets safe
```

### Note-level defaults

You can also set due date and priority defaults in frontmatter, then override them inline per task:

```yaml
---
due: 2026-05-01
priority: high
---
```

With defaults like that, a plain line such as `- [ ] Draft roadmap` inherits the due date and priority even without repeating the tokens.

### Rendering checklist

Every item below is wired up:

- [x] Paragraphs
- [x] Emphasis: _italic_, **bold**, ~~strike~~
- [x] Ordered and unordered lists
- [x] Tables
- [x] Task lists
- [x] Blockquotes
- [x] Footnotes (see [[06 — Callouts and Footnotes]])
- [x] Math blocks (see [[04 — Math with KaTeX]])
- [x] Mermaid (see [[05 — Mermaid Diagrams]])
- [x] TikZ, JSXGraph, and function-plot (see [[05b — Math Diagrams]])
- [x] Vault-wide Tasks grouping and filtering
- [ ] Screenshots in the tour due:2026-04-25 !med #docs

## Tasks as an app feature

The Tasks tab is not just a renderer demo. It is a vault-wide operational view for planning and review. Use it when you want one place to see what is due, what is waiting, what is done, and where each task lives.

#demo #tasks #tables
