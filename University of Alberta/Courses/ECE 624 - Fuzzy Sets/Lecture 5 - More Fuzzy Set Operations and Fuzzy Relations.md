## Triangular Co-norms
Building upon [[Lecture 4 - Relations and Operations on Sets#Triangular Norms]], triangular co-norms have the following properties that a function $s: [0, 1] \times [0, 1] \to [0, 1]$:
$$
\begin{matrix}
\text{commutativity} & a \, s \, b = b\, s \, a\\
\text{associativity} & a \, s \, (b \, s \, c) = (a \, s \, b) \, s \, c\\
\text{monoticity} & \text{if } b \leq c, \text{then } a \, s \, b \leq a \, s \, c\\
\text{boundary conditions} & a\, s \, 0 = a \text{ and } a \, s\, 1 = 1
\end{matrix}
$$
This can be looked upon as a maximum operator, or the set OR operator.
### Examples of Triangular Co-Norms
$$
\begin{matrix}
\max (a, b) = a \vee b\\
a + b - ab\\
\min(a + b, 1)\\
\dots
\end{matrix}
$$
### The Relationship between Triangular Norms and Co-Norms
Given $s: [0, 1] \times [0, 1] \to [0, 1]$ is a t-conorm if and only if (iff.) there exists a t-norm (so-called dual t-norm) such that for any $a$ and $b$:
$$
a\, s\, b = 1 - (1 - a) \, t \, (1-  b)
$$
and the dual t-norm would be:
$$
a\, t\, b = 1 - (1 - a) \, s \, (1 - b)
$$
Given a t-conorm, you can derive the t-norm. This basically allows for us to find a triangular norm or a triangular co-norm given the other.
#### De Morgan's Laws for $t$-norm and $t$-conorm
$$
(1 - a) \, t \, (1 - b) = 1 - a\, s\, b
$$
$$
(1 - a) \, s \, (1 - b) = 1 - a\, t \, b
$$
This is a property in set theory and as seen, it is also applicable to fuzzy sets. The above equations can be used to derive the set theory rules: $\overline{A \cup B} = \bar{A} \cap \bar{B}$, $\overline{A \cap B} = \bar{A} \cup \bar{B}$.
## Negations
Given $N: [0, 1] \to [0, 1]$, the function $N$ must satisfy the following conditions:
$$
\begin{matrix}
\text{monotonicity} & \text{N is non-increasing}\\
\text{boundary conditions} & N(0) = 1, N(1) = 0
\end{matrix}
$$
### Example Negations
$$
N(a) = \sqrt[w]{1 - a^w}, w > 0
$$
$$
N(a) = \frac{1 - a}{1 - \lambda a}
$$
## Aggregation
$[0, 1]^n \to [0, 1]$ maps a given $n$ fuzzy sets to one fuzzy set.
- boundary condition: $agg(0, 0, \dots) = 0$ and $agg(1, 1, \dots) = 1$
- monotonicity: $agg(a_1, a_2, \dots, a_n) \geq agg(b_1, b_2, \dots, b_n)$ for $a_i \geq b_i \forall i \in [1, n]$
### Ordered Weighted Average
Given a vector of membership grades: $a = [a_1, a_2, \dots, a_n], a_1 \leq a_2 \leq \dots \leq a_n$ and a weight vector: $w = [w_1, w_2, \dots, w_n], w_i \in [0, 1]$ and $\sum_{i = 1}^n w_i = 1$
$$
OWA(w;a) = \sum_{i = 1}^n a_i w_i
$$
The aggregation operator above is basically what happens in a perceptron (without the ordering for $a$).
#### Compensatory Operators
$$
\begin{matrix}
(A \blacksquare B) (x) &=& [(A \cap B)(x)]^{1 - \gamma} [(A \cup B)(x)]^\gamma\\
(A \blacksquare B) (x) &=& (1 - \gamma)[(A \cap B)(x)] + \gamma[(A \cup B)(x)]\\
\end{matrix}
$$
### Generalized Averaging Operators
$$
agg(a_1, a_2, \dots, a_n) = \sqrt[p]{\frac 1 n \sum_{i = 1}^n a_i^p}
$$
Modification of the value of $p$ can result in different equations, such as:
- $p = 1$: arithmetic mean
- $p \to 0$: geometric mean
- $p = -1$: harmonic mean
- $p \to -\infty$: minimum operator
- $p \to \infty$: maximum operator
## Fuzzy Relations
A fuzzy relation $R$ is defined as $R: X \times Y \to [0, 1]$, more generally as a $n$-fold Cartesian product:
$$
X_1 \times X_2 \times \dots \times X_n \to [0, 1]
$$
It can be represented as a multi-dimensional matrix where each axis contains the elements of its associated set.
### Domains and Codomains
A fuzzy relation $R: X\times Y \to [0, 1]$
- Domain: $\text{dom} R(x) = \sup_{y \in Y} R(x, y)$
- Domain: $\text{cod} R(x) = \sup_{x \in X} R(x, y)$
## Relationships between Fuzzy Relations
- Equality: $R = Q$: $R(x, y) = Q(x, y), \forall (x, y) \in X \times Y$
- Inclusion: $R \subseteq Q$: $R(x, y) \leq Q(x, y), \forall (x, y) \in X \times Y$
- Union: $R = P \cup Q$: $R(x, y) = P(x, y) \, s \, Q(x, y) \forall (x, y) \in X \times Y$
- Intersection: $R = P \cap Q$: $R(x, y) = P(x, y) \, t \, Q(x, y) \forall (x, y) \in X \times Y$
- Complement: $\bar R$: $\bar{R}(x, y) = 1 - R(x, y), \forall x \in X \times Y$
#### Transposition
If a fuzzy relation is defined as: $R^T: Y \times X \to [0, 1]$, then the transposition is defined as:
$$
R^T(y, x) = P(x, y), \forall (x, y) \in X \times Y
$$
The transposition operator has the following features: $(R^T)^T=R$, $\bar{R}^T = \overline{R^T}$
#### Cartesian Product
Given fuzzy sets $A_1, \dots, A_n$ defined in the universes $X_1, \dots, X_n$ respectively, a fuzzy set $R: X_1 \times \dots \times X_n \to [0, 1]$:
$$
R(x_1, \dots, x_n) = \min(A_1(x_1), \dots, A_n(x_n)), \forall x_1 \in A_1, \dots, \forall x_n \in A_n
$$
$$
R(x_1, \dots, x_n) = A_1(x_1)\, t \, A_2(x_2) \, t \, \dots \, t \, A_n(x_n), \forall x_1 \in A_1, \dots, \forall x_n \in A_n
$$
#todo More Notes
### Binary Fuzzy Relations
Defined as properties that are present for fuzzy relation $R: X \times X$.
- Reflexivity: $R(x, x) = 1, \forall x \in X$, $X$ is finite and $R \supseteq I$
- Symmetry: $R(x, y) = R(y, x), \forall (x, y) \in X \times X$, $R^T = R$
- Transitivity: $\sup_{z \in X}[R(x, z) \, t \, R(z, y)], \forall x, y, z \in X$

#### Equivalence Relations
The equivalence class of $R$, that has the properites reflexivity, symmetry, and transitivity, with respect to $x$ ($x$ is fixed), denoted by family of equivalence classes of $R$ denotes $X / R$ forms a partition of $X$. In other words, $X / R$ is a family of pairwise disjoint nonempty subsets of $X$ whose union is $X$.
$$
A_x = \{y \in Y | R(x, y) = 1\}
$$
You can imagine this as a boolean matrix where the row is fixed and $y = 1$ when the above condition is satisfied. The similarity constraint on the relation ensures that $\exists y \in Y R(x, y) = 1$ as $x = y$.
#### Similarity Relation
Fuzzy relation is reflexive, symmetric, and transitive, then:
Similarity relation represented by a nested family of its $\alpha$-cuts, $R_\alpha$. Then each $\alpha$-cut constitutes an equivalence relation and forms a partition of $X$. Similarity relation is associated with a set of $P(R)$ of partitions of $X$. Similarity relation is associated with a set of $P(R)$ of partitions of $X$.
$$
P(R) = \{X / R_\alpha | \alpha \in [0, 1]\}
$$
if $\alpha > \beta$, then the partition $X / R_\alpha$ is finer than the partition $X / R_\beta$. In a boolean matrix, they form blocks of $1$s (refer to lecture slides Presentation 4). A tree structure can also be used to represent this, and is called a **dendrogram**.
## Fuzzy Relational Equations
Given the equation:
$$
Y = X \circ R
$$
where $X$ and $Y$ are fuzzy sets defined in $\mathcal{X}$ and $\mathcal{Y}$ and $R$ is a fuzzy relation defined in $\mathcal{X} \times \mathcal{Y}$. There are two types of equations that can be written:
- Given $X, Y$, determine $R$.
- Given $Y, R$, determine $X$.
### Solution (1): $\upphi$ (pseudo-residuation operator)
Given $a, b \in [0, 1]$, define the operator $\upphi$ as:
$$
a \upphi b = \sup \{c \in [0, 1] | a \, t \, c \leq b\}
$$
For example, take $a \, t \, c = \min \{a, c\}$
$$
a \upphi b = \sup\{c \in [0, 1] | \min(a, c) \leq b\}
$$
Take the first case, $a \leq b$, then $a \upphi b = 1$. In the second case, $a > b$, then $a \upphi b = b$.

The above formulation has the following lemmas that are satisfied:
- $R \subset X \upphi (X \circ R)$
- $X \circ (X \upphi Y) \subset Y$
#### Theorem
Given a family of fuzzy relations satisfying the equation $X \circ R = Y$:
$$
\mathcal{R} = \{R | X \circ R = Y\}
$$
If $\mathcal{R} \neq \emptyset$, then the maximal element of the family of $\mathcal{R}$ denoted by $R$ is expressed as, where $\hat{R}$ is the maximum:
$$
\hat{R} = X \upphi Y
$$
This can be used for approximating the fuzzy relation between two fuzzy sets as:
$$
\begin{matrix}
(X_k, Y_k)_{k = 1, 2, \dots, n}\\
\forall_k X_k \circ R = Y_k, R_k \neq \emptyset\\
\hat{R} = X_k \circ Y_k\\
R_1 \cap R_2 \cap \dots \cap R_n\\
\hat{R} = \bigcap_{k = 1}^n \hat{R}_k
\end{matrix}
$$
#### Thoerem
If $X \neq \emptyset$, then the maximal element of $X$ (in terms of fuzzy set inclusion) is given in the form:
$$
\hat{X} = R \upphi Y
$$
$$
\hat{X}(x) = \min_y [R(x, y) \upphi Y(y)]
$$

