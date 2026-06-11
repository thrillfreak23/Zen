# Commands, help, and demo tour

ZenNotes is keyboard-first, so discoverability matters. This note covers the command palette, the built-in Help manual, and the demo-tour commands that can seed a starter vault for new users.

## Command palette

Open the command palette with:

- `⇧⌘P`
- `:commands`
- `:cmd query`

Use it when you cannot remember a shortcut, when Vim mode is off, or when you want to browse what the app can do without digging through menus.

Typical commands worth trying:

- `Open Help`
- `Open Settings`
- `Search notes`
- `Generate Demo Tour Notes`
- `Remove Demo Tour Notes`
- `Switch to Edit Mode`
- `Switch to Split Mode`
- `Switch to Preview Mode`
- `Open Tasks`
- `Open Trash`

## Ex commands

If you live in normal mode, the ex line is the fastest path for many actions:

```vim
:help
:tasks
:trash
:buffers
:view split
:zen
:cmd help
```

The ex line also supports completion with `Tab`, including command arguments like `:view edit|split|preview` and `:zen toggle|on|off`.

## Built-in Help

ZenNotes ships with an in-app manual instead of making you leave the app to learn it.

Ways to open it:

- footer **Help**
- `:help`
- command palette → `Open Help`

The Help view covers:

- quick start
- core concepts
- shortcuts
- Vim flows
- ex commands
- settings
- search backends

## Demo tour commands

The demo vault itself is seedable from inside the app.

Use:

- command palette → `Generate Demo Tour Notes`
- command palette → `Remove Demo Tour Notes`
- `:demo_generate`
- `:demo_remove`

### What generation does

- creates a guided note set under `inbox/demo`
- adds the bundled demo file at the vault root
- opens the tour start note so the onboarding flow begins immediately

### What removal does

- removes the seeded demo notes
- removes the bundled demo file
- leaves the rest of the vault alone

That makes the tour useful for:

- first-time users
- resettable demos
- showing the product to someone else
- smoke-testing renderer features in one place

## Why this matters

The app can stay low-chrome and still be discoverable if:

- commands are searchable
- Help is built in
- the starter content is one command away

That combination is a large part of what makes a keyboard-first app approachable instead of intimidating.

## Try this now

- Open the command palette and search for `help`
- Run `:cmd zen`
- Run `Generate Demo Tour Notes` in a test vault
- Open [[12 — Settings and Keymaps]] after this note to see how the shortcuts behind these commands can be remapped

#demo #commands #help #onboarding
