# Shell Scripting

## Objectives
* What is a Shell
* Using the Shell
    * Navigating the file system
    * File Manipulation
    * Running programs
    * Piping input and output 
* Writing Shell Scripts
* Scheduling Tasks/Programs 

#### Shell?
* Software that provides an interface for a user to some other software or operating system
* Can be an interface between the operating system and the services of the kernel of this operating system
* Synonym: Command Line Interface (CLI)
* Uses a Read-Evaluate-Print Loop (REPL) 
* The shell allows us to fcombine existing tools into powerful pipelines and handle large volumes of data automatically.

#### Shell commands
* cd - change directory
* ls - lists files in current directory
* mv - move files around i.e. mv myfile.txt destination-directory
* rm - delete files i.e. rm filename
* nano myScript.py - creates a file named myScript

#### IO redirection 
* Powerful feature of the shell: the ability to direct input and output to and from files, and in between programs. 
```python
    import sys
    myList = sys.stdin.read().split()
    print("There were", len(myList), "words.")
```
Use input redirection to send this file to standard input:
> python3 myScript.py < someText.txt
Redirect standard output so that the statements (print) will get saved in file (report.txt):
> python3 myScript.pt < someText.txt > report.txt
