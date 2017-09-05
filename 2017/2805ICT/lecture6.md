# Software Architecture
* Design Patterns (creational, structural, behavioural)
- Model/View Controller
* Software Architectures
- Concurrent, parallel, multiprocess
- Pipes and filters
- Distributed (Client/Server, etc)
- N-layered 
    * 3-tier/2-tier

## Reusability 
* Good software design solves a specific problem but is general enough to **address future problems**
Goal: design the software to be reusable across application domains and designs
By: using design patterns and frameworks whenever possible

## Design Patterns and Frameworks
* Design Pattern:
- A small set of classes that provide a template solution to a recurring design problem
- Reusable design knowledge on a higher level than datastructures (link lists, binary trees, etc)
* Framework:
- A moderately large set of classes that collaborate to carry out a set of responsibilities in an application domain.
    * Example: User Interface Builder
    * Example: Laravel for PHP 
* Provide architectural guidance during the design phase
* Provide a foundation for software components industry

## Design Patterns
* A design pattern describes a problem which occurs over and over again in our environment
* Then it describes the core of the solution to that problem, in such a way that you can use this solution a million times over, without ever doing it the same twice.

## Expert Pattern: Example
* Which class should hold the responsibility to compute the total amount of a sale?
* We designate the method getTotal() to the Sale class. 

* Who shall know the sub-total of a sale line item?
- SaleItemLine knows how to find the sub-total(quantity * unitary price of product)
    * We designate the operation getSubTotal() to the class SaleItemLine
- A Product is an expert in its unitary price, we allocate the getter methods getUnitaryPrice() to the class Product

## Pattern Categories
1. Creational: Creation of objects. Separate the operations of an application from how its objects are created.
* Abstract factory
* Builder
* Factory method
* Prototype 
* Singleton 
2. Structural: Concern about the composition of objects into larger structures. To provide the possibility of future extension in structure.
* Adapter
* Bridge
* Composite
* Decorator
* Facade
* Flyweight
* Proxy
3. Behavioural: Define how objects interact and how responsibility is distribute among them. Use inheritance to spread behaviour across the subclasses, or aggregation and composition to build complex behaviour from simpler components. 
* Chain od Responsibility
* Command
* Interpreter
* Iterator
* Mediator
* Memento
* Observer
* State
* Stategy
* Template Method
* Visitor 

## Pattern description format
Context:
* The general situation in which the pattern applies
Problem:
* The main difficulty to be tackled.
* Criteria for a good solution.
Solution:
* Recommended way to solve the problem.
Antipattern(optional):
* Erroneous or inferior solution.

## The abstraction-occurence pattern
Context:
* Often in a domain model you find a set of related objects (occurrences). The members of such a set share common information but also differ from each other in important ways.
* Example: 
- All the episodes of tv series
- All the copies of the same book in a library
Problem:
* Find the best way to represent such sets of occurrences in a class diagram.
* Represent the objects without duplicating the common information.
* Avoid inconsistency when changing the common information.
Solution:
* Create an <<Abstraction>> class that contains the data that is common to all the members of a set of occurrences.
* Then create an <<Occurrence>> class representing the occurrences of this abstraction.
* Connect these classes with a 1:M association 
Antipattern:
3 examples,
* LibraryItem: name, author, isbn, publicationDate, libOfCongress, barCodeNumber
* LibraryItem: name, author, isbn, publicationDate, libOfCongress, barCodeNumber with two children:
    - GulliversTravels & MobyDick
* Title: name, author, isbn, publicationDate, libOfCongress which parents:
    - LibraryItem: barCodeNumber

General idea: <<Abstraction>> 1 ... * <<Occurrence>>
Library example: <<Title>> 1 ..... * <<LibraryItem>>

## The general-hierarchy pattern
Context:
* Occurs frequently in class diagram. There is a set of objects that have a naturally hierarchical relationship.
* Example:
    - Managers and subordinates
    - Folder, Subfolder and Files
Problem:
* Draw a class diagram to represent a hierarchy of objects
* We want flexible ways of representing the hierarchy
    - that prevents some objects from having subordinates
* All objects share common features (properties and operations)
Solution:
* Create an abstract <<Node>> class to represent the features possessed by each object in the hierarchy - one such feature is that each node can have superiors
* Then create at least two subclasses of the <<Node>> class.
    - <<SuperiorNode>> must be linked by a <<subordinate>> association to the superclass;
    - <<NonSuperiorNode>> must be a leaf.
    - The multiplicty of the <<subordinates>> association can be optional-to-many or many-to-many


