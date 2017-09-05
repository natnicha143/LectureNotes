# Coverage Testing 
* Making sure that test cases sufficiently test code

## Overview
* Coverage Testing
    - Function Coverage
    - Statement Coverage
    - Branch Coverage 
    - Condition Coverage
* Coverage Testing Tools
* Random Testing
    - Types of Random Testing
    - Oracles

### Why coverage?
* Testing is based on samples
- Cannot run all possible tests
- Need to know that all areas of design are tested
- A test suite is not measured by its size
* SOLUTION: coverage analysis~~~~~

### Coverage 
* Code coverage is a measured used to describe the degree to which the source code of a program is executed when a particular test suite runs 
* The main ideas behind coverage:
    - Systematically create a list of tasks (the testing requirements)
    - Check that each task is covered during the testing 

### Test coverage
* A program will high code coverage, measured as a percentage, has had more of its source code executed during testing which suggests it has a lower chance of containing undetected software bugs compared to a program with low code coverage.
* Many different metrics can be used to calculate code coverage
    - The percentage of program subroutines.
    - The percentage of program statements called during execution of the test suite.

### Goals of coverage
* Measure the "quality" of a set of tests
* Supplement test specifications by pointing to untested areas
* Help create regression suites
* Provide a stopping criteria for unit testing

### Coverage criteria
* Function coverage - has each function been called?
* Statement coverage - has each statement been executed?
* Branch coverage - has each branch of each control structure been executed?
* Condtion coverage - has each boolean sub-expression evaluated both to true or false?

### When code coverage does not work
* It is difficult to detect omissions
    - E.g. hard disk is full when writing a file to the disk
* Need to figure out other solutions
    - Fault injection - e.g. make a hard disk fail
    - Partition the input domain in a different way
        - Use specification rather than automatic coverage 

### Codes not covered
* Infeasible: Never going to get executed
* Not worthwhile:
    - Same function tested in other tasks
* Inadequate test suite
    - Improve the test suite
    - Deliver the product for cost-benefit issue

### Regression
* A regression suite is a set of tests that are run on the application after every software or data change, in order to check that no new bugs have been introduced 
* This is vital because every bug fix, on the average, introduces one fifth of a bug.

### Random test
* Random testing is a black-box software testing technique where programs are tested by generating random, independent inputs.
* Results of the output are compared against software specifications to verify that the test output is pass or fail.
* In case of absence of specifications, the exceptions of the language are used which means if an exception arises during test execution then it means there is a fault in the program.

### Pros and Cons
Pros:
* Easily estimating software reliability from test outcomes. Test inputs are randomly generated according to an operational profile, and failure times are recorded.
* Do not have bias: unlike manual testing, it does not overlook bugs because there is misplaced trust in some code.
* Use of random test inputs may save some of the time and effort
Cons:
* Semantically redundant inputs
* can only find basic bugs
* Effective oracle is seldom available

Example:
```python
import random

def myAbs(x):
    if x > 0:
        return x
    else:
        return x
# else return -x
def testmyAbs():
    for i in range(10):
        x = random.randint(-100000, 100000)
        print(myAbs(x)>=0)

testmyAbs()
```
### Generative random testing
* Generative random testing
    - No domain knowledge, random test case generator takes its pseudo-random numbers
    - Pseudo-random numbers parameterized an algorithm(creidt card number generation, need to follow some equation)
    - Generate valid sequences of API calls or testing a web browser where we need to actually generate well-formed HTML in order to test certain parts of the browser.

### Mutation based random testing
* Inputs are created by randomly modifying existing non-randomly created inputs to the software under test.
* Have a separate source of input which is the existing test case.
* It's going to end up test cases that in some sense are kind of in the same neighbourhood as the original input.
* Never reached this part of the input domain using any kind of a generative random test case generator. 

### How to mutate test cases?
* Flip bits (change a word document to make MS word crash)
* Modify selected fields (Take the HTTP request size and replace it with some random number)
* Add, remove, and replace tokens(modify the parser of grammar).

## Oracles
### Weak
* Detecting whether or not the application crashed: the system under test violated some rules, such as illegal memory accesses, write to memory owned by the kernel 

### Medium
* Enhanced execution environments
* For example, the program terminates if it attempts to access values beyounf the end of an array

### Strong
* Guarantee actual correct operation
* Reference implementation which is an implementation of the specification which you are after that you can trust. E.g., use regular C Python implementation as a reference to implement an extremely high performance Python compiler.

