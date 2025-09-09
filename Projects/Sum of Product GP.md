---
tags:
  - optimization
---
Product of Sum form can be used to present a wide variety of arithmetic equations. For given variables $\{x_1, \dots, x_n\}$. The product of sum notation as stated is:
$$
\prod_{k=1} \left(\sum_{i=1}^n (w_k,i \cdot x_k,i)^{w_k,n+1}\right)
$$
The above formation allows for the construction of a wide variety of equations. Through limiting the parameters $w_k,i$ to integers and $w_k, n+1 \in \{-1, 1\}$, it is possible to construct any mathematical equation. This could be used as an alternative to search GP for an equation as it reduces the search space. Due to the use of integers, it is also possible to simplify the equation once optimized.
## Algorithm Issues
##### Convergence Failure
Optimization takes really long / doesns't converage in most cases for each the most basic algorithm. This could be due to the use of varying decimal point values, which results in the slow convergence. *Similar to GP, limiting the selected values to integers can make the problem a discrete one.*

## TODO
- [ ] Implementation of the algorithm in accordance with the idea in [[#Convergence Failure]].
- [ ] 
