---
Author: Silin Meng
Year: 2024
tags:
  - llm
  - pathfinding
Read: true
---
The authors propose an approach of integrating LLMs for path planning. The authors primary motivation for this algorithm is that LLMs have shown reasoning and planning capabilities that can be useful for providing an overview of the possible paths and generating a candidate list.

The authors use the LLM to generate a set of candidate paths, and then use A-star search to search through the paths. Unlike [[GridRoute - A Benchmark for LLM-Based Route Planning with Cardinal Movement in Grid Environments]], the authors make use of the LLM only to generate the candidate paths without consideration for the path itself.