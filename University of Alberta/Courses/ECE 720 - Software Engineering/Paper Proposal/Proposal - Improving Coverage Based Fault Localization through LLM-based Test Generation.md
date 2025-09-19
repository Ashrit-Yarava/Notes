## Abstract
Spectrum-based fault localization (SBFL) is one popular coverage based FL algorithm. It uses the test coverage to identify the most suspicious code elements. As a result, the quality of a test suite plays a major role in algorithm performance. Developer and automated test generation strategies aim to maximize test coverage. This results in tests that cover large portions of the codebase and is detrimental to FL. The proposed algorithm improves test suite quality by adding new unit tests. An improved test suite also leads to better SBFL performance.
## Background
### Spectrum Based Fault Localization
SBFL is a coverage based fault localization algorithm that relies on the relationship between the passing and failing tests and their associated coverage patterns. Through ranking algorithms such as Ochiai, TARANTULA, and DStar, it is possible to assign suspiciousness scores to code elements (at different levels of granularity such as class, method, or line level).

While SBFL isn't considered a state of the art fault localization algorithm, it is used almost exclusively in fields such as automated program repair ([[You Cannot Fix What You Cannot Find! An Investigation of Fault Localization Bias in Benchmarking Automated Program Repair Systems]]). As such, indirect improvements to SBFL allow for improvements to existing algorithms.
## Dynamic Basic Blocks and Fault Localization
First introduced in [[Improving fault localization with pre-training]], dynamic basic blocks refer to sets of code elements that fall under the same test coverage. In SBFL, this is a massive negative impact as it results in two elements having the same suspiciousness score (tiebreaks). Large basic blocks can result in 
