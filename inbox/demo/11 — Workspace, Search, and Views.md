# Workspace, search, and views

This note covers the part of ZenNotes that is not just markdown rendering: how the workspace behaves while you are moving around a vault.

## The three working zones

ZenNotes is organized around three persistent areas:

1. **Sidebar** for folders, built-in rows, tags, and utility entry points
2. **Note list** for the current folder, files, or list-like result sets
3. **Editor pane** for tabs, splits, preview, built-in views, and focused writing

The useful part is that each zone has its own keyboard loop, so you can stay off the mouse without losing place.

## Edit, split, and preview

Each note can be viewed in three ways:

- **Edit** for raw markdown authoring
- **Split** for source and rendered output side by side
- **Preview** for reading-only rendering

You can switch modes from the toolbar, from the command palette, or from ex commands like:

```vim
:view edit
:view split
:view preview
```

## Tabs, buffers, and panes

- tabs can be on or off
- panes can split right or down
- if tabs are hidden, buffers are still open behind the scenes
- `Space o` or `:buffers` opens the buffer switcher

This keeps ZenNotes usable for both tab-heavy and low-chrome workflows.

## Search modes

### Note search

- `⌘P` globally
- `Space f` in Vim mode
- `⌘F` or `Ctrl+F` as an extra direct shortcut when Vim mode is off
- searches note titles and paths

### Vault text search

- `Space s t`
- searches matching text lines across note contents
- opens the note and jumps to the matching line
- can run on built-in search, `ripgrep`, or `fzf`
- Settings show the runtime backend that is actually being used

## Quick Notes, Inbox, Archive, Trash

These four areas represent different stages of note life:

- **Quick Notes** for fast capture
- **Inbox** for active notes
- **Archive** for cold storage
- **Trash** for recoverable deletion

Behavior differs by design:

- clicking **Quick Notes** still folds and unfolds the sidebar section
- Quick Notes can also open as a dedicated list tab from its context menu
- **Archive** opens as a main-pane list view
- **Trash** opens as a main-pane recovery view

That keeps the sidebar singular instead of turning it into a second file browser.

## Outline, connections, and references

- **Outline** gives you a heading list for the active note
- **Connections** show backlinks, outbound links, and unresolved links
- **Reference pane** is for pinning a note or PDF beside your current work

This is the part of the app that becomes valuable once a vault turns into more than a pile of files.

## Help, Settings, and Files

The footer utilities keep the secondary surfaces discoverable:

- **Files** for local files
- **Help** for the built-in manual
- **Settings** for personalization, Vim behavior, search backends, fonts, layout, and keymaps

For the command palette and seeded onboarding flow, see [[13 — Commands, Help, and Demo Tour]].
For detached note workflows and side-by-side reading context, see [[14 — Reference Pane and Floating Windows]].

## Zen mode

Zen mode hides:

- title bar
- sidebar
- note list
- tabs
- pane header chrome
- outline and connections
- status bar

Only the active editor, preview, or split content remains. It is the cleanest way to focus on a single note.

## Session restore

ZenNotes remembers:

- open tabs
- splits
- built-in views like Help, Tasks, Archive, or Trash
- sidebar layout
- main window position, size, and maximized state

Closing and reopening the app should bring you back to roughly where you left off instead of starting from a blank shell.

#demo #workspace #search #reference
