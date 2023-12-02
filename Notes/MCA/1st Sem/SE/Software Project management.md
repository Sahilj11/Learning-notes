## Intro

- A Software Project is the complete procedure of software development from requirement gathering to testing and maintenance, carried out according to the execution methodologies, in a specified period of time to achieve intended software product.

### Need for software project management

![](../../../statics/Pasted%20image%2020231202061915.png)
The image above shows triple constraints for software projects. It is an essential part of software organization to deliver quality product, keeping the cost within client’s budget constrain and deliver the project as per scheduled. There are several factors, both internal and external, which may impact this triple constrain triangle. Any of three factors can severely impact the other two.
Therefore, software project management is essential to incorporate user requirements along with budget and time constraints

### Software management activities

Software project management comprises of a number of activities, which contains planning of project,
deciding scope of software product, estimation of cost in various terms, scheduling of tasks and events,
and resource management. Project management activities may include:

- Project Planning
- Scope Management:- It defines the scope of project; this includes all the activities, process need to be done in order to make a deliverable software product. Scope management is essential because it creates boundaries of the project by clearly defining what would be done in the project and what would not be done. During Project Scope management, it is necessary to
  - Define its scope
  - Define its control and verification
  - Divide project into small parts for ease of management
  - verify scope
- Project Estimation
  - Software Size estimation:- may be estimated either in terms of KLOC (Kilo Line of Code) or by calculating number of function points in the software.
  - Effort Estimation:- The managers estimate efforts in terms of personnel requirement and man-hour required to produce the software.
  - Time Estimation:- Software tasks are divided into smaller tasks, activities or events by Work Breakthrough Structure (WBS). The tasks are scheduled on day-to-day basis or in calendar months. The sum of time required to complete all tasks in hours or days is the total time invested to complete the project.
  - Cost Estimation:- For estimating project cost, it is required to consider
    - Size of software
    - Software Quality
    - Hardware
    - Travel Involved etc.

## Project Estimation technique

We discussed various parameters involving project estimation such as size, effort, time and cost.
Project manager can estimate the listed factors using two broadly recognized techniques-

- Decomposition Technique:- assume that software as product of various composition
  - Two main models
    - Line of code:-
    - Functional points:- number of functional points in software
- Empirical Estimation Technique:- uses empirically derived formulae to make estimation.These formulae are based on LOC or FPs
  - COCOMO:- COCOMO stands for COnstructive COst MOdel, developed by Barry W. Boehm. It divides the software product into three categories of software: organic, semi-detached and embedded.
  - Putnam Model:- This model is made by Lawrence H. Putnam, which is based on Norden’s frequency distribution (Rayleigh curve). Putnam model maps time and efforts required with software size

## Project Scheduling

Project Scheduling in a project refers to roadmap of all activities to be done with specified order and within time slot allotted to each activity. Project managers tend to define various tasks and project milestones and arrange them keeping various factors in mind.
![](../../../statics/Pasted%20image%2020231202071659.png)

For scheduling a project, it is necessary to -

- Break down the project tasks into smaller, manageable form
- Find out various tasks and correlate them
- Estimate time frame required for each task
- Divide time into work-units
- Assign adequate number of work-units for each task

**+ves of Scheduling**

- It simply ensures that everyone remains on same page as far as tasks get completed, dependencies, and deadlines.
- It helps in identifying issues early and concerns such as lack or unavailability of resources.
- It also helps to identify relationships and to monitor process.
- It provides effective budget management and risk mitigation.

#### Resource Management

All elements used to develop a software product may be assumed as resource for that project. This may include human resource, productive tools and software libraries.
Resource management includes -

- Defining proper organization project by creating a project team and allocating responsibilities to each team member
- Determining resources required at a particular stage and their availability
- Manage Resources by generating resource request when they are required and de-allocating them when they are no more needed.

#### Risk Management

Risk management involves all activities pertaining to identification, analysing and making provision for predictable and non-predictable risks in the project.Risk May include

- Experienced staff leaving the project and new staff coming in.
- Change in organizational management.
- Requirement change or misinterpreting requirement.
- Under-estimation of required time and resources.
- Technological changes, environmental changes, business competition.

##### Risk Management Process

There are following activities involved in risk management process:

- Identification - Make note of all possible risks, which may occur in the project.
- Categorize - Categorize known risks into high, medium and low risk intensity as per their possible impact on the project.
- Manage - Analyses the probability of occurrence of risks at various phases. Make plan to avoid or face risks. Attempt to minimize their side-effects.
- Monitor - Closely monitor the potential risks and their early symptoms. Also monitor the effects of steps taken to mitigate or avoid them.

#### Project Execution and Monitoring

In this phase, the tasks described in project plans are executed according to their schedules.
Execution needs monitoring in order to check whether everything is going according to the plan. Monitoring is observing to check the probability of risk and taking measures to address the risk or report the status of various tasks.
Some Measures:

