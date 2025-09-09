---
Read: true
Author: Michael Konstantinou
Year: 2025
tags:
  - testgeneration
  - llm
---
The authors propose an algorithm that is primarily motivated toward fixing the failing test cases that are generated and promptly discarded in [[ChatUniTest - A Framework for LLM-Based Test Generation]] and [[Evaluating and Improving ChatGPT for Unit Test Generation]]. The authors argue in that many of the cases for these algorithms, there is only minor modifications that need to take place to fix these errors and fixing these errors can be valuable compared to regenerating the test suite. The authors manage to achieve a high performance beating the other LLM based unit test generation tools through the use of a more robust refinement approach compared to ChatUniTest. They also make use of static analysis.

The other contribution that the authors make is the exploration of class-level and method-level test generation. They find that class-level generation is more cost efficient but method-level has a larger line coverage.