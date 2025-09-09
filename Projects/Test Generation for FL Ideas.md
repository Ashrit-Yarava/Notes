## LLM Test Generation for Maximizing Basic Blocks for Improved SBFL
SBFL results are directly related to the number of basic blocks, with more basic blocks resulting in better performance ([[Improving test suites for efficient fault localization]]). Current LLM-based test generation approaches are capable of generating tests for much more complex scenarios compared to classical approaches, however, they focus solely on test coverage and such a focus could be detrimental to SBFL. Prior work on test generation for FL primarily makes use of non-LLM based approaches such as genetic algorithm and as such, aren't able to generate tests for more complex methods.
## Motivation
- How does the number of basic blocks impact the performance of SBFL?
- Does SBFL perform worse when the faulty method is in a large basic block?
### Innovation
Identify the most suspicious methods, and the methods that are in the largest basic blocks, and generate tests to increase the number of basic blocks for those tests. This becomes a balancing problem of selecting the most suspicious test methods that are also in large basic blocks. Breaking down the basic blocks could result in better results (fewer tiebreaks, etc).
#### Minor Innovation: Bug Information
Provide the LLM with the bug information to generate tests that are more directly related to FL. This could possibly increase the likelihood of testing relevant methods. The bug information would also include information such as the failing test case. A relevant paper, [[LLM-based Unit Test Generation via Property Retrieval]], shows that there is an improvement in test generation performance when the LLM is given test cases.
*Possible ablation test on whether providing this information is helpful or not.*