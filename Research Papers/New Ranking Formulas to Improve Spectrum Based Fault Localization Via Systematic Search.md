---
Read: true
Author: Qusay Idrees Sarhan
Year: 2022
tags:
  - faultlocalization
---
The authors attempt to use a formula template to search for better fault localization algorithms. The formula template they identify is based on common SBFL algorithms in terms of structure:
$$
\frac{\sum_{t \in {ef, ep}} n_tt}{\sum_{t \in {ef, ep}} d_tt} = \frac{n_{ef} ef + n_{ep} ep}{d_{ef} ef + d_{ep} ep}
$$
where $\{n, d\}_{\{ef, ep\}} \in \{-1, 0, 1\}$. From the possible set of possibilities, the following algorithms have the best results:
$$
F_6 = \frac{ef}{ep}
$$
$$
F_{10} = \frac{ef}{ep + ef}
$$
$$
F_{12} = \frac{ef}{ep - ef}
$$
Other algorithms do not work well.
## My Notes
- #idea : The limitations of the paper is that it does not explore a larger set of functions, as well as other options such as (method count in project, elements in the basic block, etc).
- The identified functions themselves seem to have a large similarity between the ochiai and tarantula algorithms.