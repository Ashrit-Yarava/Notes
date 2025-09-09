---
Author: Yihao Qin
Year: 2024
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose an algorithm, CosFL, that uses code search concepts to augment fault localization. The primary contribution that the paper makes is the idea of using module level fault refinement before going for method level refinement. Modules are defined as closely connected methods on the call graph. Since the entire call graph cannot be fit inside an LLM's context, using the LLM to summarize modules can provide a way to generate summaries.

The authors find that their approach is able to beat [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization]] and [[SoapFL - A Standard Operating Procedure for LLM Based Method-Level Fault Localization]] in the Defects4J benchmark.