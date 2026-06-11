# Callouts, footnotes, files, and embeds

This note covers the rich block-level extras that still live comfortably inside markdown files.

## Callouts

Callouts are blockquotes that start with `> [!type]`.

> [!note]
> Use note callouts for extra context that should stand out without becoming a new section.

> [!tip] Keyboard tip
> Press `Space o` to open the buffer switcher when tabs are hidden or you want to jump fast between open buffers.

> [!warning]
> Moving a note to Trash asks for confirmation, but permanently deleting from Trash is still destructive.

> [!info] Multi-line
> Callouts can contain:
> - lists
> - `inline code`
> - [[07 — Wiki Links and Tags|wikilinks]]
> - and multiple paragraphs

> [!quote] Portable by design
> ZenNotes adds workflow around markdown, not lock-in around data.

## Footnotes

Footnotes link both ways and stay readable in the raw file.[^workflow]

Footnotes are useful for side comments that should not interrupt the main flow.[^tip]

[^workflow]: Footnote references use `[^label]` inline and `[^label]: text` at the bottom of the note.
[^tip]: They work well in long writing, specs, and research notes where parenthetical digressions get noisy.

## Strikethrough and highlights

~~Legacy wording~~ can stay visible for history, while ==highlights== are good for passages you want to notice quickly during review.

## Images and local files

Files stay local to the vault. Dropping a file into the editor inserts a normal markdown reference to the file, and by default ZenNotes places it in the vault root.

Example image:

![ZenNotes demo card](<../../zennotes-demo-card.svg>)

That relative path is the recommended form because it keeps the note portable inside the vault:

```md
![ZenNotes demo card](<../../zennotes-demo-card.svg>)
```

## File workflows

- Use the footer **Files** action to browse files anywhere in the vault.
- Image embeds render inline in preview and split mode.
- PDFs can be opened in the pinned reference pane so you can read beside your notes.
- Because these are just files, reveal them in Finder and manage them with normal tools if you want.

For the larger reading workflow around pinned notes, PDFs, and detached note windows, see [[14 — Reference Pane and Floating Windows]].

## Why this matters

ZenNotes is strongest when prose, references, and files live together:

- callouts for guidance or warnings
- footnotes for side context
- images for screenshots and visual notes
- PDFs in the reference pane for side-by-side reading

#demo #reference #attachments
