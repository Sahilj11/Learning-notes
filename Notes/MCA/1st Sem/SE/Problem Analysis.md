## Structural Analysis
it is a set of techniques and graphic tools that allows the analyst to understand the system and its activities in a logical way. It is a systematic approach, which uses graphical tools that analyze and refine the objectives of an existing system and develop a new system specification which can be easily understandable by user.

#### **Attributes/Features**
- It is graphic which specifies the presentation of application.
- It divides the processes so that it gives a clear picture of system flow.
- It is logical rather than physical i.e., the elements of system do not depend on vendor or hardware.
- It is an approach that works from high-level overviews to lower-level details.

#### **Tools of Structured Analysis**
- Data Flow Diagram(DFD)
- Decision Tables
- Decision Tree
- Data dictionary
- Structured Charts
![](../../../statics/Pasted%20image%2020231202114657.png)

##### DFD
a means of representing a system at any level of detail with a graphic network of symbols showing data stores, data processes , and data sources/destinations. examine how data flows into, out of , and within the system.

**Obj of DFD**
- Represent the system data in hierarchical order with req lvl of details
- Depicts the processes according to the defined user req and scope of software 
- To provide the overview of transformation that occur in the input data within the system to produce the output
- DFD depicts the flow of data within the system and considers a system that transform the input into req outputs 
- WHen the system is complex then data needs to be transformed by various steps to produce the output . These steps are required to refine the requirement 

 **+ve of DFD**
- Provides the functional decomposition of proposed system
- provides the details of data flow in proposed system
- communicates the existing system knowledge to stakeholder

**Notation**
a) The **Process symbol** represents an activity that transforms or manipulates the data. They may be
shown as a circle, an oval, or a rectangle box
b) The **Data store** symbol represents data that is not moving.
c) The **Data flow** symbol represents movement of data. Data flow are generally shown as arrows
coming to or going from the edge of a process box.
d) The **External Entity** symbol represents sources of data to the system or destination of data from
the system.
![](../../../statics/Pasted%20image%2020231202115148.png)

**Levels**
In Software engineering DFD(data flow diagram) can be drawn to represent the system of different levels of abstraction. Higher-level DFDs are partitioned into low levels-hacking more information and functional elements. Levels in DFD are numbered 0, 1, 2 or beyond

**0-level**
DFD Level 0 is also called a context diagram. It’s designed to be an abstraction view, showing the system as a single process with its relationship to external entities.
represents the entire system as a single bubble with input and output data indicated by incoming/outgoing arrows
![](../../../statics/Pasted%20image%2020231202115458.png)

**1-Level**
DFD Level 1 provides a more detailed breakout of pieces of the Context Level Diagram. You will highlight the main functions carried out by the system, as you break down the high-level process of the Context Diagram into its subprocesses.

![](../../../statics/Pasted%20image%2020231202115548.png)

**2-level**
DFD Level 2 then goes one step deeper into parts of Level 1. It may require more text to reachthe necessary level of detail about the system’s functioning. . It can be used to plan or record the specific/necessary detail about the system’s functioning.

##### Decision Tables
tabular representation of inputs versus rules/cases/test conditions. It is a very effective tool used for both complex software testing and requirements management. Decision table helps to check all possible combinations of conditions for testing and testers can also identify missed conditions easily. The conditions are indicated as True(T) and False(F) values.

**Components**
- Condition Stub − It is in the upper left quadrant which lists all the condition to be checked.
- Action Stub − It is in the lower left quadrant which outlines all the action to be carried out to meet such condition.
- Condition Entry − It is in upper right quadrant which provides answers to questions asked in condition stub quadrant.
- Action Entry − It is in lower right quadrant which indicates the appropriate action resulting from the answers to the conditions in the condition entry quadrant.
![](../../../statics/Pasted%20image%2020231202174323.png)

**The entries in decision table are given by Decision Rules**
- Y shows the existence of a condition.
- N represents the condition, which is not satisfied.
- A blank - against action states it is to be ignored.
- X (or a check mark will do) against action states it is to be carried out.
![](../../../statics/Pasted%20image%2020231202174547.png)
![](../../../statics/Pasted%20image%2020231202174600.png)
+ves 
- Any complex business flow can be easily converted into the test scenarios & test cases using this technique.
- Decision tables work iteratively that means the table created at the first iteration is used as input table for next tables. The iteration is done only if the initial table is not satisfactory.
- Simple to understand and everyone can use this method design the test scenarios & test cases.
- It provide complete coverage of test cases which help to reduce the rework on writing test scenarios & test cases.
- These tables guarantee that we consider every possible combination of condition values. This is known as its completeness property.