- Activity Monitoring:- All activities scheduled within some task can be monitored on day-to-day basis. When all activities in a task are completed, it is considered as complete.
- Status Reports:- The reports contain status of activities and tasks completed within a given time frame, generally a week. Status can be marked as finished, pending or work-in-progress etc.
- Milestones Checklist:- Every project is divided into multiple phases where major tasks are performed (milestones) based on the phases of SDLC

#### Project Communication Management

Effective communication plays vital role in the success of a project. It bridges gaps between client and the organization, among the team members as well as other stake holders in the project such as hardware suppliers.
Steps in Process of communication Management

- Planning - This step includes the identifications of all the stakeholders in the project and the mode of communication among them. It also considers if any additional communication facilities are required.
- Sharing - After determining various aspects of planning, manager focuses on sharing correct information with the correct person on correct time. This keeps everyone involved the project up to date with project progress and its status.
- Feedback - Project managers use various measures and feedback mechanism and create status and performance reports. This mechanism ensures that input from various stakeholders is coming to the project manager as their feedback.
- Closure - At the end of each major event, end of a phase of SDLC or end of the project itself, administrative closure is formally announced to update every stakeholder by sending email, by distributing a hardcopy of document or by other mean of effective communication

## Project Configuration Management

Configuration management is a process of tracking and controlling the changes in software in terms of the requirements, design, functions and development of the product.

SCM (Software Configuration management) defines number of tasks

- Identification: Recognizing objects in software configuration.
- Version Control: Managing and tracking changes to software versions.
- Change Control: Regulating and documenting modifications to the software.
- Configuration Audit: Assessing and ensuring the integrity of software configurations.
- Status Reporting: Communicating the current state and progress of the software configuration.

![](../../../statics/Pasted%20image%2020231202093147.png)

The Software Configuration Management (SCM) process is a set of practices and procedures that helps manage and control changes to software throughout its development lifecycle. It typically includes:

1. **Identification:** Recognizing and defining software configuration items (SCIs) or objects.

2. **Version Control:** Managing different versions of the software to track changes, revisions, and releases.

3. **Change Control:** Regulating and documenting changes to the software, ensuring proper authorization and tracking.

4. **Configuration Audit:** Reviewing and validating the configuration items to ensure consistency and compliance with requirements.

5. **Status Reporting:** Providing regular updates on the status of the software configuration, including changes, issues, and progress.

#### Baseline

A phase of SDLC is assumed over if it baselined, i.e. baseline is a measurement that defines completeness of a phase.
Configuration management is a discipline of organization administration, which takes care of occurrence of any change (process, requirement, technological, strategical etc.) after a phase, is baselined

#### Change Control

Change control is function of configuration management, which ensures that all changes made to software system are consistent and made as per organizational rules and regulations

## Project Size Estimation Techniques

#### LOC (Line Of Code)

As the name suggest, LOC count the total number of lines of source code in a project. The units of LOC are:

- KLOC- Thousand lines of code
- NLOC- Non comment lines of code
- KDSI- Thousands of delivered source instruction
  The size is estimated by comparing it with the existing systems of same kind. The experts use it to predict the required size of various components of software and then add them to get the total size.
  **+ves**
- Universally accepted and is used in many models like COCOMO.
- Estimation is closer to developer’s perspective
- Simple To use
  **-ves**
- A different programming language contains different number of lines.
- No proper industry standard exists for this technique.
- It is difficult to estimate the size using this technique in early stages of project.

#### Number of Entities in ER Diagram

The number of entities in ER model can be used to measure the estimation of size of project. Number of entities depends on the size of the project. This is because more entities needed more classes/structures thus leading to more coding.

**+ves**

- Size estimation can be done during initial stages of planning.
- Number of entities is independent of programming technologies used.
  **-ves**
- No fixed standards exist. Some entities contribute more project size than others.
- Just like FPA, it is less used in cost estimation model. Hence, it must be converted to LOC.

#### Total Number of Process in detailed DFD

The model depicts the main processes/functions involved in software and flow of data between them. Utilization of number of functions in DFD to predicts software size

**+ves**

- It is independent of programming language.
- Each major process can be decomposed into smaller processes. This will increase the accuracy of estimation
  **-ves**
- Studying similar kind of processes to estimate size takes additional time and effort.
- All software projects are not required to construction of DFD.

#### Functional Point Analysis

the number and type of functions supported by the software are utilized to find FPC (function point count).

##### Steps involved

- Count the number of functions of each proposed type:- Find the number of functions belonging to the following types:
  - External Inputs: Functions related to data entering the system.
  - External outputs: Functions related to data exiting the system.
  - External Inquiries: They lead to data retrieval from system but don’t change the system.
  - Internal Files: Logical files maintained within the system. Log files are not included here.
  - External interface Files: These are logical files for other applications which are used by our system.
- Compute the Unadjusted Function Points (UFP):- Categorise each of the five function types as simple, average or complex based on their complexity. Multiply count of each function type with its weighting factor and find the weighted sum
  - Weight factor are as follows
  - ![](../../../statics/Pasted%20image%2020231202070834.png)
