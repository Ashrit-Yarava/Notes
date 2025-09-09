---
Read: true
Author: Zifan Nan
Year: 2025
tags:
  - testgeneration
  - llm
---
The authors propose an algorithm that makes use of path exploration to generate a unit tests that have a more robust line coverage. The primary contribution the authors make is **PAINT**, which is a non-LLM tool that analyzes the CFG to identify the different execution paths that need to be explored by the test cases. The primary type of unit tests that the authors tackle are those that make use of *mocking*. The model that the authors use is the CodeLLaMa-34B-SFT which is a finetuned model for test generation.
## Test Intentions
These additional pieces of information provided to the LLM deal with adding guidance and constraints to the LLM. These intentions consist of 4 different parts:
- **Input Parameters**: Identify the parameters that the focal methods takes as input.
- **Mock Behavior**: Identify what the necessary mock statements are.
- **Hint Specification**: Additional user modified hint to guide LLM test generation.
- **Expected Result**: Identify what the test oracle should expect from a successful test (verifying correctness).
## PAINT: program analysis-drive test intention generating approach
This step consists of 3 major steps:
- **Block analysis**: Going through the CFG and combining different pieces of the call graph. The blocks are classified into 4 types: if blocks, switch blocks, exception blocks, and hybrid blocks.
- **Mock classifier**: Identification of mock callees.
- **SSM-DFS algorithm**: This step goes through the modified CFG to identify the different paths that the LLM should explore. In cases of method calls, the algorithm is called recursively to identify all [[Improving test suites for efficient fault localization#dynamic basic blocks]].
## Results
The authors test the algorithm on three industry projects that are anonymized. *The authors fail to explore properly and compare their approach to others.*
## My Notes
- The use of anonymized projects without any other information or comparison with other algorithms is somewhat frustrating. It could be that the projects themselves are easy to analyze.
- On the other hand, the LLM has definitely not seen this code due to the lack of exposure the code has to the internet.
- They also made use of a fine-tuned model that could be used for future projects as well.