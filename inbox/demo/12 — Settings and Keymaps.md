# Settings and keymaps

ZenNotes is keyboard-first by default, but it is not rigid anymore. Settings now cover both presentation and behavior.

## Appearance

From Settings you can tune:

- theme family
- light or dark mode
- theme variant or contrast
- dark sidebar treatment

The point is to keep the app comfortable for long sessions without changing the underlying note files.

## Editor behavior

Key editor settings include:

- Vim mode on or off
- leader key hints on or off
- timed vs sticky leader hints
- leader hint duration
- live preview
- note tabs
- word wrap
- PDF behavior in edit mode
- date-titled Quick Notes

## Vault text search backends

Vault text search can be powered by:

- **Auto**
- **Built-in**
- **ripgrep**
- **fzf**

You can also set explicit binary paths for `rg` and `fzf` in case they live outside your normal `PATH`.

ZenNotes now shows:

- what tools are available
- what backend is configured
- what backend is actually being used at runtime

That matters because **Auto** can fall back, and explicit backends can also fall back when the configured binary path is missing.

## Typography and layout

You can tune:

- interface font
- reading font
- monospace font
- editor and preview font size
- line height
- reading width
- editor width
- centered vs left-aligned content
- line numbers

These are workflow settings, not note-format settings. The markdown file stays the same.

## Keymaps

Keymaps are now configurable from inside the app:

- global shortcuts
- leader sequences
- pane-prefix motions
- Vim-specific editor actions
- list and view navigation

That means you can remap things like:

- search notes
- search vault text
- toggle Zen mode
- pane movement
- fold motions
- leader flows such as `Space s t`

Multi-step sequences are supported, so the keymap system can handle more than single shortcuts.

## Vault and About

The rest of Settings handles the vault and app identity:

- reveal or change the vault location
- inspect the app version
- see the About section
- find the Lumary Labs link
- remember that Settings save automatically on this device

## Practical advice

If you are learning the app:

1. keep Vim mode on
2. enable leader hints
3. leave search backend on **Auto**
4. only start remapping after the defaults feel familiar

That gives you the clearest path through the built-in help, demos, and keyboard flows.

For a deeper walkthrough of runtime backend selection, fallbacks, and fuzzy content search behavior, see [[15 — Search Backends and Fuzzy Workflows]].

#demo #settings #keymaps #reference


