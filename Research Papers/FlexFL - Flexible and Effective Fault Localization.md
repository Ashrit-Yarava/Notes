---
Author: Chuyang Xu
Year: 2024
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose an LLM based fault localization approach that makes use of smaller LLMs that can be self-hosted. The authors augment the approach compared to other approaches by using LLM agents to filter out information as well as integrating other approaches for a larger candidate list of methods.

The approach is split into two stages as follows:
1. **Space Reduction**: Making use of the LLM agent to analyze the failing test methods as well as bug reports, the algorithm generates a candidate list of methods similar to the approach used for LLM navigation of codebase in [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization|AutoFL]].
2. **Location Refinement**: Another agent in used to rerank the given methods. The agent is also given the ability to inspect the code and through this along with a chain-of-thought style approach, the agent is able to identify the most suspicious methods.

The authors demonstrate that the approach is able to beat other leading LLM based approaches such as [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization|AutoFL]] and [[SoapFL - A Standard Operating Procedure for LLM Based Method-Level Fault Localization|SoapFL]] but convey that it is unable to beat learning based approaches such as [[DeepFL - integrating multiple fault diagnosis dimension for deep fault localization|DeepFL]] or [[Boosting Coverage-Based Fault Localization via Graph-Based Representation Learning|Grace]].