##### Decision Tree
A decision tree is a decision support tool that uses a tree-like model of decisions and their possible
consequences.

A decision tree is a flowchart like structure in which each internal node represents a "test" on an attribute (e.g. whether a coin flip comes up heads or tails), each branch represents the outcome of the test, and each leaf node represents a class label (decision taken after computing all attributes). The paths from root to leaf represent classification rule.

A decision tree consists of three types of nodes:
1. Decision nodes – typically represented by squares
2. Chance nodes – typically represented by circles
3. End nodes – typically represented by triangles
Decision trees can also be drawn with flowchart symbols, which some people find easier to read
and understand.
![](../../../statics/Pasted%20image%2020231202175115.png)

Advantages
- Decision trees are able to generate understandable rules.
- Decision trees perform classification without requiring much computation.
- Decision trees are able to handle both continuous and categorical variables.
- Decision trees provide a clear indication of which fields are most important for prediction or classification.
Disadvantages
- Decision trees are less appropriate for estimation tasks where the goal is to predict the value of a continuous attribute.
- Decision trees are prone to errors in classification problems with many class and relatively small number of training examples.
- Decision tree can be computationally expensive to train. The process of growing a decision tree is computationally expensive

##### Data Dictonary
In DFD we give name to data flow, process , data store. although the names are descriptive of the data, the do not give detail. So a structured place is build to keep the detail, this place is called data dictionary. It’s a rigorous definition of all DFD. A data dictionary improves the communication between the analyst and the user.

**Advantages**
- It’s works as a valuable reference.
- It improves the communication between analysis and user.
- it can be use to compare the data description.
- Data dictionary can be use for cross referenced.
- It’s used in building a database.

##### Structured Charts
Structure Chart in software engineering represents hierarchical structure of modules. It breaks down the entire system into lowest functional modules, describe functions and sub-functions of each module of a system to a greater detail. They are used in structured programming to arrange program modules into a tree.

**Symbols**
- Modules:-It represents the process or task of the system. It is of three types.
	- Control Module:-  A control module branches to more than one sub module.
	- Sub Module:-  Sub Module is a module which is the part (Child) of another module.
	- Library Module:- Library Module are reusable and invokable from any module.
![](../../../statics/Pasted%20image%2020231202175709.png)
- Conditional Call:- It represents that control module can select any of the sub module on the basis of some condition.
![](../../../statics/Pasted%20image%2020231202175843.png)
- Loop(repetitive call of module):- It represents the repetitive execution of module by the sub module. A curved arrow represents loop in the module.
![](../../../statics/Pasted%20image%2020231202180017.png)
- Data Flow:- It represents the flow of data between the modules. It is represented by directed arrow with empty circle at the end.
![](../../../statics/Pasted%20image%2020231202180059.png)
- Control Flow:- It represents the flow of control between the modules. It is represented by directed arrow with filled circle at the end.
![](../../../statics/Pasted%20image%2020231202180131.png)
- Physical Storage:- Physical Storage is that where all the information are to be stored.
![](../../../statics/Pasted%20image%2020231202180200.png)

## Object Oriented Analysis
Any software development approach goes through the following stages −
- Analysis
- Design
- Implementation
The major phases of software development using object–oriented methodology are object-oriented analysis, object-oriented design, and object-oriented implementation.

#### Object oriented analysis
In this stage, the problem is formulated, user requirements are identified, and then a model is built based upon real–world objects. The analysis produces models on how the desired system should function and how it must be developed.

In the system analysis or object-oriented analysis phase of software development, the system
requirements are determined, the classes are identified and the relationships among classes are
identified.

The three analysis techniques that are used in conjunction with each other for object-oriented analysis are
object modelling, dynamic modelling, and functional modelling.

##### Object Modelling
Object modelling develops the static structure of the software system in terms of objects. It identifies the objects, the classes into which the objects can be grouped into and the relationships between the objects. It also identifies the main attributes and operations that characterize each class.

**Process**
- Identify objects and group into classes
- Identify the relationships among classes
- Create user object model diagram
- Define user object attributes
- Define the operations that should be performed on the classes
- Review glossary

##### Dynamic Modelling
After the static behaviour of the system is analyzed, its behaviour with respect to time and external changes needs to be examined. This is the purpose of dynamic modelling.

a way of describing how an individual object responds to events, either internal events triggered by other objects, or external events triggered by the outside world

##### Functional Modelling
Functional Modelling is the final component of object-oriented analysis. The functional model shows the processes that are performed within an object and how the data changes as it moves between methods. It specifies the meaning of the operations of object modelling and the actions of dynamic modelling. The functional model corresponds to the data flow diagram of traditional structured analysis

## System Modelling
