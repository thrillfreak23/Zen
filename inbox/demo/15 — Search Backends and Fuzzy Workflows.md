# Search backends and fuzzy workflows

ZenNotes has two different search surfaces, and the deeper one can be powered by different backends.

## Two searches, two jobs

### Note search

Use when you want to find a note by title or path:

- `⌘P`
- `Space f`

This is the fastest way to jump to a file you already roughly know.

### Vault text search

Use when you want to find matching text inside note bodies:

- `Space s t`

This searches across note content and jumps directly to the matching line when you open a result.

## Backends

Vault text search can run on:

- **Auto**
- **Built-in**
- **ripgrep**
- **fzf**

### Auto

`Auto` prefers:

1. `fzf`
2. `ripgrep`
3. built-in fallback

That makes the app adapt to what is installed on the machine.

### Built-in

Use this when you want:

- zero external dependencies
- predictable behavior across machines
- a search path that always exists even when no tools are installed

### ripgrep

Use this when you want:

- strong plain-text search performance
- system-level tooling you may already use outside the app
- a backend that is familiar to terminal users

### fzf

Use this when you want:

- terminal-style fuzzy matching behavior
- ranking that feels close to launcher workflows
- an external backend often used by Vim and Neovim users

## Custom binary paths

If `rg` or `fzf` are not in your normal `PATH`, ZenNotes lets you point to them directly from Settings.

Examples:

- `/opt/homebrew/bin/rg`
- `/opt/homebrew/bin/fzf`
- `/usr/local/bin/rg`

Blank means “use whatever is on PATH”.

## Runtime backend vs configured backend

ZenNotes shows:

- what you configured
- what tools are available
- what backend is actually being used

That distinction matters because:

- `Auto` may resolve differently on different machines
- explicit `ripgrep` or `fzf` settings can still fall back if the binary path is invalid

## Search result behavior

Vault text search is designed to be navigational, not just informational:

- results stay keyboard navigable
- the active row stays in view while you move
- the matching text is highlighted in the result
- opening a result moves the cursor to the match in the note

This makes it feel more like a picker than a grep dump.

## Good habits

- use note search when you know the file
- use vault text search when you only know the phrase
- leave the backend on **Auto** unless you have a reason to force one
- configure explicit binary paths if your tools live outside `PATH`

## Related notes

- [[07 — Wiki Links and Tags]] for search in the context of notes, tags, and links
- [[11 — Workspace, Search, and Views]] for where these pickers fit into the app
- [[12 — Settings and Keymaps]] for changing the backend and remapping the shortcut

#demo #search #fzf #ripgrep #reference
