---
Author: Nelson F. Liu
Year: 2023
tags:
  - llm
Read: true
---
The authors analyze different LLMs with large contexts (16k tokens) and identify how they utilize information present at different locations of the context. The authors make the following discoveries:
- Model performance is highest when the information occurs at the beginning or the end of the input context.
- Extended-context models are not necessarily better at using input context.
- Even in RAG models, using more for the QA isn't always that helpful as the improvements in accuracy tends to stagnate much earlier than when the context length is reached.
This phenomenon is also found in human brains, known as **the serial position effect**, when humans remember the first and last positions much better than the middle elements.