---
Author: Yiling Lou
Year: 2021
tags:
  - faultlocalization
Read: true
---
The authors propose a learning based fault localization algorithm, GRACE, which makes use of graph neural networks to integrate code structure related information. The proposed algorithm is motivated by the idea that while coverage information is useful, it can be deceiving as seen in `Lang_47`, where the buggy methods are split across two different failing tests with commonly shared correct methods being ranked higher. The paper doesn't really make any new contributions in terms of GCNN architecture.

The algorithm's use of GCNNs demonstrates that code structure plays an important role in the algorithm. The results of the algorithm tested on Defects4J 1.2 and Defects4J 2.0 demonstrate that the algorithm significantly outperforms other benchmarks such as SBFL and [[DeepFL - integrating multiple fault diagnosis dimension for deep fault localization|DeepFL]].