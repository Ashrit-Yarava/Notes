---
tags:
  - defects4j
  - faultlocalization
---
## Retrieve the list of test methods
```fish
java -cp /Users/ashrityarava/Desktop/Projects/defects4j/framework/projects/lib/junit-4.12-hamcrest-1.3.jar:$(defects4j export -p cp.test):../lib/gzoltarcli.jar com.gzoltar.cli.Main listTestMethods $(defects4j export -p dir.bin.tests) --outputFile tests.txt
```
## Identify the coverage
```fish
java -cp /Users/ashrityarava/Desktop/Projects/defects4j/framework/projects/lib/junit-4.12-hamcrest-1.3.jar:$(defects4j export -p cp.test):../lib/gzoltarcli.jar -javaagent:../lib/gzoltaragent.jar=destfile=gzoltar.ser,buildlocation=target/classes com.gzoltar.cli.Main runTestMethods --testMethods tests.txt --collectCoverage
```
## Generate the fault localization report
```fish
java -cp /Users/ashrityarava/Desktop/Projects/defects4j/framework/projects/lib/junit-4.12-hamcrest-1.3.jar:$(defects4j export -p cp.test):../lib/gzoltarcli.jar com.gzoltar.cli.Main faultLocalizationReport --buildLocation target/classes/ --granularity line --inclPublicMethods --dataFile gzoltar.ser --outputDirectory . --family "sfl" --formula "Ochiai" --formatter txt
```