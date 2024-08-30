---
tags:
  - PartialDifferentialEquations
  - FourierAnalysis
---
Links: [[Fourier Transform in R]]

We consider the equation $$\Delta u  = \frac{\partial^2 u}{\partial x^2} +\frac{\partial^2 u}{\partial y^2} = 0$$ in the horizontal strip $$\{(x, y) \mid 0 < y <1, x \in \Bbb R\}$$with boundary conditions $u(x, 0) = f_0(x)$ and $u(x, 1) = f_1(x)$, where $f_0$ and $f_1$ are both int the Schwartz space. 

We can use the Fourier transform on $x$, and we get the ode: $$-4\pi^2\omega^2 \hat u(\omega, y) + \frac{\partial^2 \hat u}{\partial y^2}(\omega, y) = 0$$ if we fix $\omega$, then we can solve this differential equation, and we get the general form of $$\hat u(\omega, y) = A(\omega) e^{2\pi \omega y} + B(\omega) e^{-2\pi \omega y}$$Then we can express $A$ and $B$ in terms of $\widehat{f_0}$ and $\widehat{f_1}$,  and get that $$\hat u (\omega, y) = \widehat{f_0}(\omega) \frac{\sinh(2\pi (1-y) \omega)}{\sinh(2\pi \omega)} + \widehat{f_1}(\omega) \frac{\sinh(2\pi y \omega)}{\sinh(2\pi \omega)}$$We have that $$\int_{-\infty}^\infty |u(x, y) - f_0(x)|^2\, dx  \to 0 \quad \text{as } y\to 0$$and$$\int_{-\infty}^\infty |u(x, y) - f_1(x)|^2\, dx  \to 0 \quad \text{as } y\to 1$$
The biggest hurdle right now is to calculate the Fourier transform of the function $$\Phi(\omega) = \frac{\sinh(2\pi \omega a)}{\sinh(2\pi \omega)}$$with $0 \le a <1$. 

The main problem, now is to find the this inverse Fourier transform, we can consider the function $$\varphi(x) = \frac{\sin \pi a}{2} \frac1{\cosh \pi x + \cos \pi a}$$
Then take it's Fourier transform. The way to calculate its Fourier transform is by, using the [[Residue Theorem]], and doing a contour integral on the rectangle with vertices at $R, R+2i, -R+2i, -R$. 

With this result we get that, we can express the solution to be $$u(x, y) = \frac{\sin \pi y}{2}\left(\int_{-\infty}^\infty \frac{f_0(x-t)}{\cosh\pi t- \cos \pi y}\, dt + \int_{-\infty}^\infty \frac{f_1(x-t)}{\cosh\pi t+ \cos \pi y}\, dt\right)$$
Finally we can check that the function $u(x, y)$ by the expression above is harmonic on the strip, and converges uniformly to $f_0(x)$ as $y\to 0$ and to $f_1(x)$ as $y\to 1$. Moreover $u(x, y)$ vanishes at infinity, that is $$\lim_{|x| \to \infty} u(x,y) = 0 \qquad \text{uniformly on } y$$