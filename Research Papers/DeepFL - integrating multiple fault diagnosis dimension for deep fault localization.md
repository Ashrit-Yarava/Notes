---
Author: Xia Li
Year: 2019
tags:
  - faultlocalization
Read: true
---
The authors propose the use of deep learning methods for learning the best latent features for fault localization. The authors make use of the flexibility of DL by making use of information related to the suspiciousness-value, fault proneness information, and textual-similarity features for method level fault localization.

For implementation, the authors made use of 34 SBFL based suspiciousness metrics, mutation based features are identified with PIT mutation testing tool, complexity based features from JHawk, and text similarity features between source code and failing tests. The neural network is a simple MLP.

The authors find that mutation information is some of the most valuable information for the MLP to rank the best.