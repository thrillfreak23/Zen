# Code blocks

ZenNotes treats code fences as plain markdown on disk and renders them with syntax highlighting in preview and split view.

## A fast way to insert them

Type `/` and choose **Code block** if you do not want to type the fence manually.

## TypeScript

```ts
export interface User {
  id: string
  name: string
  roles: string[]
}

export async function fetchUser(id: string): Promise<User | null> {
  const response = await fetch(`/api/users/${id}`)
  if (!response.ok) return null
  return (await response.json()) as User
}
```

## Python

```python
from dataclasses import dataclass

@dataclass
class Point:
    x: float
    y: float

    def distance_to(self, other: "Point") -> float:
        return ((self.x - other.x) ** 2 + (self.y - other.y) ** 2) ** 0.5
```

## Bash

```bash
#!/usr/bin/env bash
set -euo pipefail

for note in inbox/*.md; do
  words=$(wc -w < "$note")
  printf "%6d  %s\n" "$words" "$(basename "$note")"
done
```

## Rust

```rust
use std::collections::HashMap;

fn word_count(text: &str) -> HashMap<String, usize> {
    let mut counts = HashMap::new();
    for word in text.split_whitespace() {
        *counts.entry(word.to_lowercase()).or_insert(0) += 1;
    }
    counts
}
```

## JSON

```json
{
  "name": "ZenNotes",
  "productName": "ZenNotes",
  "version": "0.1.0",
  "scripts": {
    "dev": "electron-vite dev",
    "build": "electron-vite build"
  }
}
```

## Diff

```diff
- Space /
+ Space s t
```

## Plain text

```
No language tag, no syntax highlighting.
Useful for raw config examples or ASCII notes.
```

## Inline code

Use `inline code` when the snippet belongs inside a sentence.

## Workflow notes

- **Edit** mode is best for writing or refactoring the raw fence.
- **Split** mode is ideal when you want source on one side and highlighted output on the other.
- Fenced blocks are ignored by the task scanner, so `- [ ]` inside code stays an example, not a live task.
- Vault text search can still find matching text inside code fences because they are part of the note body.

## What's next

See [[05 — Mermaid Diagrams]] for Mermaid fences, [[05b — Math Diagrams]] for TikZ, JSXGraph, and function-plot, or [[10 — Ideas and Tasks]] for how snippets mix with prose and planning in a real note.

#demo #code
