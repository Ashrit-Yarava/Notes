---
Author: Potsawee Manakul
Year: 2023
tags:
  - llm
Read: true
---
The authors propose a black box algorithm for determining whether LLM output is a hallucination or not. The outlined approach demonstrates a good performance and is able to beat other white box and grey box approaches.

The algorithm revolves around comparison of LLM output to the same prompt to identify if there are differences between LLM output. Differences indicate that the LLM is not confident on the answer and as such, the probabilities for the tokens are low and are prone to change. Given an LLM output $x$, generate $x_1, \dots, x_n$ output samples from the same prompt. Compare $x$ with the other outputs to see if they relate.

The two best comparison approaches are outlined below (others weren't that good):
- *LLM prompting*: Ask the LLM whether the labels $x$ and $x_i$ are similar or not.
- *Natural Language Interface (NLI)*: Use a text entailment classifier (whether the following statement matches a premise).

Both of these approaches perform above the baseline.