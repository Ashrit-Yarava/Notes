---
Read: true
Author: Cong Li
Year: 2024
tags:
  - llm
  - codesummarization
  - codechange
---
The authors of the paper explore the use of finetuned small-scale language models ($\leq 10 \textit{ billion parameters}$) for generate change summaries between code commits.
## Code Change Summarization
The idea of code change summarization is to automate the generation of commit messages. The advantages of automated commit message generation is the existence of a default template and less time spent by the developer going over their changes such that others can understand.
## Motivation
While LLMs are capable of performing well in terms of generating commit messages, they are very resource heavy and can lead to increased costs, especially for large codebase changes. Additionally, LLMs are better for this task as prior appproaches face the following drawbacks:
- **Restricted code-change understanding**: Unable to effectively understand syntax.
- **Biased code-change datasets**: The patterns found in the dataset skew the understanding that the trained methods have.
## HQCM Benchmark
The authors develop a new small dataset that can be used for finetuning the SLM to have a competitive performance. The authors finetune the `LLaMa2-7B`, `CodeLLaMa-7B`, and `CCT5-220M` models.
## Research Questions
- **Quality of HQCM: How does HQCM dataset compare against the SOTA dataset, MCMD in finetuning SLMs?**

SLMs can be faster, requiring significantly less data while achieving a competitive performance with SOTA large-sclae datasets, such as the MCMD dataset.

- **Basic Understandings: In the context of change summarization, the foundation of other change-related tasks, how do HQCM-finetuned SLMs compare with SOTA baselines?**

All SLMs demonstrated impressive basic understanding of code changes: They achieved competitive BRSA with baselines and were more favored in anonymous evaluations.

- **Advanced Understandings: For tasks more advanced than change summarization, change classification and code refined, does HQCM enhance SLMs with competitive understanding than much better baselines?**

The `LLaMa2-7B` finetuned model acheived better performance than large language models ($\leq 70 \textit{ billion parameters}$).
## My Notes
- #idea: One of the key things that the authors do not touch upon is how the change summary differs in a real world context. Future works could work toward building a dataset of real world changes and how they differ. This could be in terms of release differences.