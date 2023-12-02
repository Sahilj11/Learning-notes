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