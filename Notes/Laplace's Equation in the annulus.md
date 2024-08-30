---
tags:
  - PartialDifferentialEquations
  - FourierAnalysis
---
Links: [[Harmonic Functions]]

We can consider the Dirichlet problem in the annulus defined by $\{(r, \theta)\mid \rho < r<1\}$ where $0 < \rho <1$ is the inner radius. The problem is to solve $$\Delta u  = \frac{\partial^2 u}{\partial r^2} + \frac1{r}\frac{\partial u}{\partial r}+ \frac1{r^2}\frac{\partial^2 u}{\partial \theta^2} = 0$$subject to the boundary conditions $$\begin{cases}u(\rho, \theta) = g(\theta) \\
u(1, \theta) = f(\theta)\end{cases}$$where $f$ and $g$ are given continuous functions. 

Looking for the separation of variables we would get the system of equations $$\begin{align*}
 G''(\theta) +\lambda G(\theta) &= 0 \\
 r^2 F''(r) + rF'(r)-\lambda F(r) &=0
 \end{align*}$$with the restriction that $G$ is $2\pi$-periodic. 

We can do the exact same thing we did for [[Laplace's Equation on the disk|Laplace's Equation on the disk]], and we get the same solutions, and some others. 

Namely we have that the solutions for $G$ are of the form $$G(\theta) = e^{in\theta}$$ with $n \in \Bbb Z$. The solutions for $$F(r) = r^n$$with $n\in \Bbb Z^*$. In the case of the disk we rejected when $n < 0$, because it is not defined at $0$, as we needed that be at least continuous on the interval $[0, 1)$. Now this restriction no longer applies and we can have $n \in \Bbb Z^-$. Lastly we need to consider one last solution that had a similar problem, $\ln r$ that emerges as the multiple root of the [[Cauchy-Euler Differential Equation|indical polynomial]]. 

Now our solutions for $F$ look like $$F(r) = A_nr^n + B_nr^{-n}\qquad n \ne 0$$and $$F(r) = A_0 + B_0\ln r$$
With all of this we have that our solution can have the form of $$u(r, \theta) = \sum_{n \ne  0} (A_n r^n + B_n r^{-n})e^{in\theta} + A_0 + B_0 \ln r$$
To figure out the coefficients. We can use the Fourier series of $f$ and $g$: $$f(\theta) \sim\sum a_n e^{in\theta} \qquad \text{and} \qquad g(\theta) \sim \sum b_n e^{in\theta}$$
With this in mind we want that for $n\ne 0$, $$\begin{align*}
A_n + B_n &= a_n \\
A_n \rho^n + B_n \rho^{-n} &= b_n\end{align*}$$this two equations come from the boundary conditions. Solving the system of equations we get that $$\begin{align*} A_n &= \frac{b_n - a_n \rho^{-n}}{\rho^n - \rho^{-n}} \\
B_n & = \frac{a_n \rho^n - b_n}{\rho^n- \rho^{-n}}\end{align*}$$
Lastly we need the case where $n = 0$, then get the system $$\begin{align*}A_0 &= a_0 \\ A_0 + B_0\ln \rho &= b_n\end{align*}$$we only need to solve for $B_0$ getting that $$B_0 = \frac{b_0- a_0}{\ln r}$$
With all of this we now get out our solution to the Dirichlet problem being: $$u(r, \theta) = a_0 + (b_0-a_0) \frac{\ln r}{\ln \rho}+\sum_{n \ne  0} \left(\frac1{\rho^n- \rho^{-n}}\right)\left[\left(\left(\frac{r}{\rho}\right)^n - \left(\frac{\rho}{r}\right)^n\right)a_n + (r^n - r^{-n}) b_n\right] e^{in\theta} $$
We can show that we have $$u(r, \theta) - (P_r*f)(\theta) \to 0 \quad \text{as }r \to 1 \text{ uniformly in }\theta$$
and $$u(r, \theta) - (P_{\rho/r}*g)(\theta) \to 0 \quad \text{as }t \to \rho \text{ uniformly in }\theta$$
