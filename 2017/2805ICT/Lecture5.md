# Paradigms of Software Design
## Main concepts
* Design Paradigms
    * Function oriented design (top-down structural decomposition & modularisation)
    * Object oriented design
    * Data centric design
    * Case studies

### Decomposition
A technique used to master complexity ("divide and conquer")
* Functional decomposition
- The system is decomposed into modules
- Each module is a major processing step (function) in the application domain
- Modules can be decomposed into smaller modules

* Object-oriented decomposition
- The system is decomposed into classes("objects")
- Each class is a major abstraction in the application domain
- Classes can be decomposed into smaller classes

### Reusability
A good software design solves a specific problem but is general enough to address future problems (for example, changing requirements)
* Experts do not solve every problem from first principles
- They reuse solutions that have worked for them in the past
* Goal for the software engineer:
- Design the software to be reusable across application domains and designs
* How?
- Use design patterns and frameworks whenever possible

### Software Design
Properties:
* Well defined subsystem
* Well defined purpose
* Can be separately compiled and stored in a library.
* Module can use other modules 
* Module should be easier to use than to build vi. Simpler from outside than from inside. 

### Modularity
* Modularity is the single attribute of software that allows a program to be intellectually manageable.
* It enhances design clarity, which in turn eases implementation, debugging, testing, documenting and maintenance of software product.


### Function oriented design
Function oriented design is an approach to software design where the design is decomposed into a set of interacting units where each unit has a clearly defined funtion. Thus, system is designed from a functional viewpoint. 

### Functional Procedure Layers
Functions are built in layers, additional notation is used to specify details. 
**Level/layer 0**
* Function or procedure name
* Relationship to other system components (e.g., part of which system, called by which subroutines, etc.)
* Brief description of the function purpose
* Author, date
**Level/layer 1**
* Function parameters (problem variables, types, purpose)
* Global variables
* Routines called by the function
* Side effects
* Input/Output Assertions/Pre-conditions/Post-conditions/Invariants
**Level/layer 2**
* Local data structures
* Timing constraints
* Exception handling (conditions, responses, events)
* Any other limitations
**Level/layer 3**
* Body (structured chart, english pseudo code, decision tables, flow charts, etc)

