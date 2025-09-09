---
Author: Jan Ploski
Year: 2007
tags:
  - faultlocalization
Read: true
---
The authors analyze prior work done in software fault categorization.
## Knuth's Errors of $\TeX$
Knuth's paper revolved around his classification of bugs from his work on $\TeX$ and the programming languages, SAIL and Pascal. One thing to note is that the author points out that his categorization scheme did not help him reduce the number of bugs, but rather helped him analyze and know the types of bugs he encountered. The 9 non-nested faults are:
- (A) algorithm awry
- (B) blunder or botch
- (D) data structure debacle
- (F) forgotten function
- (L) language liability
- (M) mismatch between modules
- (S) surprising scenario
- (T) trivial typo
## Beizer's Bug Taxonomy
Beizer and Vinter provide a comprehensive categorization schema for software faults. The dimensions used to identify the faults are not directly stated, similar to [[#Knuth's Errors of $ TeX$]]. Unlike Knuth's work, Beizer's taxonomy is hierarchal and contains 8 top level categories and over 100 leaf categories. The 8 top level categories are given below:
- Functional bugs: requires and features
- Functionality as implemented
- Structual bugs
- Data bugs
- Implementation (typographical and violations of standards and conventions, errors in documentation)
- Integration (bugs having to do with interfaces between components)
- System and software architecture
- Test definition and execution (test method bugs)
## Gray's Classification of Software Faults in production software
This paper introduces two types of bugs, similar to the bugs found in [[Automatic Defect Categorization for Fault Triggering Conditions]]:
- **transient faults** (called Heisenbugs) whose activations can be masked by restoring consistent initial state and retry. In other words, they cannot be simply reproduced by repeated execution.
- **non-transient faults** (called Bohrbugs) whose activations cannot be masked with retries.
## Orthogonal Defect Classification
This schema focuses on the required fix for the fault rather than "subjectively perceived deficiency." The set of *exclusive* defect types is given below:
- Function: missing or wrong functionality, requires formal design change.
- Interface: addresses errors in communication between users, modules, or device drivers.
- Checking: Faulty or missing validation of data and values in the source code.
- Assignment: addresses faults in the source code such as faulty initialization.
- Timing / Serialization: errors that are corrected by improved management of shared and real-time resources.
- Build / Package / Merge: Problems due to mistakes in library systems, management of changes, and version control.
- Documentation: addresses errors in documentation and maintenance notes.
- Algorithm: Efficiency or correctness problems which can be fixed by re-implementation without design change.