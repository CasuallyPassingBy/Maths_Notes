---
tags:
  - FourierAnalysis
  - PartialDifferentialEquations
---
Links: [[Laplace's Equation in the upper half-plane]], [[Fourier Transform in Rn]]

We can write expressions involving $e^{-x}$ in terms of corresponding expressions involving $e^{-x^2}$. One form of this identity $$e^{-\beta} = \int_0^\infty \frac{e^{-u}}{\sqrt{\pi u}} e^{-\beta^2/4u}\, du$$
when $\beta \ge 0$. We prove this identity by considering $\beta = 2\pi |x|$ and taking the Fourier transform, and seeing they have the same transform. 

The upper half space is defined as $$\{(x, y) \in \Bbb R^n\times \Bbb R\mid y >0\}$$
We are considering the Dirichlet problem $$ \sum_{k = 1}^n \frac{\partial^2 u}{\partial x_k^2} + \frac{\partial^2 u}{\partial y^2} = 0$$with the boundary condition $u(x, 0) = f(x)$. A way to solve this problem is by applying the Fourier transform on $x$, and getting the ODE in $y$: $$\frac{\partial^2 \hat u}{\partial y^2}(\omega, y) -4\pi\|\omega\|^2 \hat u(\omega, y)=0$$
Then we solve the ODE in $y$ with $\omega$ fixed. Then are of the form $$\hat u(\omega, y) = A(\omega) e^{-2\pi \|\omega\|y }+ B(\omega) e^{2\pi \|\omega\|y}$$We can dismiss the part of the solution with a positive exponent, due to its rapid increase. Then the solution would be of the form $$\hat u(\omega, y) = A(\omega) e^{-2\pi \|\omega\|y }$$
Applying our boundary conditions we get that $$\hat u(\omega, y) = \hat f(\omega) e^{-2\pi \|\omega\|y }$$
We can define the $n$-dimensional *Poisson kernel*, as $$P_y ^{(n)}(x)= \int_{\Bbb R^n} e^{-2\pi \|\omega\| y} e^{2\pi i x\cdot \omega}\, d\omega $$Then we can calculate this integral using the $n$[[The Heat Equation on Euclidean space|-dimensional heat kernel]]. We can show that $$P_y^{(n)}(x) = \frac{\Gamma((d+1)/2)}{\pi^{(d+1)/2}} \frac{y}{(\|x\|^2+y^2)^{(d+1)/2}}$$