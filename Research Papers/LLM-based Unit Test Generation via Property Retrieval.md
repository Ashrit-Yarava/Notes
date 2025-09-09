---
Read: true
Author: Zhe Zhang
Year: 2024
tags:
  - testgeneration
  - llm
---
The authors propose an approach to LLM based test generation that builds upon the work of [[ChatUniTest - A Framework for LLM-Based Test Generation]] by building a more robust retrieval tool for generating unit tests. The authors argue that the approach used in ChatUniTest does not take into account other elements of the code that would be useful such as helper methods already present and other similar test cases.
#### Scope Graphs
The authors make use of a scope graph to identify the information that is available to the LLM. Compared to a call graph, the scope graph identifies all possible things that are available to a method, this information can be useful when generating unit tests as it provides the LLM with more information.
## Improvements
#### Excessive Mocking
When not given the right amount of context, the LLM's generated unit tests will have an excessive amount of boilerplate code that is repeated in the actual codebase. One example is an LLM rewriting an `encode` method when testing a `decode` method when it is already there in the codebase. The authors argue that prior works do not retrieve this type of information.
## Iterative Strategy
They replicate the refinement strategy used in ChatUniTest but also accounting for changes made in this algorithm.
## Approach
Generated unit tests have 3 phases that the proposed approach targets:
- **Given**: This phase is the pre-processing step, where methods needed for setup are used.
- **When**: Information that is found the codebase can help identify what information to pass to the focal method.
- **Then**: Assertions and exception handling in the `encode` method's unit test can be a framework for how the `decode` method's unit test should look like.
Note that during the information retrieval stage, methods in the codebase along with their associated unit tests are retrieved. This retrieval approach also helps with larger codebase elements such as inheritance and interfaces.
## Results
The results show that the author's proposed approach, PAGTest, significantly outperforms the other methods due to the added information. The LLM is also less prone to running into compilation errors and the like. Finally, the iterative strategy shows improvements in reducing errors and improving unit test generation.
## My Notes
- This paper is a much more robust algorithm that builds upon the prior work. Unlike the other unit test generation algorithms, this one provides a lot more information to the LLM and thus, producing better unit tests.
- One of the concerns the authors raise is how performance is negatively impacted in projects that make use of a lot of abstract classes and such, where the LLM attempts to initialize these abstract classes resulting in errors.