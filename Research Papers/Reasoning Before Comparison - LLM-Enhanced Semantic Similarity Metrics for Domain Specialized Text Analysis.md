---
Author: Shaochen Xu
Year: 2024
tags:
  - llm
  - nlp
Read: true
---
The paper argues that using traditional text similarity metrics such as BLEU and ROGUE is not viable for identifying similarity in domain specific tasks. The traditional approaches focus more on the semantic similarity and not the content that is present. However, through the use of LLMs such as GPT-4, the authors tackle text similarity identification. Through the use of an LLM to generate labels for the given topic, and then using those labels, they use an embedding model to identify their similarity using cosine similarity.

The authors find that the LLM based approach is much better and approaches the theoretical best much more than traditional approaches.