- Find Total Degree of Influence (TDI):- Use the ’14 general characteristics’ of a system to find the degree of influence of each of them. The sum of all 14 degrees of influences will give the TDI. The range of TDI is 0 to 70
- Compute Value Adjustment Factor (VAF):- Use the following formula to calculate VAF VAF = (TDI `*` 0.01) + 0.65
- Find the Function Point Count (FPC):- Use the following formula to calculate FPC FPC = UFP `*` VAF

**+ves**

- It can be easily used in the early stages of project planning.
- It is independent on the programming language.
- It can be used to compare different projects even if they use different technologies (database, language etc.).
  **-ves**
- It is not good for real time systems and embedded systems.
- Many cost estimation models like COCOMO uses LOC and hence FPC must be converted to LOC.

## Personnel Management

Personnel Planning deals with staffing. Staffing deals with the appoint personnel for the position that is identified by the organizational structure

It involves:

- Defining requirement for personnel
- Recruiting (identifying, interviewing, and selecting candidates)
- Compensating
- Developing and promoting agent

## Team Structure

Team structure addresses the issue of arrangement of the individual project teams. There are some possible methods in which the different project teams can be organized. There are primarily three formal team structures: chief programmer, Ego-less or democratic, and the mixed team organizations

#### Ego-Less or Democratic Teams

consist of a team of fewer programmers. The objective of the group is set by consensus, and input from each member is taken for significant decisions. Group leadership revolves among the group members. Due to its nature, egoless teams are consistently known as democratic teams.

structure allows input from all representatives, which can lead to better decisions in various problems. This suggests that this method is well suited for long-term research-type projects that do not have time constraints.
![](../../../statics/Pasted%20image%2020231202092608.png)

#### cheif programmmer

A chief-programmer team, in contrast to the ego-less team, has a hierarchy. It consists of a chief- programmer, who has a backup programmer, a program librarian, and some programmers. The chief programmer is essential for all major technical decisions of the project. He does most of the designs, and he assigns coding of the different part of the design to the
programmers.

The program librarian is vital for maintaining the documentation and other communication-related work.
![](../../../statics/Pasted%20image%2020231202092750.png)

#### Controlled Decentralised Team

A third team structure known as the controlled decentralized team tries to combine the strength of the democratic and chief programmer teams.

It consists of project leaders who have a class of senior programmers under him, while under every
senior programmer is a group of a junior programmer. The group of a senior programmer and his junior programmers behave like an ego-less team, but communication among different groups occurs only through the senior programmers of the group.

The senior programmer also communicates with the project leader.

This structure works best for large projects that are reasonably straightforward. It is not well suited for
simple projects or research-type projects.

![](../../../statics/Pasted%20image%2020231202092928.png)

## COCOMO

Boehm proposed COCOMO (Constructive Cost Estimation Model) in 1981.COCOMO is one of the most generally used software estimation models in the world. COCOMO predicts the efforts and schedule of a software product based on the size of the software.

#### Steps involved in model

1. Get an initial estimate of the development effort from evaluation of thousands of delivered lines of source code (KDLOC).
2. Determine a set of 15 multiplying factors from various attributes of the project.
3. Calculate the effort estimate by multiplying the initial estimate with all the multiplying factors i.e., multiply the values in step1 and step2.

## Risk Management

#### What is risk

problem that could cause some loss or threaten the progress of the project, but which has not happened yet.

Risk Management is the system of identifying addressing and eliminating these problems before they
can damage the project.

#### Risk Management

There are three main classifications of risks which can affect a software project:

- Project risks:- Project risks concern differ forms of budgetary, schedule, personnel, resource, and customer-related problems. A vital project risk is schedule slippage.
- Technical risks:- Technical risks concern potential method, implementation, interfacing, testing, and maintenance issue
- Business risks:- This type of risks contain risks of building an excellent product that no one need, losing budgetary or personnel commitments

##### Risk Management Activities

![](../../../statics/Pasted%20image%2020231202093711.png)
**Risk Assessment**
The objective of risk assessment is to division the risks in the condition of their loss, causing potential. For risk assessment, first, every risk should be rated in two methods:

- The possibility of a risk coming true
- The consequence of the issues relates to that risk.

Risk Identification:-

1. Technology risks: Risks that assume from the software or hardware technologies that are used to develop the system.
2. People risks: Risks that are connected with the person in the development team.
3. Organizational risks: Risks that assume from the organizational environment where the software is being developed.
4. Tools risks: Risks that assume from the software tools and other support software used to create the system.
5. Requirement risks: Risks that assume from the changes to the customer requirement and the process of managing the requirements change.
6. Estimation risks: Risks that assume from the management estimates of the resources required to build the system

**Risk Control**
There are three main methods to plan for risk management:

- Avoid the risk: This may take several ways such as discussing with the client to change the requirements to decrease the scope of the work, giving incentives to the engineers to avoid the risk of human resources turnover, etc.
- Transfer the risk: This method involves getting the risky element developed by a third party, buying insurance cover, etc.
- Risk reduction: This means planning method to include the loss due to risk. For instance, if there is a risk that some key personnel might leave, new recruitment can be planned.
