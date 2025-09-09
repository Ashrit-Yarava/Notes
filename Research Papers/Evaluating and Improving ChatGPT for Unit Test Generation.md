---
Read: true
Author: Zhiqiang Yuan
Year: 2024
tags:
  - testgeneration
  - llm
---
The authors explore the use of ChatGPT for generating unit tests for focal methods. The authors propose a rudimentary approach where they provide the LLM with the class level information and the focal method code and ask the LLM to generate the unit test. They then perform a refinement step attempting to fix the compilation errors that might occur. The authors compare their results against a learning-based approach and a normal test generation suite. The primary contribution the authors make is identifying that the LLM-generated tests are similar to human written tests which is an improvement over system generated tests which are usually unreadable.
## Results
While the generated tests are human-readable, a large percentage of them are unable to be fixed by the refinement step. The results from the paper are given below:
- ChatGPT outperforms learning-based techniques but only a portion of the generated tests can pass the execution.
- ChatGPT fails to generate accurate assertions often.
- ChatGPT generated tests resemble manually written ones in terms of test sufficiency. They also achieve a similar coverage.
The authors propose some possible improvements to the algorithm, one of them being providing more information regarding the coverage and information about the project, which is explored in [[ChatUniTest - A Framework for LLM-Based Test Generation]].
## My Notes
- The paper itself doesn't have significant results, it is more of an exploratory study. But it sufficiently shows that ChatGPT can produce viable tests.