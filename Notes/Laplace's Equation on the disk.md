---
tags:
  - FourierAnalysis
  - PartialDifferentialEquations
---
Links: [[Harmonic Functions]], [[2D Harmonic Functions]], [[The Heat Equation]]

We are looking for the solution of the steady-state heat equation $\nabla^2 u = 0$ in the unit disk in terms of polar coordinates. If we separate variables and remembering that $$\Delta u  = \frac{\partial^2 u}{\partial r^2} + \frac1{r}\frac{\partial u}{\partial r}+ \frac1{r^2}\frac{\partial^2 u}{\partial \theta^2} = 0$$
Then we can put everything related to $\theta$ and $r$ onto different sides, getting that $$r^2 \frac{\partial^2 u}{\partial r^2} + r\frac{\partial u}{\partial r} = - \frac{\partial^2 u}{\partial \theta^2}$$
Having the separation of variables as $u(r, \theta) = F(r)G(\theta)$, with the added restrain that $F \in \mathcal C([0,1])$ and $G$ being $2\pi$ periodic, getting that $$\frac{r^2 F''(r)+rF'(r)}{F(r)} = \lambda = -\frac{G''(\theta)}{G(\theta)}$$
With then we have the equations to solve $$\begin{align*}
 G''(\theta) +\lambda G(\theta) &= 0 \\
 r^2 F''(r) + rF'(r)-\lambda F(r) &=0
 \end{align*}$$
 With the restraint that $G$ is $2 \pi$ periodic, we have that $\lambda = m^2$ for some $m\in \Bbb Z$. Then we see that $G(\theta)$ is a linear combination of $e^{im\theta}$ and $e^{-im\theta}$.
 
Lastly, we need to solve $F$ for the different values of $\lambda$. If $m > 0$, then $F$ also has two solutions $r^m$ and $r^{-m}$. We can discard $r^{-m}$ since it is not continuous on the interval $[0, 1]$. Similarly for $m<0$, we discard the one with negative sign. Lastly for $m = 0$, we have the solutions $1$ and $\ln r$, but we discard $\ln r$ for similar reasons. Leaving us with $F(r) = r^{|m|}$. 

So the special solutions are of the form $$u_m(r, \theta) = a_m r^{|m|} e^{im\theta}$$
superimposing we get that $$u(r, \theta) = \sum_{n = -\infty}^\infty a_n r^{|n|}e^{in\theta}$$Lastly if we add the boundary condition that $u(1, \theta) = f(\theta)$. Setting $r= 1$, then we see that $\{a_n\}$ are the Fourier coefficients of $f$.

If $f$ is Riemann integrable, the coefficients $a_n$ are bounded, and since the factor $e^{-4 \pi ^2 n^2 t}$ tends to zero extremely fast, the series defining $u$ converges. In fact, $u$ is twice differentiable and solves the equation. 

Then we can write the solution as $$u(r,\theta) = (f*P_r)(\theta)$$where $P_r(\theta)$ is the [[Main definitions for Fourier Analysis|Poisson Kernel]]. 

**Th:** Let $f$ be an integrable function defined on the unit circle. The the function $u$ defined on the unit disk by the Poisson integral $$u(r, \theta) =(f*P_r)(\theta) $$
has the following properties 
- $u$ has two continuous derivatives in the unit disk and satisfies $$\nabla^2 u = 0$$- If $\theta$ is any point of continuity of $f$, then $$\lim_{r\to 1^-} u(r, \theta) = f(\theta) $$if $f$ is continuous, then this limit is uniform

This is the exact same result as we found out using [[2D Harmonic Functions#Poisson’s Formula|Complex Analysis]] 