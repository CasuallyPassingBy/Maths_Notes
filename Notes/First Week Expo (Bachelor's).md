---
tags:
  - Topology
---
Links: [[Regular spaces]], [[Fréchet spaces]], [[Normal Spaces]]

**Def:** A family $\{A_s\}_{s\in S}$ of subsets of $X$ topological space is *locally finite* if for every point $x\in X$ there exists a neighbourhood $U$ such that $|\{s\in S\mid U \cap A_s \ne \varnothing\}|<\aleph_0$. If every point $x\in X$ has a neighbourhood that intersects at most one set of a given family, then we say that the family is *discrete*

**Def:** A family of subsets of a topological space is called $\sigma$-locally finite ($\sigma$-discrete) if it can be represented as a countable union of locally finite (discrete) families

**Th 4.4.1 (Stone):** Every open cover of a metrizable space has an open refinement which is both locally finite and $\sigma$-discrete

**Proof:** Let $\{U_s\}_{s\in S}$ be an open cover of $X$, where $X$ is metric with metric $\rho$. Since $S$ is a set, we an give it a well-order relation $<$. We want to create a countable set of families $\mathcal V_i$ that are discrete, and also a refinement. For that We need to define the following sets inductively, $$V_{s, i} = \bigcup B(c, 1/2^i)$$where $c\in X$, that need to follow some properties $$ s= \min \{t\in S\mid c\in U_t\}$$, that $$c \notin V_{t, j} \text{ when } j < i \text{ and } t\in S$$and $$B(c, 3/2^i) \subseteq U_s$$
We see that clearly $V_{s, i}$ are all open, and $V_{s, i} \subseteq U_s$. We now define $\mathcal V_i = \{V_{s, i}\}_{s\in S}$. We now define the set $$\mathcal V = \bigcup_{i = 1}^\infty \mathcal V_i$$. We see that $\mathcal V$ is an open refinement. We need to check that is indeed $\sigma$-discrete, but by out construction, we need see that each $\mathcal V_i$ is discrete. To see is to fix $i\in \Bbb N^+$. Let $x_1 \in V_{s_1, i}$ and $x_2 \in V_{s_2, i}$. Then we know there are points $c_1$ and $c_2$ such that $$x_1 \in B(c_1, 1/2^i)$$ and $$x_2 \in B(c_2, 1/2^i)$$
Since $s_1 < s_2$, then we see that $c_2 \notin V_{s_1, i}$, and by the third condition $B(c_1, 3/2^i) \subseteq V_{s_1, i}$. Then we get that $$\rho(c_1, c_2) \ge \frac3{2^i}$$
Then using the triangle inequality we get that $$\rho(c_1, c_2) \le \rho(c_1, x_1)+ \rho(x_1, x_2)+ \rho(x_2, c_2)$$which can be manipulated into $$\rho(x_1, x_2) \ge \rho(c_1, c_2)- \rho(x_1, c_1)-\rho(x_2, c_2) \ge \frac1{2^i}$$this proves that $\mathcal V_i$ is discrete. Meaning that $\mathcal V$ is $\sigma$-discrete.

Lastly we need to check is locally finite. 

Let $t\in S$ and $k, j \in \Bbb N^+$. The points $c$ of the definition of $V_{s, i}$, then $c\notin V_{t, j}$ when $i \ge j+k$ by the second condition of the $c$ points. If $B(x, 1/2^k)\subseteq V_{t, j}$, then $$\rho(x, c) \ge \frac1{2^k}$$
for every of the $c$ points of $V_{s, i}$. Since $j+k\ge k+1$ and $i \ge k+1$.
Suppose that $y\in B(x, 1/2^{j+k}) \cap B(c, 1/2^i)$, then $\rho(x, y) <1/2^{j+k}$ and $\rho(y, c)< 1/2^i$. Then $$
\begin{align*}\rho(x, c) &\le \rho(x, y) + \rho(y, c) \\
&< \frac1{2^{j+k}}+ \frac1{2^i} \\
&\le \frac1{2^{k+1}}+\frac1{2^{k+1}}= \frac1{2^k}\end{align*}$$
Meaning that $B(x, 1/2^{j+k}) \cap B(c, 1/2^i) = \varnothing$, meaning that the at most $B(x, 1/2^{j+k})$ meets at most $j+k-1$ members of $\mathcal V$

The proof of the Stone theorem gives a bit more: every open cover of a space $X$ whose topology is induced by a pseudo metric has an open refinement which is both locally finite and $\sigma$-discrete. $\square$

**Th 4.4.3:** Every metrizable space has a $\sigma$-discrete base.

**Proof:** The way we prove this is by considering the open covers $\mathcal U_i = \{B(x, 1/i) \subseteq  X \mid x \in X\}$, then we consider then $\sigma$-discrete open refinement $\mathcal B_i$ of $\mathcal U_i$. Then we consider the set $$\mathcal B = \bigcup_{i = 1}^\infty \mathcal B_i$$is a base $\square$ 

**Cor 4.4.4:** Every metrizable space has a $\sigma$-locally finite base. 

**Lemma 1.5.15:** If $X$ is a $T_1$ space and for every closed set $F\subseteq X$ and every open set $W\subseteq X$ that contains $F$ there exists a sequence $W_1, W_2, \dots$ of open subsets of $X$ such that $F\subseteq \bigcup_{i = 1}^\infty W_i$ and $\overline{W_i} \subseteq W$ for $i\in \Bbb N$, then the space $X$ is normal.

**Proof:** Let $A$ and $B$ be disjoints closed sets of $X$. Let's consider $F = A$ and $W= X\setminus B$, then we have a sequence of $W_1, W_2, \dots$ of open subsets of $X$ such that $$A \subseteq \bigcup_{i =1}^\infty W_i \quad \text{and}\quad \overline{W_i}\cap B = \varnothing \quad \text{for } i \in \Bbb N^+$$and $F = B$ and $W = X\setminus A$, then there's a sequence $V_1, V_2, \dots$ of open subsets of $X$ such that $$B \subseteq \bigcup_{i =1}^\infty V_i \quad \text{and}\quad \overline{V_i}\cap A = \varnothing \quad \text{for } i \in \Bbb N^+$$With these sequences, we can construct other sequences, let $$G_i = W_i \setminus \bigcup_{j \le i}\overline{V_j} \qquad \text{and}  \qquad H_i = V_i \setminus \bigcup_{j \le i}\overline{W_j}$$
We see that each $G_i$ and $H_i$ are open. With this we can now define our open sets: $$A \subseteq U = \bigcup_{i = 1}^\infty G_i \qquad B \subseteq V = \bigcup_{i = 1}^\infty H_i$$
Lastly, we need to see that $U$ and $V$ are disjoint. We see that $G_i \cap V_j = \varnothing$, when $j \le i$, then $G_i \cap H_j =\varnothing$ for  $j \le i$. Similarly, we get that $W_i \cap H_j = \varnothing$ when $i \le j$, then $G_i \cap H_j = \varnothing$ when $i \le j$. Getting that $G_i \cap H_j = \varnothing$ for $i, j \in \Bbb N^ +$. Thus $U \cap V = \varnothing$. $\square$

**Lemma 4.4.5:** Every regular space which has a $\sigma$-locally finite base is perfectly normal.

**Proof:** Let $\mathcal B = \bigcup_{i = 1}^\infty \mathcal B_i$ be a base, where $\mathcal B_i$ are locally finite, and $X$ is normal.  Let $W$ be a nonempty open subset, since it is nonempty we have that $x\in W$, there's a natural number $i(x)$ and an open set $U(x) \in \mathcal B_{i(x)}$ such that $x \in U(x) \subseteq \overline{U(x)} \subseteq W$. Letting $W_i = \bigcup \{U(x) \mid i(x) = i\}$, we obtain a sequence $W_1, W_2, \dots$ such that $\overline{W_i} \subseteq W$ and $W = \bigcup_{i = 1}^\infty W_i$. Then combined, gives us that $W = \bigcup_{i = 1}^\infty \overline {W_i}$. Added by the lemma 1.5.15, we get that $X$ is perfectly normal. $\square$

**Theorem 4.1.10:** For every set $A$ in a metric space $(X, \rho)$ assigning to each point $x\in X$ the distance $\rho(x, A)$ defines a continuous function on $X$. 

**Cor 4.1.11:** For every set $A$ in a metric $(X, \rho)$ we have that $$\overline A = \{x\in X \mid \rho(x, A) = 0\}$$
**Lemma 4.4.6:** Let $X$ be a $T_0$-space and $\{p_i\}_{i = 1}^\infty$ be a countable family of psuedometrics on the set $X$ which are all bounded by $1$ and satisfy the following conditions:
1. $\rho_i :X\times X \to \Bbb R$ is continuous functions for $i \in \Bbb N$
2. For every $x\in X$ and every non-empty closed set $A \subseteq X$ such that $x\notin A$ there exists an $i$ such that $\rho_i(x, A) = \inf\{\rho_i(x, a) \mid a \in A\} >0$
Then the space $X$ is metrizable and the function $\rho$ defined by $$\rho(x, y) = \sum_{i = 1}^\infty \frac1{2^i}\rho_i(x, y)$$is a metric on the space $X$. 
**Proof:** One readily sees that $\rho(x, x) = 0$ for every $x \in X$ and that $\rho$ satisfies the other conditions of the psuedometric. Since $X$ is a $T_0$ space, we have that either $y\notin \overline{\{x\}}$ or $x\notin\overline{\{y\}}$. By $(2.)$ we have that, $\rho(x, y) >0$. Meaning that $\rho$ is a metric on $X$.

We need to check that $\rho$ is a metric on the space $X$, then by Corollary 4.1.11, we only need to check that $$\rho(x, A) = 0 \iff x\in \overline A$$The first implication is fairly trivial, we use that $x\notin \overline A$. then there's an $i \in \Bbb N ^+$ such that $\rho_i(x, A)>0$, then get that $\rho(x, A)> 0$. 

Since $\rho$ converges uniformly, and every $\rho_i$ is continuous, then $\rho$ is continuous. Then, we have that the function $f(x) = \rho(x, A)$ is continuous (in particular Lipschitz continuous). If $x\in  \overline A$, then $f(x) \in f[\overline A]\subseteq \overline f[A] = \{0\}$, then getting that $\rho(x, A) = 0$. $\square$

**Lemma 1.5.13:** A subset $A$ of a normal space $X$ is an open $F_\sigma$-set iff there exists a continuous function $f:X \to I$ such that $A = f^{-1}[(0, 1]]$ 

**The Nagata-Smirnov Metrization Theorem 4.4.7:** A topological space is metrizable iff it is regular and has a $\sigma$-locally finite base.

**Proof:** The sufficient conditions follow from that metric spaces are regular, and one of the corollaries of the Stone theorem.
Since $X$ is regular and $\mathcal B = \bigcup_{i = 1}^\infty \mathcal B_i$ is a base, where $\mathcal B_i = \{U_s\}_{s\in S_i}$ are locally finite family, by one of the corollaries of the Stone theorem, we have that $X$ is perfectly normal. By the lemma beforehand, we know that there's a continuous function $f_s:X\to I$ such that $U_s= f^{-1}[(0, 1]]$.
We now define the family $\{W_s\}_{s\in S_i}$, where $W_s = (U_s \times X) \cup (X\times U_s)$, is locally finite in $X\times X$, and $|f_s(x)-f_s(y)| = 0$ if $(x, y) \notin W_s$. 
(We have the equivalence that a function $f:X\to Y$ is continuous iff for every point $x\in X$ has a neighbourhood $U$ such that $f|_U$ is continuous), then the function $$g_i(x, y) = \sum_{s\in S_i}|f_s(x)-f(y)|\qquad (x, y)\in X\times X$$with $g_i: X\times X \to \Bbb R$. For $i \in \Bbb N^+$, the formula $\rho_i(x, y) = \min\{1, g_i(x, y)\}$ defines a psuedometric on the set $X$ which is bounded by $1$. We would like to use the last lemma to prove for metrisability. 
The first condition being $\rho_i:X\times X\to \Bbb R$ is a continuous function for $i\in \Bbb N^+$, is trivial since $g_i$ is continuous. 
The second condition: for every $x\in X$, and every non-empty closed set $A\subseteq X$ such that $x\notin A$ there exists an $i$ such that $\rho_i(x, A) >0$.
To prove this, we can consider the set $U = X\setminus A$, since it's open, and $x\in U$, then there exists $i\in \Bbb N$, such that  $U_s\in \mathcal B_i$,  that $x\in U_s \subseteq U$, then $f_s(x) >0$, and $f_s[A] = \{0\}$. Then $$\rho_i (x, A) = \inf_{a\in A} \rho_i(x, a) \ge f_s(x) > 0$$
Metrisability follows from the lemma beforehand. $\square$

**Urysohn Metrization Theorem**: A second countable $T_3$ space is metrizable
**Proof:** A $T_3$ is regular, and since the base is countable, then $\mathcal B = \{B_i\}_{i = 1}^\infty$, then i can consider that $$ \mathcal B = \bigcup_{i = 1}^\infty \{B_i\}$$where each $\{B_i\}$ is locally finite. By Nagata-Smirnov is metrizable. $\square$

**Bing Metrization Theorem 4.4.8:** A topological space is metrizable iff it is regular and has a $\sigma$-discrete base

**Proof:** The sufficient conditions are immediate by one of Stone theorem's corollaries. Since, we have that has a $\sigma$-discrete base, then it implies that is $\sigma$-locally finite, thus metrizable. $\square$

**Def:** Let $\kappa$ be an infinite cardinal and $J_\alpha := (0, 1] \times \{\alpha\}$ for each $\alpha<\kappa$. Additionally $J(\kappa) := \{\langle 0, 0 \rangle\} \cup \bigcup_{\alpha<\kappa} J_\alpha$ and $d:J(\kappa) \to \Bbb R$, the function determined by $$d(\langle x, \alpha\rangle, \langle y, \beta\rangle) = \begin{cases}|x-y| & \alpha = \beta \\ x+y & \alpha \ne \beta\end{cases}$$
We have that $d$ is a metric on $J(\kappa)$. The resulting metric space is known as the *metrizable hedgehog of spininess $\kappa$*. This space has weight $\kappa$. 

**Lemma 4.1.12:** Every closed set of a metrizable space is functionally closed and, in particular, is a $G_\delta$-set

**Lemma 2.1.13:** If $\{F_s\}_{s\in S}$ is locally finite closed cover of a space $X$ and $\{f_s\}_{s\in S}$, where $f_s: F_s\to Y$, is family of compatible continuous mapping, then the combination $f = \bigcup_{s\in S} f_s$ is a continuous mapping o f $X$ to $Y$.

**Def:** A mapping $f:X \to Y$ is called a *homeomorphic embedding* if it's a composition of a homeomorphism and an embedding, i.e., if there exists a subspace $L$ of $Y$ and a homeomorphism $f': X\to L$ such that $f = \iota_L \circ f'$; clearly we have that $L =f [X]$ and $f' = f|_X$. If for $X$ there exists a homeomorphic embedding $f:X\to Y$ in a space $Y$, we say that $X$ is *embeddable in* $Y$.

**Lemma 2.3.19:** If the continuous mapping $f:X\to Y$ is a injective and the one-element family $\{f\}$ separates points and the closed sets, then $f$ is a homeomorphic embedding.
**Proof:** It suffices to show that for every closed $F\subseteq X$ we have $$f[F] = f[X] \cap \overline{f[F]}$$If $y = f(x) \in f[X] \setminus f[F]$, then $x\notin F$, and $y \notin \overline{f[F]}$. $\square$

**Diagonal Theorem 2.3.20:** If the family $\mathcal F = \{f_s\}_{s\in S}$ of the continuous mappings, where $f_s:X\to Y_s$, separates points, then the diagonal $f = \triangle_{s\in S} f_s=\prod_{s\in S} f_s : X\to \prod_{s\in S}Y_s$ is a injective mapping. If, moreover, the family $\mathcal F$ separates points and closed sets, then $f$ is an homeomorphic embedding. 
In particular, if there exists an $s\in S$ such that $f_s$ is a homeomorphic embedding then $f$ is a homeomorphic embedding

**Proof:** If the family $\mathcal F$ separates points, then for every pair of distinct points $x, y\in X$ there exists an $f_s\in \mathcal F$ such that $f_s(x) \ne f_s(y)$, so that $f(x) \ne f(y)$ which $f$ is injective.
If the family $\mathcal F$ separates points and closed sets, then the family $\{f\}$ also does, because if 
$f(x) \in \overline{f[F]}$ for an closed set $F\subseteq X$, then $f_s(x) = \pi_s(f(x))\in \pi_s[\overline{f[F]}]\subseteq \overline{\pi_s[f[F]]} = \overline{f_s[F]}$  for every $s\in S$. Then $f$ is a homeomorphic embedding by the lemma beforehand. $\square$

**Prop 1.1.15:** If $w(X) \le \kappa$ then for every base $\mathcal B$ for $X$ there exists a base $\mathcal B_0$ such that $|\mathcal B_0| \le \kappa$ and $\mathcal B_0 \subseteq \mathcal B$. 

**Kowalsky Theorem 4.4.9:** The Cartesian product $[J(\kappa)]^{\aleph_0}$ of $\aleph_0$ copies of the hedgehog $J(\kappa)$ is universal for all metrizable spaces of weight $\kappa \ge \aleph_0$. 

**Proof:** Clearly $[J(\kappa)]^{\aleph_0}$ is metrizable with weight $\kappa$, since it is the countable product of metrizable spaces is metrizable, and of weight $\kappa$. 

**Prop 1.1.11:** For every locally finite family $\{A_s\}_{s\in S}$ we have the equality $$\overline{\bigcup_{s\in S}A_s} = \bigcup_{s\in S}\overline{A_s}$$**Proof:** We have that in general, $\overline{A_s} \subseteq \overline{\bigcup\limits_{s\in S} A_s}$, then we have that $\bigcup\limits_{s\in S} \overline{A_s} \subseteq\overline{\bigcup\limits_{s\in S} A_s}$, for every $s\in S$. To prove the other inclusion takes into account the local finiteness. Let $x\in \overline{\bigcup\limits_{s\in S} A_s}$,, there exists a neighbourhood $U$ such that $S_0 = \{s\in S \mid U\cap A_s \ne \varnothing\}$ is finite. Then $x\notin \overline{\bigcup\limits_{s\in S\setminus S_0} A_s}$. Then $$x\in \overline{\bigcup\limits_{s\in S} A_s} = \overline{\bigcup\limits_{s\in S_0} A_s} \cup \overline{\bigcup\limits_{s\in S\setminus S_0} A_s}$$then $x\in \overline{\bigcup\limits_{s\in S_0} A_s} = \bigcup\limits_{s\in S_0} \overline{A_s}$, because $S_0$ is finite. Lastly, $x\in \bigcup\limits_{s\in S_0} \overline{A_s} \subseteq \bigcup\limits_{s\in S} \overline{A_s}$. $\square$ 

**Def:** A family $\{A_s\}_{s\in S}$ of subsets of $X$ is called *point-finite* (*point-countable*) if for every $x\in X$ the set $\{s\in S \mid x\in A_s\}$ is finite (countable). 

**Lemma 4.4.12:** If every cover of topological space $X$ has a locally finite closed refinement, then every open cover of $X$ has also a locally finite open refinement

**Proof:** Let $\mathcal U$ be an open cover of the space $X$. Then we take a locally finite refinement $\mathcal A =\{A_s\}_{s\in S}$. Since it is locally finite, and for every $x\in X$, then there's a neighbourhood $V_x$ such that only intersects a finite amount of elements of $\mathcal A$. 
Then we have the have the open cover $\{V_x\}_{x\in X}$, then we get the locally finite closed refinement $\mathcal F$. We want to consider for every $s\in S$, then $$W_s := X \setminus \bigcup\{F\in \mathcal F\mid F\cap A_s = \varnothing\} = \bigcap\{X\setminus F\mid F\in \mathcal F, F\cap A = \varnothing \}$$Since $\mathcal F$ is a locally finite, the the union of a locally finite of closed sets is closed, by the last proposition. We see that $W_s$ is open, and contains $A_s$, because $F\cap A_s = \varnothing$ iff $F \subseteq X\setminus A_s$ if we get $\bigcup\{F\in \mathcal F\mid F\cap A_s = \varnothing\} \subseteq X\setminus A_s$, iff $A_s \subseteq W_s$. 

One thing have that $W_s \cap F = \varnothing$ then $A_s \cap F = \varnothing$. Let $F_0\in \mathcal F$ and $F_0\cap A_s = \varnothing$, then $F_0 \in \{F\in \mathcal F \mid F \cap A_s = \varnothing\}$. This implies that $F_0 \subseteq \bigcup\{F\in \mathcal F \mid F\cap A_s = \varnothing\}$, $W_s = X\setminus \bigcup\{F\in \mathcal F\mid F\cap A_s = \varnothing \} \subseteq X\setminus F_0$, then $W_s\cap F_0 = \varnothing$. Meaning that $$W_s \cap F \ne \varnothing \iff A_s \cap F \ne \varnothing$$
For every $s\in S$ take $U(s) \in \mathcal U$ such that $A_s \subseteq U(s)$, and let $V_s = W_s \cap U(s)$. The family $\{V_s\}_{s\in S}$ is an open refinement of $\mathcal U$. Let $x\in X$, then there's a neighbourhood that only intersects a finite amount of elements in $\mathcal F$, and every member of $\mathcal F$ only intersects a finite number of elements in $\mathcal A$, from the the equivalence, only intersects a finite amount of $W_s$. Thus it is locally finite. $\square$

**Prop 1.5.18:** For every point-finite open cover $\{U_s\}_{s\in S}$ of a normal space $X$ there exists an open cover $\{V_s\}_{s\in S}$ of $X$ such that $\overline{V_s}\subseteq U_s$ for every $s\in S$.

**Th 1.4.12:** A continuous mapping $f:X\to Y$ is closed (open) iff for every $B\subseteq Y$ and every open (closed) set $A\subseteq X$ which contains $f^{-1}[B]$, there exists an open (a closed) set $C\subseteq Y$ containing $B$ such that $f^{-1}[C] \subseteq A$. 

**Proof:** Let $f:X\to Y$ is closed, $B$ is a subset of $Y$ and $A$ is an open subset of $X$ which contains $f^{-1}[B]$. The set $C = Y\setminus f[X\setminus A]$ is open in $Y$ and contains $B$. Moreover, $$f^{-1}[C] = X \setminus f^{-1}[f[X\setminus A]] \subseteq X\setminus (X\setminus A) = A$$
Let $f$ satisfies the other conditions. Let $F\subseteq X$ closed. The set $A=X\setminus F$ is open, and for $B = Y\setminus f[F]$ we have that $$f^{-1}[B] = X\setminus f^{-1}[f[F]] \subseteq X\setminus F = A$$Thus there's an open set $C$ such that $Y\setminus f[F] \subseteq C$ and $f^{-1}[C] \subseteq A$, $f^{-1}[C] \cap F = \varnothing$. This implies that $C \cap f[F] = \varnothing$, Meaning that $C\subseteq Y\setminus f[F]$. Getting that $f[F] = Y\setminus C$, and this shows that $f[F]$ is closed. $\square$

**Prop 1.4.13:** A continuous mapping $f:X\to Y$ is closed iff for every point $y\in Y$ and every open set $U\subseteq X$ which contains $f^{-1}[\{y\}]$, there exists in $Y$ a neighbourhood $V$ of the point $y$ such that $f^{-1}[V]\subseteq U$.

**Proof:** Let us take a set $B\subseteq Y$ and an open set $A\subseteq X$ such that $f^{-1}[B] \subseteq A$. For every $y\in B$ we can choose a neighbourhood $V_y\subseteq Y$ of the point $y$ such that $f^{-1}[V_y]\subseteq A$. The set $C = \bigcup_{y \in B} V_y$, then $B\subseteq C$ and $f^{-1}[C] \subseteq A$, thus $f$ is closed by 1.4.12 $\square$

**Lemma 3.10.11:** If $f:X\to Y$ is a perfect mapping, then for every locally finite family $\mathcal A$ of subsets of $X$, the family of images $\{f[A] \mid A\in \mathcal A\}$ is locally finite in $Y$.

**Proof:** From compactness of fibers of $f$ it follows that for every $y\in Y$ there exists an open set $U(y) \subseteq X$ that contains $f^{-1}[\{y\}]$ and meets only a finitely many members of $\mathcal A$. From the closedness of $f$ and 1.4.13 it follows that $y$ has a neighbourhood $V(y)$ such that $f^{-1}[V(y)] \subseteq U(y)$. The neighbourhood $V(y)$ meets only finitely many members of the family $\{f[A] \mid A \in \mathcal A\}$. 

**Lemma 4.4.13:** If there exists a perfect mapping $f:X\to Y$ of a metrizable space $X$ onto a space $Y$, then every open cover of the space $Y$ has an open locally finite refinement. (We can actually make it slightly looser conditions on $X$ since we only use the fact that $X$ is normal and every open cover has a locally finite refinement)

**Proof:** Let $\mathcal V$ be an open cover of $Y$. Using Stone theorem the open cover of $X$ $\{f^{-1}[V]\}_{V\in \mathcal V}$ has a locally finite finite $\{U_s\}_{s\in S}$. Using 1.5.18, there's a locally finite closed refinement $\mathcal F = \{F_s\}_{s\in S}$ of the space $X$ such that $F_s \subseteq U_s$ for every $s\in S$. Since $\mathcal F$ is locally finite, we can use lemma 3.10.11, then the family $\{f[F_s]\}_{s\in S}$ is a locally finite closed refinement of the cover $\mathcal V$ of $Y$. The lemma follows now from 4.4.12. $\square$

**Prop 1.5.20:** The class of $T_i$-spaces for $i\in\{1, 4\}$ and the class of perfectly normal spaces are invariant under closed mappings

**Proof:** The invariance of $T_1$-spaces follows from that fact $T_1$-spaces are characterised as spaces in which one-point subsets are closed.

Now, let $f:X\to Y$ be closed mapping of a normal space onto a space $Y$. Then $Y$ is a $T_1$-space. We consider the pair $U, V \subseteq Y$ such that $U\cup V = Y$. The sets $f^{-1}[U]$ and $f^{-1}[V]$ are open in $X$ and cover of the space $X$. By normality, we have that there are $A_0, B_0 \subseteq X$ such that $A_0 \subseteq f^{-1}[U]$, $B_0\subseteq f^{-1}[B_0]$ and $A_0 \cup B_0 = X$. The sets $A = f[A_0]$ and $B= f[B_0]$ are closed in $Y$. $A \subseteq f[f^{-1}[U]]=U$ and  $B \subseteq f[f^{-1}[V]] = V$, and $A\cup B =f[X] = Y$. Then $Y$ is a normal space. 

If $f:X\to Y$ is a closed mapping of a perfectly normal space, then $Y$ is normal and for every open set $U\subseteq Y$ we have that $f^{-1}[U] = \bigcup_{i = 1}^\infty  F_i$, where $F_i$ are closed sets in $X$. Hence $$f[U] = f[f^{-1}[U]] = f\left(\bigcup_{i = 1}^\infty F_i\right) = \bigcup_{i = 1}^\infty f[F_i]$$and is an $F_\sigma$ in $Y$, meaning that $Y$ is perfectly normal. $\square$

**Theorem 4.4.15:** Metrisability is invariant of perfect mapping

**Proof:** 

**Vaĭnšteĭn's Lemma 4.4.16:**