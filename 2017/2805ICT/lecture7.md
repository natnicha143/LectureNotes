# Software Archiectures
* Concurrent, parallel, multiprocess
* Pipes and filters
* Distributed (Client/Server, etc)
* N-layered
    * 3 tier/2 tier

## Software arch
* The design process for identifying the sub-systems making up a system and the framework for sub-system control and communication is archiectural design.
* The output of this design process is a description of the software architecture.

## Arch design is..
* An early stage of the system design process
* Links specification and design processes
* Often carried out in parallel with some specification activities
* It involves identifying major system components and their communications


## Architectural rep
* Block diagrams showing entities and relationships: used for documenting software architectures.
* Critized: lack semantics, not show relationship types between entities nor the visible properties of entities in the architecture.

## Box and line diagrams
* Very abstract - do not show nature of component relationships nor externally visible properties of sub-systems.
* However, useful for communication with stakeholders and for project planning.

## Use of architectural models
* As a way of facilitating discussion about the system design
    * 

## Archiecture and system characteristics
* Performance
 * Localise critical operations and minimise communications.
* Security
    * Use a layered architecture with critical assets in the inner layers.
* Safety
    * Localise safety-critical features in a small number of sub-systems.
* Availability
    * Include redundant components and mechanisms for fault tolerance. 
* Maintainability 
    * Use fine-grain, replacable components. 


## The Model-View-Controller (MVC) pattern
Name: MVC
Desc: Separates presentation and interaction from the system data. The system is structured into 3 logical components that interact with each other. 
* The model component: manages system data and associated operations on that data.
* The view component (the even handler): defines and manages how the data is presented to the user.
* The controller component: manages user interfaction (e.g., key presses, mouse clicks etc.) and passes these interaction to the View and the Model.
Example: Archiecture of a web application system can be organized using the MVC pattern.
Used when: There are multiple ways to view and interact with data. Also used when the future requirements for interaction and presentation of data are unknown.
Advantages: Allows data to change independently of its own and vice versa. Supports presentation of the same data in different ways with changes made in one representation shown in all of them. 
Disadvantages: Can involve additional code and code complexity when the data model and interactions are simple. 

## Layered Architecture
* Used to model the interfacing of sub-systems. 
* Organises the system into set of layers each of which provide a set of services.
* Supports the incremental development of sub-systems in different layers. 

## The layered architecture pattern
Name: Layered architecture
Desc: Organizes the system into layers with related functionality associated with each layer. A layer provides services to the layer above it, so the lowest-layers represent core services that are likely to be used throughout the system. 
When used: 
* When building new facilities on top of existing systems.
* When the development is spread across several teams with each team responsible for a layer of functionality 
* When there is a requirement for multi-level security. 
Advantages: 
* Allows placement of entire layers so long as the interface is maintained. 
* Redundant facilities (e.g., authentication) can be provided in each layer to increase the dependability of the system.
Disadvantages:
* Performance: because of multiple levels of interpretation of a service request as it is processed at each layer.

## A generic layered architecture
1. User interface
2. User interface management | Authentication and authorization
3. Core business logic/application functionality | System utilities
4. System support (OS, database etc.)

## Architecture of the LIBSYS system
1. Web browser interface
2. LIBSYS login | Forms and query manager | Print manager
3. Distributed search | Document retrievel | Rights manager | Accounting
4. Library index
5. DB1 | DB2 | DB3 | DB4 | DBn

## Repository architecture
* When large amounts of data are to be shared, the repos model of sharing is most commonly used as this is an efficient data sharing mechanism.
Name: Respository
Desc: All data in a system is managed in a central respos that is accessible to all system components. Components do not interact directly, only through the respository. 
Example: An IDE where the components use a repository of system design information. Each software tool generates information which is then available for use by other tools. 
When used:
* A system in which large volumes of information are generated that has to be stored for a long time. 
* In data-driven systems where the includsion of data in the repos **triggers** an action or tool. 
Advantages:
* Components can be independent 
Disadvantages:
* Single point of failure - so problems in the repos affect the whole system.
* Inefficiencies in organizing all communication through the repos.
* Distributing the repos across several computers may be difficult.

