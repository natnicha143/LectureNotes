# 1 | Shell Scripting
**Concept of a shell:**
* Provides an interface for a user to the OS or other software
* Interface between the OS and services of the kernel
* Shell == Command Line Interface
* The most common shell is BaSH(Bourne again Shell)
**Commands in Windows & Linux:**
BaSH
* pwd : print working directory
* ls : lists files 
    * ls -l : uses long listing format with more info
    * ls -R : will recursively go through subdirectories and list their contents in a tree-like structure
* mv : move files around
    * mv myfile.txt destination-directory
    * mv myfile.txt myrenamedfile.txt
    * my myfile.txt ../ : move to parent directory
* rm : delete files
    * rm filename
    * rm -d directoryname (only works if dir is empty)
    * rm -r directoryname (deletes all contents & itself)
Windows
* cd : print directory + change directory
    * cd ~ : puts you in home directory
    * cd ~username: puts you in username's home directory
    * cd dir (without a /) : subdirectory
    * cd .. : parent directory
    * cd \ : root directory (top directory)
* dir : lists files in directory
* del : removes files
**Common Environment Variables in BaSH**
* PATH : stores a list of directory paths. When a user types a command each directory in PATH list is examined for the command.
* HOME : home directory for the current user
* PS1 : defines how the prompt is displayed in BaSH
* TEMP : location where processes can store temp files 
**I/O Redirection in BaSH**
* Send file to standard input : 
> python3 myScript.py < someText.txt
* Redirect standard output to get saved in a file :
> python3 myScript.py < someText.txt > report.txt
* Redirect standard output of one program to input of next :

* Redirects output of the ls-a command and sends it to the standard input of the python interpreter 
> ls -a | python3 myScript.py
* Allows scrolling up and down of output :
> somecommand | less
* Grep is used to search for a particular string or pattern in a file and display the lines that match :
> somecommand | grep "keyword"
**Basic shell scripting** 
create var : STRING
echo $STRING 

function_name(){
    list of commands
}
**File permissions**
Changing file and folder permissions:
> chmod
    > rwx (read, write, exe)
    > rw- (read, write)
    > r-x (read, execute)
    > r-- (read only)
    > -wx (write and execute)
    > -w- (write only)
    > --x (execute only)
    > --- (none)
e.g.: chmod + 755 filename (file owner, file group members, other users)
# 2 | Sofware System testing
**Purpose of testing**
* To generate more reliable sfotware
* Make software fail
* Find bugs and fix failures
* Verifying that the software product is fit for use
**Defects and failures**
* Human Error -> Defect (fault, bug) -> executed -> failure
* Not all defects result in failures. A defect can turn into a failure when the environment is changed. -
    * New hardware platform, alterations in source data, or interacting with different software.
**Phased process model vs agile approach**
Phased process : Waterfall model 
* Most testing occurs after system requirements have been defined then implemented in testable programs. 
* Results in testing phase being used as a project buffer to compensate for project delays, thereby compromising the time devoted to testing.

Agile approach :
* Requirements, programming, and testing are done concurrently.
* "Test-driven software development" model
1. Unit tests
2. Tests fail initially
3. More code is written
4. More tests pass
Goal : to achieve continuous integration where software updates can be published to the public frequently. 
* Meets the requirements that guided its design and development
* Responds correctly to all kinds of inputs
* Performs its functions within an acceptable time
* Is sufficiently usable
* Can be installed and run in its intended environments
* Achieves the general result its stakeholders desire
**Static vs dynamic testing**
Static: reviews and inspects code
Pros:
* Absolutely complete analysis
* Identify the issues directly in source code 
* Pre-defined patterns identified in source
Cons:
* Potential for many false-positives
* Extremely resource intensive analysis
* Inability to contextualize issues
Dynamic: executin code with test cases
Pros:
* Lower false-positive rate
* Well established testing tools
* Ability to execute layered testing
Cons:
* Incomplete
* Cannot point to source-code where errors exist
* Prone to inconsistency issues 

**Whitebox and blackbox test**
White-box: test internal structure or functions

Black-box: examining functionality without any knowledge of internal implementation, without seeing the source code 
**Unit test and Python module**
Unit test : white-box testing
```python
class TestHelperFunction(unittest.TestCase):
    def test_same_function(self):
        self.assert_Equal(word_ladder.same("lead", "lead"), 4)
```
Assertion in unittest :
assertEqual(a, b) 
* Checks a == b
assertNotEqual(a, b)
assertTrue(a) 
* Bool(a) is True
assertNotIn(a, b)

```python
def test_add_floats(self):
    result = add(10.5, 5.1)
    self.assertEqual(result, 15.6)
```
*Test methods should be prepended by test__*

**Mocking in unit test and how it works**
* Mocking is replacing the part of the application you are testing with a dummy version of that part called a mock.
* For increased speed
* For avoiding undesired side effects during testing
* import unittest.mock

