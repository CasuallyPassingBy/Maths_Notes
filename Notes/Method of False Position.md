---
tags:
  - NumericalAnalysis
---
Links: [[Bisection Method]]

It is not a generally recomended method, but it serves to show a concept called _**************Root Bracketing,**************_ meaning that at each iteration we have that $a_n$ and $b_n$ that “bracket” the root $p$.

Then we want to modify slightly the Secant Method, we have that $p_n$, and $p_{n-1}$ bracket the root at every step of the approximation, basically merging bisection and the secant method. It has similar problems, to the Secant Method and Newton’s Method

### The Method of False Position Code

```julia
function false_position(f, a, b, tol=1e-6, max_iter=1000)
	# Check if f(a) and f(b) have opposite signs
	if f(a) * f(b) > 0
		error("Function has the same sign at both endpoints. False position method cannot proceed.")
	end
	
	# Initialize iteration counter and variables
	iter = 0
	x_prev = a
	x_current = b
	
	while iter < max_iter
		f_prev = f(x_prev)
		f_current = f(x_current)
		
		# Check for convergence
		if abs(f_current) < tol
			return x_current
		end
		
		# Check if the difference is close to zero
		if abs(x_current - x_prev) < tol
			println("Difference between approximations close to zero. False position method cannot proceed.")
			return x_current
		end
		
		# Update the approximation using the false position method
		x_next = x_current - f_current * (x_current - x_prev) / (f_current - f_prev)
		
		# Determine the new interval
		if f(x_next) * f(a) < 0
			b = x_next
		else
			a = x_next
		end
		
		# Update variables for the next iteration
		x_prev = x_current
		x_current = x_next
		
		iter += 1
	end
	
	println("Did not converge within the maximum iterations.")
	return x_current
end
```