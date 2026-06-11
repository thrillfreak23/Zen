# Math with KaTeX

ZenNotes renders LaTeX math via KaTeX. The source stays plain markdown while preview and split mode give you readable math output.

## A fast way to insert math

Type `/` and choose **Math block** when you want display math without typing the fence from memory.

## Inline math

Euler's identity is $e^{i\pi} + 1 = 0$.  
The area of a circle is $A = \pi r^2$.  
A quadratic has roots $x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a}$.

## Display blocks

$$
\int_{-\infty}^{\infty} e^{-x^2}\, dx = \sqrt{\pi}
$$

$$
\frac{\partial}{\partial t} \Psi(x, t) = -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} \Psi(x, t) + V(x)\Psi(x, t)
$$

## Aligned equations

$$
\begin{aligned}
(a + b)^2 &= a^2 + 2ab + b^2 \\
(a - b)^2 &= a^2 - 2ab + b^2 \\
a^2 - b^2 &= (a + b)(a - b)
\end{aligned}
$$

## Matrices

$$
\mathbf{A} =
\begin{bmatrix}
  1 & 2 & 3 \\
  4 & 5 & 6 \\
  7 & 8 & 9
\end{bmatrix}
\qquad
\det(\mathbf{A}) = 0
$$

## Summations, limits, derivatives

$$
\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}
\qquad
\lim_{x \to 0} \frac{\sin x}{x} = 1
\qquad
\frac{d}{dx} \ln x = \frac{1}{x}
$$

## Probability and finance

$$
P(A \mid B) = \frac{P(B \mid A) P(A)}{P(B)}
$$

$$
C = S_0 \Phi(d_1) - K e^{-rT} \Phi(d_2)
$$

$$
d_1 = \frac{\ln(S_0 / K) + (r + \tfrac{1}{2}\sigma^2) T}{\sigma \sqrt{T}}, \qquad d_2 = d_1 - \sigma \sqrt{T}
$$

## Why this matters in ZenNotes

- **Edit** mode keeps the raw LaTeX visible.
- **Split** mode is great when you want source and rendered math side by side.
- **Preview** mode turns math-heavy notes into something closer to a paper or spec.
- Vault text search still sees the underlying source, which makes formulas searchable as text.

## What's next

When the note needs geometry, plotted functions, or figure-quality diagrams rather than equation layout, jump to [[05b — Math Diagrams]].

#demo #math #reference
