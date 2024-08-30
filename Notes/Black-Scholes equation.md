---
tags:
  - PartialDifferentialEquations
---
Links: [[The Heat Equation]]

The *Black-Scholes equation* from finance theory is $$\frac{\partial V}{\partial t}+ rs\frac{\partial V}{\partial s} + \frac{\sigma^2 s^2}{2} \frac{\partial^2 V}{\partial s^2} - rV = 0 \qquad 0 < t<T$$subject to the *final* boundary condition $V(s, T) = F(s)$. 

We can multiply the equation by $e^{-rt}$, and define $V_1 = e^{-rt}V$. Then the equation becomes $$\frac{\partial V_1}{\partial t}+ rs\frac{\partial V_1}{\partial s} + \frac{\sigma^2 s^2}{2} \frac{\partial^2 V_1}{\partial s^2} = 0$$
Let $t_1 = -(\sigma^2/2)t$. Then $\dfrac{\partial V_1}{\partial t} = \dfrac{\partial V_1}{\partial t_1} (-\sigma^2/2)$, and upon dividing by $-\sigma^2/2$ on both sides we get $$\frac{\partial V_1}{\partial t_1}= \frac{2r}{\sigma^2}s\frac{\partial V_1}{\partial s} + s^2\frac{\partial^2 V_1}{\partial s^2}$$
Then we can solve this using the same method as we did for [[A Variant of the Heat Equation on the First Quadrant|a variant of the heat equation]]

An alternative way is to consider the change of variables and the substitution $V(s,t) = e^{ax+b\tau} = U(x, \tau)$, with $x = \ln s$, $\tau = \frac{\sigma^2}{2} (T-t)$, $a = \frac1{2} - \frac{r}{\sigma^2}$, and $b = -\left(\frac1{2}+ \frac{r}{\sigma^2}\right)^2$. Then this gets us that $$\frac{\partial U}{\partial \tau} = \frac{\partial^2 U}{\partial x^2}$$with an initial condition of the form $U(x, 0) = e^{-ax}F(e^x)$. We can solve the this equation getting $$U(x, \tau) = \frac1{\sqrt{4\pi \tau}}\int_{-\infty}^\infty e^{-ay}F(e^{y}) \exp\left(\frac{(x-y)^2}{4\tau}\right) \, dy$$
Doing all the substitutions back we get that the solution is $$V(s, t) = \frac{e^{-r(T-t)}}{\sqrt{2\pi \sigma^2(T-t)}} \int_0^\infty F(s^*) \exp\left(-\frac{(\ln(s/s^*)+(r-\sigma^2/2)(T-t))^2}{2\sigma^2(T-t)}\right)\, ds^*$$