---
Author: Yasin Abbasi Yadkori
Year: 2024
tags:
  - llm
Read: true
---
The authors propose a metric for determining the amount of epistemic uncertainty in LLM output. *Epistemic uncertainty* refers to the irreducible randomness and could take the form of multiple outputs. The proposed metric is useful for identifying when using an LLM's output is unreliable.

Prior works deal on the assumption that there is only one correct answer and this approach is not useful for LLMs due to the inherent variance present in natural language as well as the presence of multiple answers to given prompts.

The main idea behind the paper is to prompt the model multiple times and providing prior responses to generate more responses. This approach generates a distribution of possible answers with the higher likelihood answers encountered more often. The example prompt in the paper is given as follows:
	Consider the following question $Q$: $x$
	One answer to question $Q$ is $Y_1$. Another answer to $Q$ is $Y_2$. $\dots$ Another answer to $Q$ is $Y_t$.
	Provide an answer to the following question:
	Q: $x$. A:

Information on the implementation and the math behind the algorithm can be found in the paper.