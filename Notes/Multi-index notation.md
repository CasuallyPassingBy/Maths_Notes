---
tags:
  - SpecialNotations
---
An $n$-dimensional multi-index is an $n$-tuple
$$
\alpha =(\alpha_1, \alpha_2, \dots, \alpha_n)
$$
of nonnegative integers, or $\alpha \in \Bbb N^n$. 
For multi-indeces $\alpha, \beta \in \Bbb N^n$ and and $x = (x_1, x_2, \dots, x_n)\in\Bbb R^n$ we define: 

###### Componentwise sum and difference
$$
\alpha \pm \beta = (\alpha_1 \pm \beta_1, \alpha_2 \pm \beta_2, \dots, \alpha_n \pm \beta_n)
$$
###### Partial Order
$$
\alpha \le \beta \iff\alpha _i \le \beta_i \quad
\forall i \in \{1, \dots, n\} 
$$
###### Sum of components (absolute value)
$$
|\alpha| = \sum_{i = 1}^n \alpha_i
$$
###### Factorial
$$
\alpha! = \prod_{i = 1}^n \alpha_i !
$$
###### Binomial coefficient
$$
{\alpha \choose \beta} = \prod_{i = 1}^n {\alpha_i \choose \beta_i} = \frac{\alpha!}{\beta!(\alpha-\beta)!}
$$
###### Multinomial coefficient
$$
{k \choose \alpha } = \frac{k!}{\alpha _1!\alpha _2!\cdots \alpha _n!} = \frac{k!}{\alpha !}
$$
where $k = |\alpha | \in \Bbb N$
###### Power
$$
x^ \alpha = \prod_{i = 1}^n x_i^{\alpha _i} 
$$
###### Higher-order partial derivatives
$$
\partial^\alpha = \partial_1^{\alpha _1} \partial_2^{\alpha _2}\cdots \partial_n^{\alpha_n }
$$
where $\partial_i^{\alpha_i} = \partial^{\alpha_i}/\partial x^{\alpha_i}$. Sometimes the notation $D^\alpha =\partial^\alpha$.
