---
Author: Xin Xia
Year: 2014
tags:
  - faultlocalization
  - swe
Read: true
---
The authors propose a model to classify faults between two categories: *Bohrbug* and *Mandelbug*. The definitions for two bugs are provided below.
- *Bohrbug*: A bug which can be easily isolated and manifests consistently under a well-defined set of conditions.
- *Mandelbug*: This type of bug is difficult to isolate, and failures caused by it are hard to reproduce. It can happen either due to interactions with other systems or a time lag between the failure and the occurrence.
The authors make use of the bug reports to generate the solutions. For the classification algorithm, the authors make use of a text classifier that first picks out the most relevant features from a labelled dataset, and then identify which category matches the most based on the words in the bug report being prompted.