---
Author: Md Nakla Rafi
Year: 2018
tags:
  - faultlocalization
  - llm
Read: true
---
The algorithm's steps are: Context Extraction Agent, Debugger Agent, Reviewer Agent. The context extraction agent makes use of failing tests and stack traces to generate a failure reason. Code coverage is split into groups using the SBFL-Ochiai algorithms such that each group fits within a token limitation to avoid overflow when using the LLM. Each fault group is then used to enhance the failure reason and a new ranking is generated. Finally, the enhancement made in this step is the use of self-critique, which allows the LLM to refine its enhanced failure reasons iteratively.
The authors find that their proposed algorithm beats [[SoapFL - A Standard Operating Procedure for LLM Based Method-Level Fault Localization]] and [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization]] in top@1.