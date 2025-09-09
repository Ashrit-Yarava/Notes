---
Author: Inseok Yeo
Year: 2025
tags:
  - faultlocalization
  - llm
Read: true
---
Other LLM based approaches do not give the model a context regarding the project which might cause confusion in the LLM as it does not have an idea about the larger scope of the project. This paper introduces an approach to alleviate this through the introduction of a static memory component. This component keeps track of information across the LLM and allows the LLM to retain information it might need later (description of the class as well as how it might be used). In comparisons with AutoFL and SoapFL, the authors found that MemFL performs much better.