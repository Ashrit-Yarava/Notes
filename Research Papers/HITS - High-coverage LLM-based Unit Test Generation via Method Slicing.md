---
Read: true
Author: Zejun Wang
Year: 2024
tags:
  - testgeneration
  - llm
---
The paper explores the use of method slicing as a way to generate unit tests for methods with a high cyclomatic complexity. Unlike other approaches such as [[ChatUniTest - A Framework for LLM-Based Test Generation]], which fail for complex methods, the authors' proposed approach of splitting the method and dealing with each portion individually is able to generate a higher coverage compared to the others.