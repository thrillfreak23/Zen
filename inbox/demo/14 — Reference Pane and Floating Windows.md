# Reference pane and floating windows

ZenNotes is strongest when you can keep context visible while still writing. This note covers the pinned reference pane, link preview workflows, and floating notes.

## Reference pane

The reference pane is for keeping a second document visible while you work in the main note.

Good uses:

- drafting against a spec
- reading a PDF while taking notes
- comparing two notes side by side
- keeping a glossary or checklist open while editing

## What can live there

- another markdown note
- a PDF
- a linked document opened from the current note

This keeps the main pane focused on writing while the side pane holds supporting material.

## Link-following flows

When the cursor is on a wikilink or markdown link:

- `gd` follows it in Vim mode
- PDFs can pin into the reference pane
- missing notes can be created from the link target

That means links are not just navigation. They can become working context.

## Connections + reference workflow

The **Connections** panel works well with the reference pane:

- inspect backlinks
- move to a related note
- peek a backlink
- pin the most useful one beside the current draft

This is especially useful for research notes and longer documentation trees.

## Floating windows

Sometimes you do not want a second pane inside the same layout. In that case, a note can open in its own floating window from the context menu.

Floating windows are useful when:

- you want a scratch note on another monitor
- you are comparing two notes without disturbing the main layout
- you want a temporary detached reference

They are intentional, separate work surfaces, not just accidental duplicate tabs.

## Research pattern

One practical pattern:

1. Keep the current draft in **Edit** or **Split**
2. Open **Connections**
3. Find a related note or PDF
4. Pin it in the reference pane or open it in a floating window
5. Keep writing without losing context

## Good companion notes in this tour

- [[07 — Wiki Links and Tags]] for backlinks, tags, and search
- [[11 — Workspace, Search, and Views]] for the larger pane model
- [[06 — Callouts and Footnotes]] for local files
- [[10 — Ideas and Tasks]] for a note that benefits from supporting context

## Try this now

- Open this note, then pin [[11 — Workspace, Search, and Views]]
- Open **Connections** on [[10 — Ideas and Tasks]]
- Follow a wikilink with `gd`
- Open a note in a floating window from its context menu

#demo #reference #research #windows
