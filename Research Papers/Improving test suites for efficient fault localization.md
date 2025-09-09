---
Read: true
Author: Benoit Baudry
Year: 2003
tags:
  - faultlocalization
  - testgeneration
---
The authors explore the impact of generating test cases with the goal of fault localization. Unlike regular test generation, this approach focuses on generating test cases that attempt to help improve fault localization performance. The primary contribution of the paper is the concept of the test criterion, a measure of how good a test suite is for fault localization.
## Test-for-Diagnosis (TfD) criterion
This criterion bridges the gap between generating good test cases and how well they perform for fault localization. This is calculated using the **Dynamic Basic Block**.
> Two statements $s_1$ and $s_2$ are part of the same dynamic basic block if they test cases that they are executed under is the same.

Good fault localization performance aims to maximize the number of dynamic basic blocks.

The authors empirically test this by making use of a genetic algorithm to identify how differences in TfD (number of dynamic basic blocks) impact the performance. The authors find that larger number of dynamic basic blocks are beneficial to the algorithm.
## My Notes
- The paper is really old and makes use of terminology that is not reflected in the more recent papers. *Diagnosis accuracy* is the $top@k$ metric.