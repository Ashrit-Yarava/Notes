---
Author: Alexandra van der Spuy
Year: 2025
tags:
  - faultlocalization
Read: true
---
Current bug classifications primarily make use of the repairs as proxies but they are unable to capture the nature of the faults. To tackle this issue, the authors propose a new schema that captures this detail and make use of a 8 label classification system. The faults schema is given below:
- *Unconditional control-flow target faults*: These kinds of faults deal with wrong statement orders, jumps, or method calls.
	- *Statement Order faults* (`order`): A sequence of consecutive edges connect multiple nodes in the wrong order, but the set of statements is correct. The repair simply rearranges the order of statements.
	- *Jump faults* (`jump`): Rewriting of the jump statement. (changing the value of a return statement).
	- *Method Call faults* (`call`): Wrong method calls / uncalled methods.
- *Control-flow predicate faults*: The predicate is incorrect in a conditional statement.
	- *Predicate node faults* (`pred`): The condition is incorrect but the variables used are correct.
	- *Predicate existence faults* (`guard`): This fault type occurs when the program either has too many conditionals causing the correct path to be guarded or not enough and a path is taken that should not be.
	- *Predicate block faults* (`block`): An entire conditional block is missing (condition and guarded code).
- *Data Flow Faults*:
	- *Definition Faults* (`def`): Incorrect use of a variable.
	- *Use faults* (`use`): Incorrect value is modified.
The data is available at [https://doi.org/10.5281/zenodo.15032242](https://doi.org/10.5281/zenodo.15032242). The authors manually classified 488 faults.