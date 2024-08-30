---
tags:
  - Statistics
---
Links: [[Evaluation of Point Estimators]], [[Convergence of Random Variables#Convergence in distribution|Convergence in distribution]], [[Unbiased Point Estimation]]

**Def:** Let a sequence of estimator $\{T_n\}$ is said to be *asymptotically efficient* for a parameter $\tau(\theta)$ if $$\sqrt n (T_n - \tau(\theta) ) \stackrel{d}{\longrightarrow} N(0, \text{CRLB}(\tau(\theta)))$$
This means, the asymptotic variance of $T_n$ becomes the CRLB

It can be proved that [[Maximum Likelihood estimators|maximum likelihood estimators]], that are [[Evaluation of Point Estimators#Consistency|Consistent]] and asymptotically efficient.

**Lemma:** If $\{X_n\}$ is a sequence of variables satisfy that $\sqrt n (X_n -\theta) \stackrel{d}{\longrightarrow} N(0, \sigma^2)$, then for a function and a specific value of $\theta$, we have that $$\sqrt n[\tau(X_n)-\tau(\theta)] \stackrel{d}{\longrightarrow} N\left(0, \sigma^2\left(\tau'(\theta)\right)^2\right) $$
**Th:** Let $X_1, \dots, X_n$ be a random sample of a population of a density function $f(x; \theta)$, let $\widehat {\theta}$  be the maximum likelihood estimator of $\theta$, and $\tau(\theta)$ be a continuous function and differentiable on $\theta$. Under the regularity conditions on $f(x;\theta)$ and, thus on the likelihood function $L(\theta)$, we have that $$\sqrt n[\tau(\hat \theta) - \tau(\theta)] \stackrel{d}{\longrightarrow} N(0, \text{CRLB}(\tau(\theta))) $$
where $\text{CRLB}(\tau(\theta))$ is the Cramér-Rao Lower Bound for estimators of $\tau(\theta)$. This means that the maximum likelihood of $\tau(\theta)$, $\tau(\hat \theta)$ is an efficient estimator of $\tau(\theta)$