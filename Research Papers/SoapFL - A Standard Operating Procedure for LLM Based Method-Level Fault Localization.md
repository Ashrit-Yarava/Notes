---
Author: Yihao Qin
Year: 2025
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose an approach on the use of LLMs without running into issues with long context as highlighted in [[Lost in the Middle - How Language Models Use Long Contexts]]. The primary contribution is an approach that is able to provide LLMs with useful information regarding the coverage and test behavior.

Many approaches such as [[Large Language Models for Test-Free Fault Localization]] take a simplified approach and don't tackle the entire project context.
## Methodology
The process is composed of three main steps:
- **Fault Comprehension**: Analyze the potential causes of the exposed fault.
- **Codebase Navigation**: Search through the codebase by gradually refining the search, first identify suspiciousness classes and then identify the buggy methods in those classes. Unlike [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization|AutoFL]], the LLM does not have as much control in terms of navigating the codebase.
- **Fault Confirmation**: Aims to generate a list of the most suspicious methods that the developer should look through in order.