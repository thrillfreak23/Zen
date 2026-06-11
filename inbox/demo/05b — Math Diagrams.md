# Math diagrams — TikZ, JSXGraph, and function-plot

Beyond Mermaid (see [[05 — Mermaid Diagrams]]) and KaTeX (see [[04 — Math with KaTeX]]), ZenNotes renders three more diagram types from plain fenced code blocks. Each one shines at a different job.

Switch to **Preview** or **Split** mode to see them rendered. The source stays plain markdown on disk.

---

## TikZ — figure-quality math diagrams

Use when you want paper-grade vector figures: coordinate systems, geometry, commutative diagrams, automata, trees, plots. The full TikZ + pgfplots toolchain compiles on-device via WebAssembly — no network, no LaTeX install.

### A parabola with axes

```tikz
\begin{tikzpicture}
  \draw[->, thick] (-2.2,0) -- (2.2,0) node[right] {$x$};
  \draw[->, thick] (0,-0.5) -- (0,4.5) node[above] {$y$};
  \draw[domain=-2:2, smooth, thick, blue] plot (\x,{\x*\x});
  \node[blue, above right] at (1.4, 1.96) {$y = x^2$};
\end{tikzpicture}
```

### A triangle with labelled vertices

```tikz
\begin{tikzpicture}
  \coordinate[label=below left:$A$] (A) at (0,0);
  \coordinate[label=below right:$B$] (B) at (4,0);
  \coordinate[label=above:$C$] (C) at (1.5,3);
  \draw[thick] (A) -- (B) -- (C) -- cycle;
  \draw[dashed] (C) -- ($ (A)!(C)!(B) $) node[pos=0.5, right] {$h$};
\end{tikzpicture}
```

### A small commutative diagram

```tikz
\begin{tikzpicture}[node distance=2.2cm, every node/.style={font=\small}]
  \node (A) {$A$};
  \node (B) [right of=A] {$B$};
  \node (C) [below of=A] {$C$};
  \node (D) [right of=C] {$D$};
  \draw[->] (A) -- node[above] {$f$} (B);
  \draw[->] (A) -- node[left]  {$g$} (C);
  \draw[->] (B) -- node[right] {$h$} (D);
  \draw[->] (C) -- node[below] {$k$} (D);
\end{tikzpicture}
```

---

## JSXGraph — interactive geometry and plots

Use when you want the diagram to be **draggable** and **live**. Points move, sliders animate, curves reflow. Configuration is a small JSON object — no JavaScript required.

Each object takes a `type` (the JSXGraph element name) and `args` (the element's constructor arguments). Assign an `id` to reference an object from a later one using `"@id"` — useful for attaching points to curves, for example.

### Sine wave with a point on the curve

JSXGraph's `functiongraph` evaluates string expressions with its built-in **JessieCode** parser — so write `sin(x)`, `cos(x)`, `x^2`, `exp(x)`, etc. directly (no `Math.` prefix).

```jsxgraph
{
  "boundingbox": [-6.5, 1.6, 6.5, -1.6],
  "axis": true,
  "objects": [
    {
      "id": "curve",
      "type": "functiongraph",
      "args": ["sin(x)"],
      "attributes": { "strokeColor": "#6caedf", "strokeWidth": 2 }
    },
    {
      "type": "glider",
      "args": [1, 0, "@curve"],
      "attributes": {
        "name": "P",
        "size": 4,
        "strokeColor": "#d35e0c",
        "fillColor": "#d35e0c"
      }
    }
  ]
}
```

Drag `P` along the curve.

### Unit circle with a labelled point

```jsxgraph
{
  "boundingbox": [-1.6, 1.6, 1.6, -1.6],
  "axis": true,
  "width": 360,
  "height": 360,
  "objects": [
    {
      "type": "circle",
      "args": [[0, 0], 1],
      "attributes": { "strokeColor": "#945e80" }
    },
    {
      "type": "point",
      "args": [0.7, 0.7141],
      "attributes": {
        "name": "Q",
        "fillColor": "#6c782e",
        "strokeColor": "#6c782e"
      }
    }
  ]
}
```

### Two lines and their intersection

```jsxgraph
{
  "boundingbox": [-5, 5, 5, -5],
  "axis": true,
  "objects": [
    { "id": "A", "type": "point", "args": [-3, -2], "attributes": { "name": "A" } },
    { "id": "B", "type": "point", "args": [ 3,  2], "attributes": { "name": "B" } },
    { "id": "C", "type": "point", "args": [-3,  2], "attributes": { "name": "C" } },
    { "id": "D", "type": "point", "args": [ 3, -2], "attributes": { "name": "D" } },
    {
      "id": "L1",
      "type": "line",
      "args": ["@A", "@B"],
      "attributes": { "strokeColor": "#45707a" }
    },
    {
      "id": "L2",
      "type": "line",
      "args": ["@C", "@D"],
      "attributes": { "strokeColor": "#c14a4a" }
    },
    {
      "type": "intersection",
      "args": ["@L1", "@L2", 0],
      "attributes": { "name": "X", "size": 4, "fillColor": "#b47109" }
    }
  ]
}
```

Drag any of `A`–`D` and the intersection follows.

---

## function-plot — quick Cartesian plots

Smallest and simplest of the three. Give it functions, get a plot. Great for calculus-style notes and quick sanity checks.

The fence body is the options object passed to [function-plot](https://mauriciopoppe.github.io/function-plot/). Expression syntax is standard JavaScript math — `Math.PI`, `Math.sin(x)`, etc. — plus the `x^2` shorthand for powers.

### Several functions on one axis

```function-plot
{
  "yAxis": { "domain": [-1.5, 1.5] },
  "xAxis": { "domain": [-6.28, 6.28] },
  "grid": true,
  "data": [
    { "fn": "sin(x)",          "color": "#45707a" },
    { "fn": "cos(x)",          "color": "#c14a4a" },
    { "fn": "x / 3.14159265",  "color": "#6c782e" }
  ]
}
```

### A derivative annotation

Hover the curve — the tangent slope updates live.

```function-plot
{
  "yAxis": { "domain": [-2, 8] },
  "xAxis": { "domain": [-3, 3] },
  "grid": true,
  "data": [
    {
      "fn": "x^2",
      "derivative": { "fn": "2 * x", "updateOnMouseMove": true },
      "color": "#945e80"
    }
  ]
}
```

### A parametric curve

```function-plot
{
  "xAxis": { "domain": [-1.5, 1.5] },
  "yAxis": { "domain": [-1.5, 1.5] },
  "grid": true,
  "data": [
    {
      "graphType": "polyline",
      "fnType": "parametric",
      "x": "cos(t)",
      "y": "sin(t)",
      "range": [0, 6.283],
      "color": "#b47109"
    }
  ]
}
```

---

## When to reach for which

| You want…                                                        | Use                                         |
| ---------------------------------------------------------------- | ------------------------------------------- |
| Paper-grade static figure, TikZ muscle-memory, LaTeX portability | **TikZ**                                    |
| Interactive geometry, draggable points, geometry theorems        | **JSXGraph**                                |
| Quick plot of a few functions, minimal config                    | **function-plot**                           |
| Flow / sequence / state / gantt / ER diagram                     | **Mermaid** (see [[05 — Mermaid Diagrams]]) |
| Inline formulas, display equations                               | **KaTeX** (see [[04 — Math with KaTeX]])    |

#demo #math #diagrams #tikz #jsxgraph #function-plot
