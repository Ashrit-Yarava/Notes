---
Author: Kechen Li
Year: 2025
tags:
  - llm
  - pathfinding
Read: true
---
Pathfinding algorithms are essential in robotic and other environments. LLMs have demonstrated incredible reasoning ability. This paper aims to bridge the two and develop a new prompting strategy for LLMs that allows for finding optimal paths. Prior work in the field demonstrates that LLMs have been used directly to find paths but not as integrated with other existing algorithms.

The main idea behind the proposed prompting strategy, **Algorithm of Thought**, is to provide the LLM with a chain of thought style prompt but also provide the algorithm logic that a chain of thought model would use. The findings are as follows:
- AoT significantly improves LLM performance compared to Vanilla. AoT-Dijkstra and CoT maintain robust performance across different models and map sizes making them generally stable.
- Direct examples without reasoning with AoT tend to yield more consistent perforamcne, suggesting that *example complexity may influence model performance.*
- While scaling up models improves performance, it also leads to performance decline.