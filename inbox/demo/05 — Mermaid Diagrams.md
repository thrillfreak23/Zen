# Mermaid diagrams

Mermaid fences render inline in ZenNotes. They are still just markdown code blocks on disk, so you can version them, diff them, and edit them anywhere.

For TikZ, JSXGraph, and function-plot, see [[05b — Math Diagrams]].

## A fast way to insert one

Type `/` and choose **Code block**, then change the language to `mermaid`.

## Flowchart

```mermaid
flowchart LR
  A([User types]) --> B{Vim mode?}
  B -- yes --> C[CodeMirror vim keymap]
  B -- no --> D[Standard editing]
  C --> E[Save to .md]
  D --> E
  E --> F([File on disk])
```

## Sequence diagram

```mermaid
sequenceDiagram
  autonumber
  actor U as User
  participant R as Renderer
  participant M as Main process
  participant D as Disk

  U->>R: Type in editor
  R->>M: writeNote(path, body)
  M->>D: fs.writeFile(...)
  D-->>M: ok
  M-->>R: NoteMeta
  R-->>U: Clean tab title
```

## State diagram

```mermaid
stateDiagram-v2
  [*] --> Draft
  Draft --> Review : Submit
  Review --> Draft : Request changes
  Review --> Approved : Accept
  Approved --> Published : Ship
  Published --> Archived : 90 days
  Archived --> [*]
```

## Gantt chart

```mermaid
gantt
  title Product roadmap
  dateFormat  YYYY-MM-DD
  axisFormat  %b %d

  section Editor
  Vim motions polish      :done,    vim1, 2026-03-10, 5d
  Outline panel           :done,    out1, 2026-03-17, 3d
  Attachments preview     :active,  att1, 2026-04-15, 7d
  Multi-window sync       :         mws1, after att1, 5d

  section Release
  QA pass                 :         qa1, after mws1, 3d
  Ship                    :milestone, rel1, after qa1, 0d
```

## Pie chart

```mermaid
pie title How the day was spent
  "Deep work" : 45
  "Meetings"  : 15
  "Slack"     : 10
  "Reading"   : 20
  "Breaks"    : 10
```

## Vault map

```mermaid
graph TB
  subgraph Lifecycle
    Q[Quick Notes]
    I[Inbox]
    A[Archive]
    T[Trash]
  end
  Q --> I
  I --> A
  I --> T
  A --> I
  T --> I
```

## Working with diagrams in the app

- **Split** mode is usually the sweet spot: raw source on one side, rendered diagram on the other.
- Diagrams are still searchable because the source fence lives in the note body.
- If Mermaid syntax breaks, ZenNotes falls back to showing the source block, which makes failures debuggable instead of mysterious.

## What's next

Stay in diagram mode with [[05b — Math Diagrams]] if you want interactive geometry, coordinate figures, or compact function plots.

#demo #mermaid #diagrams
