---
Read: true
Author: Sijja Gu
Year: 2025
tags:
  - testgeneration
  - llm
---
The authors propose the use of dynamic and static analysis for the generation of unit tests that capture more of the paths present. The authors present the algorithm as an emulation of the process human developers use for writing tests.
## Approach
The authors make use of the control flow graph and generate approximates through static analysis of the different paths. Then they use the test cases to identify invalid paths as well as provide failsafes in case there are methods which the LLM is unable to reason for.
### Iterative Strategy
The authors make use of an iterative strategy similar to the one found in [[ChatUniTest - A Framework for LLM-Based Test Generation]].
## My Notes
- Paper doesn't seem like it introduces anything that revolutionary.
- The results also are only compared against SysPrompt, which is the inspiration for the approach and the authors find that their approach beats SysPrompt handily.