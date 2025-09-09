A fuzzy set $A$ in $X$ is characterized by a membership (characteristic) function $f_A(x)$ which associates with each point in $X$ to a real number in the interval $[0, 1]^2$ with the value of $f_A(x)$ at $x$ representing the "grade of membership" of $x$ in $A$. Thus the nearer the value of $f_A(x)$ to unity, the higher the grade of membership of $x$ in $A$.
> A function $f$ rather than being binary defines the level of membership in a set. The function $f_A$ maps $f_A: X \to [0, 1]$. In a binary set, the characteristic function is defined as $f_A: X -> \{0, 1\}$.

Fuzzy set membership notation can be written as follows for a set $X = [0 \dots 10]$ (level of membership over the number):
$$
A = [0 / 0, 0 / 1 , 0.2 / 2, \dots]
$$
Membership into a fuzzy set can be used for approximations and such where the exact value might not be known so the entire range needs to be taken into consideration but not considered fully part of the set (examples include scientific error).
## Classes of Membership Functions
- **Triangular membership function**: A range of values where the function is increasing until a peak ($1$) and then it drops back down to $0$.
- **Trapezoidal membership function**: A selected range has inclusion ($f_A(x) = 1$) rather that a single point at the peak like a triangular membership function.
- **$\Gamma$-membership function**: A smooth non-linear increase (*sort of like a sigmoid function*).
- **S-membership function**: Similar to $\Gamma$ membership function.
- **Gaussian membership function**: A bell curve.
- **Exponential-like membership function**: It is similar to the gaussian membership function but has a different mathematical formulation.
- **Piecewise-linear membership function**: Consists of a piecewise function with linear sections. This is a broader view of the triangular and the trapezoidal membership functions.
### Normal Fuzzy Set
At least one element in the fuzzy set belongs to the set ($f_A(x) = 1$). The height of a fuzzy set $\text{hgt}$ is defined as:
$$
\text{hgt}(f_A) = \sup_{x \in X} f_A(x)
$$
$\sup$ refers to the supremum, the least upper bound of a set of numbers or the range of the function. A normal fuzzy set has the following rule:
$$
\text{hgt}(f_A) = 1
$$
If $f_A$ is not normal, then it can be transformed into a normal fuzzy set through normalization:
$$
\frac{f_A(x)}{\text{hgt}(f_A)}
$$
### Support and Core
The **support** is the set of values that have a non-zero membership value in the fuzzy set ($f_A(x) > 0$).
The **core** of a fuzzy set is the set of values that are included in the fuzzy set ($f_A(x) = 1$).
### Equality and Inclusion
Given two sets $A, B$ that are fuzzy sets.
- **Equality** is defined by: $A = B$ if $A(x) = B(x)$ for all $x \in X$
- **Inclusion** is defined by: $A \subset B$ if $A(x) \leq B(x)$ for all $x \in X$
### $\alpha$-cuts of fuzzy sets
An extension of the support of a fuzzy set where rather than including all elements that are even remotely possible to be in the set, set an $\alpha$ that defines the minimum requirement for the element to be part of the $\alpha$-cut set.
$$
A_\alpha = \{x \in X | A(x) \geq \alpha\}
$$
$$
A_\alpha = \{x \in X | A(x) > \alpha\}
$$
The second measure is called a strong $\alpha$-cut and is not widely used in literature. $\alpha = 1$ is the core of the fuzzy set in the weaker $\alpha$ cut but an empty set in the stronger measure.
## Energy Measure
Define a function $e$ such that:
- $[0, 1] \to [0, 1]$
- $e(0) = 0$
- $e(1) = 1$
- It is monotonically increasing (can do up or stay the same only).

> This allows for integration (only in continuous $X$) and other fun stuff. A large increase for a fuzzy set that grows abnormally, and grows small for little to no increases.

$$
E(f_A) = \sum_{i = 1}^n e[f_A(x_i)]
$$
$$
E(f_A) = \int_X e[f_A(x)]\ dx
$$
$E$ is usually referred to as the **cardinality** of the fuzzy set.
## Entropy Measure
Measures the amount of fuzziness (uncertainty) in a fuzzy set. The most uncertainty occurs at $f_A(x) = 0.5$. A similar thing applies for discrete sets but using the $\Sigma$ instead.
$$
H(f_A) = \int_X h[f_A(x)] \ dx
$$
Where $H(f_A)$ satisfies the following:
- $h(0) = 0, h(1) = 1, h(0.5) = 1$
## Geometric Representation of Sets
Sets can be plotted such that each axis represents the membership value of the set with the axis being bound to $[0, 1]$. Through this manner, a universe $X$ such that $|X| = 10$ would be a 10-dimensional plot with the set's location being on the plot at the associated fuzziness values of each of the members on the set. A fuzzy set with the highest possible entropy measure will be located in the center of the plot (with the restrictions on the range).
## Representation Theorem
A fuzzy set $A$ can be represented by a family of $\alpha$-cut sets.

Given a set $A = [1, 0.3, 0.7, 0.5]$, then the following alpha cuts:
$$
\begin{matrix}
\alpha = 1 & A_1 = [1, 0, 0, 0] \\
\alpha = 0.3 & A_{0.3} = [1, 1, 1, 1] \\
\alpha = 0.7 & A_{0.7} = [1, 0, 1, 0] \\
\alpha = 0.5 & A_{0.5} = [1, 0, 1, 1] \\
\end{matrix}
$$
From the set of $\alpha$-cuts, it is possible to reconstruct the fuzzy set as follows:
- Multiply the values of $\alpha$ by the set. Then get the maximum from each column.