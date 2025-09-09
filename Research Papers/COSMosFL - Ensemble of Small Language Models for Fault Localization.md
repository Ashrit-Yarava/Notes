---
Author: Hyunjoon Cho
Year: 2025
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose an improvement to [[A Quantitative and Qualitative Evaluation of LLM-Based Explainable Fault Localization|AutoFL]] to address concerns of code privacy as the AutoFL code was tested with the OpenAI GPT models. The proposed approach, however, makes use of ensemble of small language models (SLMs) to generate results. The authors *differential evolution* as a way to identify which models should contribute more.

One of the most interesting discoveries the authors make is that the different tested LLMs perform better for specific bugs. In other words, there is an orthogonality where specific LLMs succeed in localizing specific bugs while others do not.