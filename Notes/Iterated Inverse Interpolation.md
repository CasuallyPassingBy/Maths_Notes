---
tags:
  - NumericalAnalysis
---
Suppose $f\in {\cal C}^1[a, b]$, and $f'(x) \ne 0$ for all $x\in (a,b)$ and $f$ has a zero at $p\in [a,b]$. Let $x_0, \dots, x_n \in [a, b]$ be $n+1$ distinct points, with $f(x_k) = y_k$ for each $k \in {0, \dots, n}$. To approximate $p$, we can construct an interpolating polynomial of degree $n$ on the nodes $y_0, \dots, y_n$ for $f^{-1}$. Then we need to interpolate $f^{-1}(0)$, with the points we got, this is an iterated inverse interpolation

This can be done with [[Neville's Method]] 

This is a link between [[Interpolation and Polynomial Approximation]], and [[Solutions of Equations of One Variable]]

The algorithm using Nevilles's method is of the form:
```julia
function iterated_inverse_interpolation(x_values, y_values; target_y = 0)
    n = length(x_values)
    Q = similar(x_values, Float64) # Initialize the first column of the table with y-values

    for j in 2:n

        for i in 1:n-j+1

            Q[i] = ((target_y - y_values[i]) * Q[i+1] - (target_y - y_values[i+j-1]) * Q[i]) / (y_values[i+j-1] - y_values[i])

        end

    end

    return Q[1] # The interpolated value is in the top-right corner of the table

end
```
