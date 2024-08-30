---
tags:
  - PartialDifferentialEquations
---
Links: [[Harmonic Functions]]

The general heat equation is of the form: $$\frac{\partial u}{\partial t} = \Delta u $$

We can consider the an analogue to the maximum principle for harmonic functions.

Suppose that $u(x, t)$ is a real-valued solution to the [[The Heat Equation on the Real line]], which is continuous on its closure. Let $R$ denote the rectangle $$R = [a,b] \times [0, c]$$and $\partial' R$ as $$\partial'R= [a, b]\times\{0\} \cup \{a, b\} \times [0, c]$$
meaning that is part of the boundary of $R$, except for the top part. Then $$\min_{(x, t)\in \partial'R}u(x, t) = \min_{(x, t)\in R}u(x, t)$$and $$\max_{(x, t)\in \partial'R}u(x, t) = \max_{(x, t)\in R}u(x, t)$$
This can be generalised to get that with $\Omega$ be a bounded region, and $u$ be a solution of the heat equation on $R= \Omega\times [0, c]$. Then the special boundary is $$\partial' R = \Omega \times\{0\} \cup \partial \Omega \times [0, c]$$Then $$\min_{(x, t)\in \partial'R}u(x, t) = \min_{(x, t)\in R}u(x, t)$$and $$\max_{(x, t)\in \partial'R}u(x, t) = \max_{(x, t)\in R}u(x, t)$$

There are a lot of solutions: 
- [[The Heat Equation on Euclidean space]]
	- [[The Heat Equation on the Real line]]
- [[The Heat Equation on the Circle]]
- [[A Variant of the Heat Equation on the First Quadrant]]
