---
Read: true
Author: Shay Artzi
Year: 2007
tags:
  - faultlocalization
  - testgeneration
---
The authors attempt to identify how well automatically generated test suites are for fault localization. The authors test a combined approach to test generation (concrete and concolic) that allows for a fewer number of tests while maintaining a similar fault localization performance. The authors use SBFL (ochiai and tarantula) as metrics to identify how good the test dataset is.

For their implementation, the authors make use of *Apollo*, which makes use of a shadow interpreter for concrete executions and symbolic executions.
## Approach
Concolic testing refers to the symbolic execution of certain variables in a program to identify the values upon which they cause different program outputs. This approach can be useful for deriving a much smaller subset of test methods while maintaining the same level of coverage.
### Similar Executions
Generating test cases that have similar executions is also pivotal for a good test suite. In this case, the authors compare the paths that the test cases take to identify similarity. In this manner, methods that are different from one another in the similar test cases can be treated as the root cause of the bugs.

This is the primary innovation in the paper, with the generation of similar test cases found to have better results compared to other test case generation algorithms targeted toward fault localization.
## My Notes
- The idea of generating similar test cases could be explored more in depth with LLM based approaches. This is especially true for large projects where symbolic execution might not be viable. Or if symbolic execution has too large a search space.