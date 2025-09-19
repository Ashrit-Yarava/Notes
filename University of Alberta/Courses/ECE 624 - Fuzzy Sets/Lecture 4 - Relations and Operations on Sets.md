The [[Lecture 3 - Interval Computing#Extension Principle]] can also be extended to functions that take multiple arguments as inputs:
$$
B = f(A, C)
$$
$$
B(y) = \sup_{x, y} [\min (A(x), C(z))], y=f(x, z)
$$
## Relations
> subsets of a cartesian product of some spaces.

$$
R = \{(x, y) | x^2 + y^2 = 4\}
$$
Relations are **direction free constructs**.
### Operations on Relations
- **Union**: $(R \cup G)(x, y) = \max(R(x, y), G(x, y))$
- **Intersection**: $(R \cap G)(x, y) = \min(R(x, y), G(x, y))$
- **Complement**: $\bar{R}(x, y) = 1 - R(x, y)$
## Cylindric Extension
If $A$ is defined over $X$, its cylindric extension formed over the Cartesian product of $X$ and $Y$, $\text{cyc}_y{A}(x, y) = A(x)$ for any pair of $(x, y)$. Now $\text{cyc}(A)$ and $R$ are of the same form being the two relations defined over $X \times Y$. This is a way of adding new dimensions to a given relation.
## Projection
Reduction of the dimensionality of $R$.
$$
\text{Projection on } X : \text{Proj}_X R(x, y) = \sup_y R(x, y)
$$
$$
\text{Projection on } Y : \text{Proj}_Y R(x, y) = \sup_x R(x, y)
$$
## Composition
Given $R \in X \times Z$ and $G \in Z \times Y$, identify a relation $T \in X \times Y$. There are two ways to perform this:
- **sup-min composition** (max-min): $T = R \circ G \to T(x, y) = \sup_z [\min (R(x, z), G(z, y))]$
- **inf-max composition** (min-max): $T = R \star G \to T(x, y) = \inf_z [\max (R(x, z), G(z, y))]$

## Operations on Fuzzy Sets
The set operations defined for sets also apply to fuzzy sets. However, there is a $\max$ and $\min$ that needs to be taken into account.
$$
(A \cap B)(x) = \min(A(x), B(x))
$$
$$
(A \cup B)(x) = \max(A(x), B(x))
$$
The complement is defined as:
$$
\bar{A}(x) = 1 - A(x)
$$
For fuzzy sets however, the **excluded-middle** and **non-contradiction** are not satisfied. They do not result in an empty set, or the universe set.
### Triangular Norms
Inspired originally by probabilistic metric spaces. Given two degrees of membership $a = A(x), b = B(x)$. There are an infinite family of functions that satisfy the following conditions.
Triangular norms allow for the following properties:
- commutativity: $a \ t \ b = b \ t \ a$
- associativity: $a \ t \ (b \ t \ c) = (a \ t \ b) \ t \ c = a \ t \ b \ t \ c$
- monotonicity: if $b \leq c$, then $a \ t \ b \leq a \ t \ c$
- boundary conditions: $a \ t \ 1 = a$ and $b \ t \ 0 = 0$
This can be looked upon as the set AND operator.
### Example $t$-norm functions
- $\min$
- Product
- $a \ t \ b = \max(a + b - 1, 0)$
- Drastic Product: $a \ t \ b = \left\{\begin{matrix}a & \text{if } b = 1\\ b & \text{if } a = 1\\ 0 & \text{otherwise}\end{matrix} \right\}$ 
- $a \ t \ b = \frac{ab}{p + (1 - p)(a + b - ab)}, p \geq 0$
- $a \ t \ b = \max{0, (1 + p)(a + b - 1) - pab}, p \geq -1$
- $a \ t \ b = \sqrt[p]{\max{(0, a^p + b^p - 1)}}, p > 0$
Drastic Product < t-norm < minimum