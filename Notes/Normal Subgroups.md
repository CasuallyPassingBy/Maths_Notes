---
tags:
  - GroupTheory
---
Links: [[Groups]], [[Subgroups]], [[Integers modulo n]], [[Equivalence Relations and Partitions]]

# Cosets

We want to have an analogue to the idea of having integers to general groups and subgroups. Let $G$ be group and $H\le G$. Then we can define the equivalence relations $x\equiv_H y$ iff $xy^{-1} \in H$, and $x \:_H \equiv y$ iff $x^{-1}y \in H$ 

**Def:** If $H \le G$, then by the *left coset of $H$ in $G$* we mean a subset of $G$ of the form $aH$, where $a\in G$ and $aH = \{ah \mid h\in H\}$, and the *right coset of $H$ in $G$*, we mean a subset of $G$ of the form $Ha$, defined as $Ha = \{ha \mid h\in H\}$. 

**Th:** Let $H\le G$. For $g\equiv_H a$ iff $g\in Ha$, and $g\;_H \equiv a$ iff $aH$ 

**Cor:** Let $H\le G$, and let $a, b\in G$. Then $Ha = Hb$ iff $ab^{-1}\in H$, and $aH = bH$ iff $b^{-1}a\in H$

# Normal Subgroups