**Creation of test cases**
```python
def add(num):
    add = x + y
    return add
```
**Integration testing**
* It is the phase in which individual software modules are combined and tested as a group. It occurs after unit testing and before system testing. 
    - Test the interface between modules
    - 
**System testing**
* Testing on a complete, integrated system to evaluate the system's compliance with its specified requirements.
* Black-box testing
* Purpose: detect any inconsistencies between the software units that are integrated together or between integrated units and the hardware

**Acceptance testing**
* Conduct operational readiness (pre-release) of a product, service or system as part of a quality management system.
* Focuses on operational readiness of system to be supported, or become part of the production environment
* Portability, working as expected, does not damage or corrupt its OS environment.
**How to create testable software**
* clean, neat code
* refactor code - change internal structure but not functionality
* clear understanding of the function of a module and its interaction with other modules
* avoid large amount of global variables
* support unit test
* large amount of assertions
# 3 | Coverage testing
**Concept of test coverage**

**Why do we need coverage test**
Testing is based on samples
* Cannot run all possible tests
* Need to know that all areas of design are tested
* A test suite is not measured by its size
Solution: Coverage analysis
**Goals of coverage**
* Measure the "quality" of a set of tests
* Supplement test specifications by pointing to untested areas
* Help create regression suites
* Provide a stopping criteria for unit testing
**Different coverages: function, statement, branch, condition, path**
Function - has each function been called?
Statement - has each statement been executed?
branch coverage - has each branch of each control structure (if and case statements) been executed?
condition - has each boolean sub-expression evaluated both to true or false?
**Why codes are not covered**
* It is difficult to detect omissions:
    E.g. hard disk is full when writing a file to the disk
* Need to figure out other solutions
    - Fault injection - e.g. make a hard disk fail
    - Partition the input domain in a diff way
        * Use specification rather than automatic coverage
* Infeasible: never going to get executed
* Not worthwhile: same function tested in other tasks
* Inadequate test suite
    - Improve the test suite
    - Deliver the product for cost-benefit issue

**Interpretation of Python coverage test results**

**Basic concept of regression test**
* A regression suite is a set of tests that are run on the application after every software or data changed, and every night or every weekend, in order to check that no new bugs have been introduced
*vital*: Every bug fix on the average, introduces one fifth of a bug.
**Basic concept of random test**
Development of tests using a black box method, in which test cases are chosen to match the functional cross-section, usually using an algorithm of pseudo-random selection. 
* Where programs are tested by generating random, independent inputs.

**Three types of oracles**
Weak oracle: 
Medium oracle:
Strong oracle:


# 4 | Software configuration management
**Why SCM is needed**

**What is included in SCM**

**Configuration identification**

**Configuration control**

**Why version control is needed**

**Different types of version control systems**

**Basic concept of graph structure**

**Git command**


# 5 | Regular Expression
**Basic syntax to complete workshop tasks or similar**
```python
import re
x = re.search("cat"."A cat and a rat can't be friends.")
print(x)


```

# 6 | Databases
**Concept of database management systems**

**SQL as Data Manipulation Language**

**Basic SQL syntax for single table data insertion, query and update**

**Python for SQLite: create a table, insert data, update a database, query the database. Basic syntax to complete workshop tasks or similar**

```python
import sqlite3
connection = sqlite3.connect("company.db")
cursor = conntection.cursor()

sql_command = """CREATE TABLE employee(
    staff_num INTEGER PRIMARY KEY,
    fname VARCHAR(20),
    gender CHAR(1)
); """

cursor.execute(sql_command)
```
* All access to db is via cursor object
Updating db:
never forget..
connection.commit()
connection.close()


# 7 | Python and Excel
**Excel related concept**

**openpyxl module and programming**
    * Accessing workbook and worksheet
```python
import openpyxl
wb = openpyxl.load_workbook('.xlsx')
sheet = wb.get_sheet_by_name('Microsoft')
```
    * Accessing worksheet cells
```python
sheet['A1']
or
sheet['A1'].value
```
    * Slicing
    * Iteration through worksheet
    * Creating workbooks and worksheets
```python
wb = openpyxl.Workbook()
wb.get_sheet_name()
sheet = wb.active
sheet.title

sheet.title='Hello world sheet'
wb.get_sheet_names()
wb.save('example_copy.xlsx')
```
    * Write values to cells 

# 8 Numpy and Scipy
**Typical Scipy packages**
These include: 
 NumPy/SciPy – numerical and scientific function libraries. 
 Numba – Python compiler that support JIT compilation.
 ALGLIB – numerical analysis library.
 Pandas – high-performance data structures and data analysis tools. 
 PyGSL – Python interface for GNU Scientific Library. 
 ScientificPython – collection of scientific computing modules.

**What is included in Numpy**
* a powerful n-dimensional array object
* sophisticated functions
* toold for integrating C/C++ and fortran code
* useful linear algebra, fourier transform, and random number capabilities
**ndarray object and programming**