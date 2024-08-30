---
tags:
  - GroupTheory
---
Links: [[Functions]], [[Groups]], [[Subgroups]]

**Def:** If $X$ is a nonempty set, then a bijective map from $X$ to $X$ is called a *permutation* of $X$. Meaning that $f\in \text{Sym}(X)$ is a permutation, where $\text{Sym}(X)$ represents the set of all bijective maps from $X$ to $X$. 

From the definitions of bijective functions we see that:
- $\text{Id}_X$ behaves like an identity under $\circ$
- $\circ$ is associative
- every $f\in \text{Sym}(X)$ has an inverse

**Prop:** $(S_X, \circ)$ is a group

**Def:** $(S_X, \circ)$ is called the *symmetric group on* $X$. If $X$ is a finite set, $|X| = n$, then we just write $S_n$ instead of $S_X$, and is called the *symmetric group of order* $n$, and it has order $n!$. 

Let $f\in S_n$. Then we can represent $f$ as $$\begin{pmatrix}1 &2 &  3 & \cdots& n \\
f(1) &f(2) &  f(3) & \cdots& f(n)\end{pmatrix}$$where $f(k)$ is placed under $k$ for each between $1$ and $n$.

Let $x_1, x_2, \dots, x_r$, $1\le r\le n$, be $r$ distinct elements of $\{1, 2, \dots, n\}$. The $r$*-cycle* $(x_1, x_2, \dots, x_r)$ is the element of $S_n$ that maps $x_1\to x_2\to x_3 \to \cdots \to x_r \to x_1$, and leaves all elements of $\{1, 2, \dots, n\}$ other than $x_1, x_2, \dots, x_r$ fixed. A $2$-cycle, is called a *transposition*. 

Two cycles $(x_1, x_2, \dots, x_r)$ and $(y_1, y_2, \dots, y_s)$ in $S_n$ are called *disjoint*, with $s, r\ge 2$, if $$\{x_1, x_2, \dots, x_r\} \cap \{y_1, y_2, \dots, y_s\} = \varnothing$$
We can also see that disjoint cycles commute

**Def:** Let $\sigma \in S_n$ be permutation. for an element $x \in \{1, \dots, n\}$ the set $$\mathcal O_\sigma(x) := \{\sigma^k(x) \mid k \in \Bbb Z\}$$is called the *orbit of $x$ under $\sigma$.*

**Prop:** Let $\sigma \in S_n$ a permutation. Then:
- $x \in \mathcal O_\sigma(x)$, therefore the orbits are nonempty
- The orbits are disjoint, meaning that if $\mathcal O_\sigma(x) \cap\mathcal O_\sigma(z) \ne \varnothing$, then $\mathcal O_\sigma(x) = \mathcal O_\sigma(z)$
- The union of orbits is $\{1, \dots, n\}$

**Prop:** If $\sigma \in S_n$ and $x\in \{1, \dots, n\}$, then the restriction $\sigma|_{\mathcal O_\sigma(x)}$ is a cycle of the length of the cardinality of $\mathcal O_\sigma(x)$



**Th:** Let $\sigma \in S_n$. Then there exists disjoint cycles $\sigma_1 \sigma_2, \dots, \sigma_m$ in $S_n$ such that $\sigma = \sigma_1 \circ \sigma_2 \circ \cdots \circ\sigma_m$

**Th:** If $n \ge 2$, then any cycle in $S_n$ can be written as a product of transpositions, and it is given by $$(x_1, x_2, \dots, x_r) = (x_1, x_r) \circ (x_1, x_{r-1}) \circ \cdots \circ (x_1, x_3) \circ (x_1, x_2)$$
**Cor:** If $n \ge 2$, the any element of $S_n$ can be written as a product of transpositions

**Def:** A permutation is *even* if it can be written as a product of an even number of transpositions. It is *odd* if it can be written as the product of an odd number of transpositions. 

**Th:** No permutation is both even and odd

**Def:** With this we can define the *sign* of a permutation $\sigma \in S_n$ that can be expressed as $\sigma = \tau_1 \circ \cdots \circ \tau_r$ as a product of transpositions, as $\text{sgn}(\sigma) = (-1)^r$ since a permutation cannot be odd and even then the function is well defined. 

**Def:** Let $A_n = \{\sigma \in S_n \mid \text{sgn}(\sigma) = 1\}$.