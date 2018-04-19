A.	Run maven cucumber java

1. Create a sample maven project with the structure posted below 

└── cucumber-jvm-maven
    ├── pom.xml
    └── src
        ├── main
        │   └── java
        │       └── com
        │           └── samplemavencucumber
        │               └── bdd
        │                   └── calculator
        │                       └── Calculator.java
        └── test
            ├── java
            │   └── com
            │       └── samplemavencucumber
            │           └── bdd
            │               ├── runner
            │               │   └── RunCalculatorTest.java
            │               └── steps
            │                   └── CalculatorSteps.java
            └── resources
                └── cucumber
•	└── calculator.feature

2. Execute the maven cucumber java tests as JUnit 
    2.1. Right click the runner file ..... run as JUnit test 
            This executes the tests kept in the runner and results are generated in target folder. 

3. Debug the code
   3.1. Keep break points in the code. 
           Right click the runner .....  debug as JUnit test 
           This switches the IDE in debug mode and we can debug, add checkpoints to complete the 
           test flow. 

4. Execute the maven cucumber selenium java tests as maven build
   4.1. mvn clean test  
           This runs the project as a maven build and once BUILD SUCCESS, executes the tests, completes  
           the browser session and prints test result board.

5. Right click tetng.xml ..... perform debug action  


C.	Executing maven cucumber test and generation of report
$ mvn clean test
[INFO] Scanning for projects...
[INFO]   
[INFO] -------------------------------------------------------
[INFO] Building cucumber-jvm-maven 1.0-SNAPSHOT
[INFO] -------------------------------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.3:clean (default-clean) @ cucumber-jvm-maven ---
[INFO]
[INFO] --- maven-resources-plugin:2.3:resources (default-resources) @ cucumber-jvm-maven ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /home/jakub/development/blog/cucumber-jvm-maven/src/main/resources
[INFO]
[INFO] --- maven-compiler-plugin:3.1: compile (default-compile) @ cucumber-jvm-maven ---
[INFO] No sources to compile
[INFO]
[INFO] --- maven-resources-plugin:2.3:testResources (default-testResources) @ cucumber-jvm-maven ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 1 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ cucumber-jvm-maven ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 1 source file to /home/jakub/development/blog/cucumber-jvm-maven/target/test-classes
[INFO]
[INFO] --- maven-surefire-plugin:2.10:test (default-test) @ cucumber-jvm-maven ---
[INFO] Surefire report directory: /home/jakub/development/blog/cucumber-jvm-maven/target/surefire-reports

[INFO] -------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] -------------------------------------------------------
[INFO] Total time: 20.603s
[INFO] Finished at: Sun Jul 20 23:22:04 BST 2014
[INFO] Final Memory: 12M/211M
[INFO] -------------------------------------------------------

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.czeczotka.bdd.runner.RunCalculatorTest
Feature: Calculator
  As a user
  I want to use a calculator
  So that I don't need to calculate myself

  Scenario: Add two numbers     ←[90m# cucumber/calculator.feature:6←[0m
    ←[32mGiven ←[0m←[32mI have a calculator←[0m   ←[90m# CalculatorSteps.i_have_a_calculator()←[0m
    ←[32mWhen ←[0m←[32mI add ←[0m←[32m←[1m2←[0m←[32m and ←[0m←[32m←[1m3←[0m          ←[90m# CalculatorSteps.i_add_and(int,int)←[0m
    ←[32mThen ←[0m←[32mthe result should be ←[0m←[32m←[1m5←[0m ←[90m# CalculatorSteps.the_result_should_be(int)←[0m

1 Scenarios (←[32m1 passed←[0m)
3 Steps (←[32m3 passed←[0m)
0m0.226s

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.092 sec

