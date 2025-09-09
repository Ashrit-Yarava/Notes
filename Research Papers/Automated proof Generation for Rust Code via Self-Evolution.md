---
Author: Tianyu Chen
Year: 2024
tags:
  - codeverification
  - llm
Read: true
---
The paper tackles the use of proof generation for program code using [Verus](https://github.com/verus-lang/verus)-a proof verification tool for Rust code. They propose a method (SAFE) using LLMs to generate proofs for Rust code without a large dataset as is present for LEAN. They make use of VERUS as it tackles proof generation for Rust which is a popular programming language but also doesn't have a lot of code that is VERUS compatible.

The steps of the algorithm are as follows:
1. *Generating VERUS-compatible code*: VERUS cannot check specific Rust syntax yet (such as for loops). As such, Rust code needs to be translated to generate an initial set of programs.
2. *Self-Evolving Specification Synthesis*: LLMs are tasked with generation preconditions and postconditions for a Rust function based on function's implementation and docstring. The authors note that the goal of the program is not code correctness but proof synthesis and as such they can ignore the incompleteness requirement (incorrect code implementations should be rejected).
3. *Self-Evolving Proof Synthesis*: Use an LLM to synthesize a proof for the Rust code, with the model being able to correct itself on previous outputs depending on how the output performed.

The authors find that SAFE performs better than the current benchmark (CodeNet-Test).