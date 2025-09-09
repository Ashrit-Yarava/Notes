---
Author: Aidan Z.H. Yang
Year: 2023
tags:
  - faultlocalization
  - llm
Read: true
---
The authors propose a test-free approach to *line level fault localization* making use of LLMs to identify the most suspicious method in the codebase. The authors trained LLMs of a variety of sizes on the *Defects4J* corpus.

Compared to prior works such as [[DeepFL - integrating multiple fault diagnosis dimension for deep fault localization|DeepFL]], are mainly only good for method level FL and have limited performance at the line level.

The approach is as follows: Get the buggy program and retrieve the tokens for the given code using the GPT-2 tokenizer. Use the pretrained LLM along with a mask of the positions of the newline tokens to generate the scores for each of the tokens in the code. Using these tokens and the locations of the newline tokens, generate scores for each line using dot produce between the values for each token in the line and a learning 1d matrix. The LLM also has a bidirectional adapter for allowing the model to look at the code before and after the token of interest.

Since the algorithm is line level, the authors only run the algorithm on modified files in the buggy projects.
## Results
The authors identify that the 16B parameter model performs the best on Defects4J 1.2.0 and is able to outperform the other algorithms. The authors also note in an ablation study that the algorithm performs poorly without pre-training or bi-directionality.