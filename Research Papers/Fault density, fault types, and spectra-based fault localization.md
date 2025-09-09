---
Author: Nicholas DiGiuseppe
Year: 2014
tags:
  - faultlocalization
  - swe
Read: true
---
The authors analyze the performance of spectrum based fault localization algorithms and how they compare in terms of fault density (how many faults are there relative to the entire codebase) and fault types (classification of the faults). The authors define fault types from the papers:

Smith92
1. Inter-routine conceptual
2. Inter-routine actual
3. Intra-routine conceptual
4. Intra-routine actual

Firesmith92
1. Incorrect visibility
2. Missing component
3. Inconsistent component
4. Incorrect allocation/deallocation of resources
5. Does not meet requirements

Hayes94
1. Abstraction
2. Encapsulation
3. Modularity
4. Hierarchy

Hayes11
1. Data Declaration
2. Data Initialization
3. Data representation
4. Data accessing
5. Incorrect equation
6. Wrong manipulation
7. Incorrect/missing processing
8. Unnecessary processing
9. Rampaging go to
10. Incorrect labels
11. Dead-end code
12. Duplicate logic
13. Unachievable path
14. Incorrect initial value
15. Incorrect terminal value
16. Incorrect control value processing
17. Incorrect exception exit processing
18. Illogical conditions or impossible cases
19. Incorrect module interaction
20. Incorrect module-external data structure
21. Incorrect input parameters
22. Large response time
23. Lack of naturalness
24. Inconsistency
25. Redundancy
26. Complexity
27. Lack of flexibility
28. Non-supportiveness
29. Unpredictable flows
30. Visual stimulation
31. Platform
32. Wrong file included
33. Incorrect environment variable setting
34. Documentation

The authors make the following findings:
- The prominent fault's suspiciousness as well as the latent suspiciousness tends to increase as fault quantity increases.
- For spectrum based fault localization, there is little to no correlation between CFL and the fault type.
- In multi bug scenarios, there is also little correlation between the amount of interference and the fault type.