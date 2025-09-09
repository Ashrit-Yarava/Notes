---
Read: true
Author: Jifeng Xuan
Year: 2011
tags:
  - faultlocalization
  - testgeneration
---
The authors propose an approach toward improving SBFL by targeting the test cases. The motivating example the authors present is based on the idea that test cases with multiple assertions can be split. For example, in the code below, if the first assertion fails, then the later assertions are not executed resulting in "tests" that are not explored.
```python
x = get_x()
assert x == 20
assert x == 10 
```
The authors evaluate their approach on 1800 seeded bugs (synthetic bugs).
## Approach
The authors first localize the faults with the given SBFL technique. From there, they retrieve the failing test cases and perform test case purification to get single-assertion test cases. These single-assertion test cases are then ran once again to get the spectra. Finally, the rank refinement phase adjusts the scores according to the new information.
### Test Case Purification
Purification of a test case refers to silencing failing assertions in a test case through surrounding the assertion with a `try-catch` block. This prevents the failing assertion from impacting the other methods. The authors make use of test case purification by first duplicating the test case for each assertion and then silencing specific assertions in each test case such that each test case is executed.
### Rank Refinement
In the proposed approach, the authors make use of the rank refinement phase to adjust the original SBFL scores to take into account the failing test cases. The $ratio$ is defined as the score for the new test cases and is defined as:
$$
ratio(s) = \frac{\beta_{ef}(s)}{\beta_{ef}(s) + \beta_{nf}(s)}
$$
where $\beta_{ef}(s)$ is the number of test cases that execute $s$ and $\beta_{nf}(s)$ is the number of test cases that do not execute $s$. They define the $norm$ as the normalized score of the original SBFL suspiciousness scores with the set of SBFL scores defined as $S$:
$$
norm(s) = \frac{susp(s) - min(S)}{max(S) - min(S)}
$$
## Results
The authors found that their approach rarely has a negative impact (only around 1% of the bugs had a worse performance) on the rankings averaging around 30% of the seeded bugs being successful at improvement while the others were not.
## My Notes
The paper explores the algorithm on seeded bugs with unit testing. Possible avenues of exploration from here are:
- Testing how the algorithm performs on transient faults (stuff found in the `java.util.Math` project).
- Synthetically generated bugs are often found to not be a good metric for comparison (explore how the algorithm performs in actual bugs).
- Exploring only the failing test cases leaves the passing test cases un-purified possibly skewing the result by not adding more to the `ep`.