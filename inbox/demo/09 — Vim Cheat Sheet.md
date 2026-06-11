# Vim cheat sheet for ZenNotes

ZenNotes ships with Vim mode on by default. The editor uses CodeMirror Vim bindings, and the app adds its own keyboard-first flows around panes, panels, search, and built-in views.

## Global shortcuts

| Keys | Action |
| --- | --- |
| `⌘P` | Search notes |
| `⇧⌘P` | Open command palette |
| `⇧⌘N` | New Quick Note |
| `⌘,` | Open Settings |
| `⌘1` | Toggle sidebar |
| `⌘2` | Toggle connections |
| `⌘3` | Toggle outline panel |
| `⌘.` | Toggle Zen mode |
| `⌘W` | Close active tab or built-in view |
| `⌥Z` | Toggle word wrap |

If you explicitly turn Vim mode off, `⌘F` or `Ctrl+F` becomes an extra direct note-search shortcut.

## Pane and panel motion

| Keys | Action |
| --- | --- |
| `Ctrl-w h` / `j` / `k` / `l` | Move focus between sidebar, note list, editor panes, outline, and connections |
| `Ctrl-w v` | Split right |
| `Ctrl-w s` | Split down |
| `Ctrl-o` | Jump back in note history |
| `Ctrl-i` | Jump forward in note history |

## Leader (`Space`) shortcuts

| Keys | Action |
| --- | --- |
| `Space o` | Open buffers |
| `Space f` | Search notes |
| `Space s t` | Search vault text |
| `Space e` | Toggle sidebar |
| `Space p` | Open note outline |
| `Space l f` | Format the active note |
| `Space`, then pause | Show leader hints when enabled |

Leader hints can be **timed** or **sticky** in Settings. Sticky mode stays open until you press `Space` again or `Esc`.

## Folding

| Keys | Action |
| --- | --- |
| `zc` | Fold the heading at the cursor |
| `zo` | Unfold the heading at the cursor |
| `zM` | Fold all headings |
| `zR` | Unfold all headings |

## Links and hint mode

| Keys | Action |
| --- | --- |
| `gd` | Follow wikilink, markdown link, or open/create note under cursor |
| `f` | Hint mode for clickable targets when not in insert mode |

## Sidebar, list, and built-in views

When focus is in the sidebar, note list, Tasks, Tags, Archive, Trash, or Quick Notes tab:

| Keys | Action |
| --- | --- |
| `j` / `k` | Move selection |
| `gg` / `G` | Jump to top / bottom |
| `Enter` / `l` | Open selected item |
| `h` | Collapse or move back |
| `o` | Toggle selected folder |
| `/` | Filter the current list or view |
| `m` | Open the context menu for the selected row |
| `Esc` | Return toward the editor |

View-specific extras:

| Keys | Action |
| --- | --- |
| `Space` / `x` | Toggle selected task in **Tasks** |
| `r` | Restore selected note in **Trash** |
| `x` / `d` | Permanently delete selected note in **Trash** |
| `:` | Open the local ex prompt in **Tasks** or **Tags** |

## Preview and connections

When focus is in rendered preview or the connections panel:

| Keys | Action |
| --- | --- |
| `j` / `k` | Scroll line by line |
| `Ctrl-d` / `Ctrl-u` | Half-page down / up |
| `gg` / `G` | Jump to top / bottom |
| `p` | Peek the selected backlink in Connections |
| `h` / `Esc` | Back out toward the editor |

## Ex commands

Type `:` in normal mode:

| Command | Action |
| --- | --- |
| `:w` | Save the active note |
| `:q` | Close the current tab or built-in view |
| `:wq` | Save and close |
| `:help` | Open the built-in manual |
| `:tasks` | Open Tasks |
| `:tag foo bar` | Open Tags filtered to `foo` and `bar` |
| `:trash` | Open Trash |
| `:e path` / `:edit path` | Open or create a note by vault-relative path |
| `:new [path]` | Create a new note |
| `:split` / `:vsplit` | Split the current tab down or right |
| `:bn` / `:bp` | Next / previous tab |
| `:buffers` / `:ls` | Open the buffer switcher |
| `:bd` / `:bc` | Close the active tab |
| `:view edit|split|preview` | Switch the current pane mode |
| `:editmode` / `:splitmode` / `:previewmode` | Direct aliases for note mode changes |
| `:zen` / `:zen on` / `:zen off` | Toggle or force Zen mode |
| `:format` | Format the active note |
| `:fold` / `:unfold` | Fold or unfold the current heading |
| `:foldall` / `:unfoldall` | Fold or unfold every heading |
| `:cmd query` / `:commands` | Run or browse command palette entries |
| `Tab` on the ex line | Complete commands and supported arguments |

## One more important note

Every shortcut above can now be remapped in [[12 — Settings and Keymaps]]. Vim mode is the default, but the app no longer hardcodes every sequence forever.

#demo #vim #reference
