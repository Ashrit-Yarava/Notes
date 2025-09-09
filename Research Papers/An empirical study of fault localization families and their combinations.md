---
Read: true
Author: Daming Zou
Year: 2019
tags:
  - faultlocalization
---
The authors explore the performance and ability of 6 different fault localization strategies:
- **Spectrum-based fault localization**
- **Mutation-based fault localization**
- **Dynamic Program Slicing**
- **Stack Trace Analysis**
- **Information-retrieval based fault localization**
- **History-based fault localization**
The authors also propose a new algorithm, `CombineFL`, which attempts to take an ensemble of these methods in order to achieve better performance.
## Research Questions
1. *Effectives of Standalone Techniques*: SBFL is found to be the most effective fault localization strategy overall. Stack trace analysis is the best for crash faults.
2. *Correlation between techniques*: Most techniques are weakly correlated, and the strongly correlated methods are only correlated in the same strategy.
3. *Effectives of combined techniques*: The combined technique significantly outperforms any other technique.
4. *Time Consumption and Combination Strategy*: Less time consuming techniques almost always have a positive impact if a more time consuming strategy is used when used in combination.
## My Notes
- #idea: This paper could be used as a template for studying LLM based fault localization strategies.