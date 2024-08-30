---
tags:
  - GroupTheory
---
Links: [[Groups]], [[Subgroups]], [[Normal Subgroups#Cosets|Cosets]]

**Lemma:** Let $G$ be any group and let $H\le G$. Then $|Ha| = |Hb|$, and $|aH| = |bH|$. 

**Lagrange's Theorem:** Let $G$ be a finite group and let $H \le G$, then $|H| \mid |G|$.  

If $G$ is any group and $H\le G$, then the number of distinct right cosets of $H$ in $G$ is called the *index* of $H$ in $G$ denoted as a $[G:H]$. Thus the Lagrange's theorem, tells us that if $G$ is finite, then $$|G| = [G:H] |H|$$
**Th:** Let $H\le G$, then the number of left cosets of $H$ in $G$ is $[G:H]$. 

**Th:** Let $G$ be finite group and let $x\in G$. Then $o(x) \mid |G|$, as a corollary $x^{|G|} = e$ for every $x\in G$.

**Th:** Let $G$ be a group and assume $|G|$ is a prime. Then $G$ is cyclic. Moreover, any element of $G$ other than $e$ is a generator for $G$.

**Def:** Let $G$ be a group. We say that $a, b\in G$, $a$ is conjugate to $b$ iff there exists some $x\in G$ such that $a = xbx^{-1}$

**Lemma:** Being conjugate is an equivalence relation on $G$.

The equivalence class of an element $a\in G$ under the conjugate relation of $a$ is called the *conjugacy class* of $a$, and consistes of all conjugates of $a$. That is $\{xax^{-1}\mid x\in G\}$ 

**Lemma:** Let $G$ be a finite group and let $a\in G$. Then the number of distinct conjugates of $a$ in $G$ is $[G:Z(a)]$

**Class Equation:** Let $G$ be a finite group, and let $\mathcal C = \{a_1, \dots, a_k\}$ consiste of one element from each conjugacy class containing at least two elements. Then $$|G| = |Z(G)| + \sum_{a \in \mathcal C} [G:Z(a)]$$
