---
tags:
  - PartialDifferentialEquations
---
Links: [[Harmonic Functions]], [[Convergence of Fourier Series]]

We have Laplace's equation on $2$-dimension: $$\Delta u  = 0$$in the semi infinite strip $$S = \{(x, y)\mid 0<x < 1, 0<y\}$$subject to the following boundary conditions: $$\begin{cases}
u(0, y) = 0 & 0 \le y \\
u(1, y) = 0 & 0 \le y \\
u(x, 0) = f(x) & 0 \le x \le 1
\end{cases}$$
where $f$ is a given function, with of course $f(0) = f(1) = 0$. $$f(x) = \sum_{n = 1}^\infty a_n \sin(n \pi x)$$ We can see that $$u_n (x, y) = e^{-n\pi y}\sin (n\pi x)$$
Then we can express $$u(x, y) = \sum_{n = 1}^\infty a_n e^{-n\pi y}\sin(n\pi x)$$
We can consider the odd extension of $f$ and following the derivation of the [[Main definitions for Fourier Analysis|Poisson kernel]] with $e^{\pi y}$ and $e^{i \pi t}$ replacing $r$ and $e^{it}$, respectively, we obtain $$u(x, y) = \frac1{2} \int_{-1}^1 f(t) Q_y(x-t)\, dt $$where $$Q_y(t) = \frac{1-e^{2\pi y}}{1-e^{-\pi y}\cos\pi t+ e^{-2\pi y}}$$
Which gives us that $$u = (f* Q_y)(x)$$