## The Client-server pattern - POPULAR
Name: Client-server
Example: A film and video/DVD library organized as a client-server system. 
When used: 
* When data in a shared DB has to be accessed from a range of locations.
* Because servers can be replicated, may also be used when the load of a system is variabe.
Advtanges:
* __Servers can be distributed across a network__.
* General functionality can be __available to all clients__ and does not need to be implemented by all services.
Disadvantages: 
* Each service is a single pont of failure, so susceptible to denial of service attacks or server failure.
* Performance may be unpredictable because it depends on the network as well as the system.
* May be management problems if servers are owned by different organizations.

Thin client:
* Client implements only the GUI
* Server implements business logic and data management
Thick client:
* Client implements both the GUI and the business logic
* Server implements data management
Disadvantages of thick clients:
* No central place to update the business logic
* Security issues: Server needs to trust clients
    * Access control and authentication needs to be managed at the server
    * Clients need to leave server database in consistent state
    * One possibility: Encapsulate all database access into stored procedures
* Does not scale to more than several 100s of clients
    * Larger data transfer between server and clients
    * More than one server creates a problem: x clients, y servers: x*y connections


## Pipe and filter architecture - POPULAR
Name: Pipe and filter
Desc: The processing of the data in a system is organized so that each processing component (filter) is discrete and carries out one type of data transformation. The data flows (as in pipe) from one component to another for processing. 
Example: Data flow system could be a pipe and filter system used for processing invoices. 
When used:
* Data processing applications (both batch- and transaction-based) where inputs are processed in separate stages to generate related outputs.
Advantages: 
* Easy to understand and supports transformation reuse.
* Workflow style matches the structure o fmany business processes.
* Evolution by adding transformations is straightforward.
* Can be implemented as either a sequential or concurrent system.
Disadvantages:
* Format for data transfer has to be agreed upon between communication transformations.
* Each transformation must parse its input and unparse its output to the agreed form. 
* This increases system overhead and may mean that it is impossible to reuse functional transformations that use incompatible data structures.

## Application architectures

Examples:
* Transaction processing systems
    * E-commerce systems
    * Reservation systems
* Language processing systems
    * Compilers
    * Command interpreters
When used:
* As a starting point for arch design
* As a design checklist
* As a way of organising the work of the development team
* As a means of assessing components for reuse
* As a vocab for talking about application types

## Components of Data-Intensive Systems
Three separate types of functionality: 
* Data management
* Application logic
* Presentation
    * MVC pattern from software engineering
The system architecture determines whether these three components reside on a single system(tier) or are distributed across several tiers.

## Single-tier architectures
All functionality combined into a single tier, usually on a mainframe
* User access through dumb terminals
Advantages:
* Easy maintenance and administration
Disadvtanges:
* Today, users expect GUI
* Centralized computation of all of them is too much fo a central system

## The three-tier architecture
Thick client.

DBMS -> Network -> Application logic -> Network -> Client | Client

Architecture:
Presentation tier (Client program: web browser) - HTML, Javascript, XSLT
* Primary interface to user
* Needs to adapt to different display devices (PC, PDA, Cell phone, tablet, voice access?)
Middle tier (Application server) - Tomcat, Apache (JSP, Servlets, Cookies, CGI)
* Implements business logic (implements complex actions, maintains state between different steps of a workflow)
* Accesses different DBMS
Data management tier (DBMS) - Oracle, DB2 (XML, Stored Procedures)
* One or more standard DBMS

Advantages:
* Heterogeneous systems
* Thin clients
* Integrated data access
* Scalability
* Software development

## Information Systems architecture
These are transaction-based systems as interaction with these systems generally involve database transactions. 
Layers include:
* The user interface 
* User communications | Authentication and authorization
* Information retrieval | and modification 
* System database | Transaction management database 

### Web-based information systems
* 