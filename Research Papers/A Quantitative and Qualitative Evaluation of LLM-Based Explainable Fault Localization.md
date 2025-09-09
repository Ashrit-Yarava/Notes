---
Author: Sungmin Kang
Year: 2023
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose a method for the use of LLMs in FL by allowing the LLM to navigate the codebase. The LLM is augmented with the following functions allowing it to not only parse through the information presented in the codebase but also identify next steps to take through an approach similar to Chain of Thought.
- `get_class_covered`: Get the class in the coverage.
- `get_method_covered`: Get the method in the coverage.
- `get_code_snippet`: Get the specific code snippet related to a piece of code (method or class).
- `get_comments`: Get the documentation and other comments from the given element.
The steps for the algorithm are as follows:
1. AutoFL is given the failing test information and the descriptions of available functions for debugging. The LLM is given the failing test code and stack trace.
2. The LLM interacts with the provided functions (above) to interact with the codebase.
3. From the information, the LLM generates a root cause explanation.
4. LLM is queried to return the buggy location without the ability to make function calls.

The authors also implement a confidence mechanism, where the algorithm is run multiple times and the scores are combined based on the position of the method in the list through the formula given below:
$$
\text{score}(m) = \frac 1 R \sum_{k = 1}^R (\frac{1}{|r_k|} \cdot [m \in r_k])
$$
The formula above allows for reranking based on how the LLM identifies the method to be buggy across different runs. The authors identify that one of the issues that AutoFL runs into is when the FL requires digging deeper into the codebase. In other words, the LLM doesn't explore that well.