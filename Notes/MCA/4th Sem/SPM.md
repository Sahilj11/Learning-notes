# Unit 3
## Risk Management 
### Intro
- Risk is an uncertain event or condition that , if it occurs has +ve or -ve effect on a project objectives
- Risk management plan is a document that a project manager prepares to forsee risks, estimate impacts , and defines response to risks.
### Nature of Risk
|Characteristic|Description|
|---|---|
|**Uncertainty**|Risk deals with future events that may or may not happen.|
|**Potential Impact**|If the event occurs, it may affect time, cost, scope, or quality.|
|**Probability**|Risk is probabilistic (not guaranteed); usually classified as high/med/low.|
|**Time Sensitivity**|Risks are only relevant during a specific time window in the project.|
|**Dual Nature**|Risks can be **negative** (threats) or **positive** (opportunities).|
|**Manageability**|Most risks can be **identified**, **analyzed**, and **mitigated**.|
### Types of risk
![](../../statics/Pasted%20image%2020250420111120.png)
- Actors :- referes to all people involed in development of application
- Technology:- tech used to develop the application and that embedded in the delivered products
- Structure:- describe management structure and system including those affecting planning control 
- Tasks:- relates to work planned . For instance , complexity of work might lead to delay because of additional time required

| Category                    | Description                                             | Examples                                                                       |
| --------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Technical Risk**          | Related to technology, architecture, or implementation. | Use of new, untested frameworks; performance bottlenecks; compatibility issues |
| **Project Management Risk** | Poor planning or execution of project activities.       | Unrealistic deadlines; inaccurate estimation; weak leadership                  |
| **Business Risk**           | Affects the business value or viability of the project. | Change in market trends; stakeholder conflicts; unclear ROI                    |
| **Operational Risk**        | Related to people, process, or system failures.         | Team resignations; poor communication; tool failures                           |
| **External Risk**           | Outside the control of the project team.                | Legal issues; natural disasters; vendor failures; political changes            |
| **Security Risk**           | Relates to data loss, cyberattacks, or breaches.        | Insecure APIs; improper access controls                                        |
| **Finanacial Risk**         | Related Market , credit                                 |                                                                                |
| **Compliance Risk**         | Changes in rules and compliance                         |                                                                                |

### Process
![](../../statics/Pasted%20image%2020250420102254.png)
![](../../statics/Pasted%20image%2020250420102933.png)

#### Risk Identication
Risk identification refers to the systematic process of recognizing and evaluating potential threats or hazards that could negatively impact an organization, its operations, or its workforce. This involves identifying various types of risks, ranging from IT security threats like viruses and phishing attacks to unforeseen events such as equipment failures and extreme weather conditions.

**Methods**
1. **Checklist Analysis –** Checklist Analysis is type of technique generally used to identify or find risks and manage it. The checklist is basically developed by listing items, steps, or even tasks and is then further analyzed against criteria to just identify and determine if procedure is completed correctly or not. It is list of risk that is just found to occur regularly in development of software project.
2. **Brainstorming –** It is creative and unique technique to gather risks spontaneously by team members. The team members identify and determine risks in ‘no wrong answer’ environment
3. **SWOT Analysis –** Strengths-Weaknesses-Opportunities-Threat (SWOT) is very technique and helpful for identifying risks within greater organization context.
4. **Flowchart Method –** This method allows for dynamic process to be diagrammatically represented in paper. This method is generally used to represent activities of process graphically and sequentially to simply identify the risk.

#### Risk Analysis

Risk Analysis is the process of evaluating identified risks to understand their potential impact and likelihood. This allows the project team to prioritize risks and plan appropriate responses. It helps answer questions like: “How serious is this risk?”, “How likely is it to happen?”, and “What will happen if it does?”

**Objectives of Risk Analysis**

- Prioritize risks based on severity
    
- Understand root causes and possible effects
    
- Provide a foundation for planning responses
    
- Support better project decisions
    

**When is Risk Analysis Performed?**

Risk analysis is done after identifying risks and is revisited regularly throughout the project, especially after changes in scope, technology, or team structure.

**Types of Risk Analysis**

There are two main types of risk analysis: qualitative and quantitative.

1. Qualitative Risk Analysis
    

This is a non-numeric, subjective method to evaluate and rank risks based on probability and impact.

Steps involved:

- Assign probability: Low, Medium, High (or on a 1 to 5 scale)
    
- Assign impact: Low, Medium, High (or on a 1 to 5 scale)
    
- Calculate a simple risk score using:  
    Risk Priority Number (RPN) = Probability × Impact
    

An example:

| Risk                  | Probability | Impact | RPN | Priority |
| --------------------- | ----------- | ------ | --- | -------- |
| API integration fails | High        | High   | 9   | Critical |
| Developer sick leave  | Medium      | Medium | 4   | Moderate |
| Tool license delay    | Low         | Medium | 2   | Low      |

This is often visualized using a risk matrix or heatmap.

2. Quantitative Risk Analysis
    

This is a data-driven approach that evaluates risks in numeric terms, especially useful in large or high-cost software projects.

Common techniques include:

a. Expected Monetary Value (EMV)  
Formula: EMV = Probability × Monetary Impact  
Example:  
If a delay has a 40% chance and will cost ₹50,000, then  
EMV = 0.4 × 50,000 = ₹20,000

b. Three-Point Estimation (PERT)  
Formula: Expected Time (TE) = (O + 4M + P) / 6  
Where:

- O = Optimistic time
    
- M = Most likely time
    
- P = Pessimistic time
    

Standard Deviation: σ = (P - O) / 6

c. Z-Value Calculation (for schedule risk)  
Formula: Z = (D - TE) / σ  
Where:

- D = Desired completion time
    
- TE = Expected time
    
- σ = Standard deviation  
    Use a Z-table to find the probability of meeting the schedule.
    

d. Monte Carlo Simulation  
This technique uses a computer model to simulate thousands of possible project outcomes and gives a probability distribution for schedules, costs, or risks.

**Differences Between Qualitative and Quantitative Analysis**

|Aspect|Qualitative Analysis|Quantitative Analysis|
|---|---|---|
|Type|Subjective, descriptive|Objective, numerical|
|Output|Risk ranking|Measurable risk impact|
|Speed|Faster|Time-consuming|
|Best Used For|Most projects, early planning|Complex, high-budget projects|

**Summary**

Risk analysis helps project managers understand which risks need urgent attention and which ones are acceptable. Qualitative analysis is used for early risk screening, while quantitative analysis helps in cost, time, and schedule estimations. A good risk analysis leads to better planning, fewer surprises, and higher project success.

#### Reducing the risk

**Reducing the Risk in Software Project Management**

Reducing risk involves taking proactive steps to minimize the likelihood of a risk occurring or reducing its impact if it does occur. It is part of the overall risk management strategy and is critical for ensuring project success.
Control :- reduce event probability
Mitigation:- reduce risk impact
**Why Reduce Risks?**

- To avoid project delays, cost overruns, or quality issues
    
- To increase confidence among stakeholders
    
- To improve the stability and predictability of the project
    

**Approaches to Reducing Risk/ Risk Planning**

1. **Risk Avoidance**
    
    - Changing the project plan to eliminate the risk entirely
        
    - Example: Avoid using a new, untested technology by choosing a stable one
        
2. **Risk Reduction and Mitigation**
    - Taking actions to reduce the probability or impact of the risk
    - Example: Training the team in a new tool to reduce skill-based risks
3. **Risk Transfer**
    
    - Shifting the impact of the risk to a third party
        
    - Example: Outsourcing a high-risk component to a specialist vendor or buying insurance
        
4. **Risk Acceptance**
    
    - Acknowledging the risk and preparing a contingency plan
    - Example: If a third-party API might go down, prepare fallback features
        

**Common Techniques for Reducing Risk**

- **Improve Requirements Gathering**
    
    - Use clear, documented, and validated requirements to reduce ambiguity
        
- **Use Prototyping or Proof of Concept**
    
    - Helps to test risky features or technologies early
        
- **Follow Coding and Quality Standards**
    
    - Helps reduce technical and quality-related risks
        
- **Automated Testing and Continuous Integration**
    
    - Ensures quick detection of bugs and reduces the risk of late-stage issues
        
- **Incremental Development (Agile/Scrum)**
    
    - Regular deliveries help catch and fix problems early
        
- **Skill Development and Training**
    
    - Reduces the risk of human error and improves productivity
        
- **Risk Sharing and Contracts**
    
    - Well-written contracts can define responsibilities and reduce legal/financial risk
        
- **Regular Risk Reviews**
    
    - Frequent monitoring helps spot emerging risks early
        
- **Buffering Time and Budget**
    
    - Allocating extra time or budget can absorb the impact of unforeseen risks
        

**Example of Reducing Specific Risks**

|Risk|Reduction Strategy|
|---|---|
|Inexperienced team members|Provide training or hire experienced consultants|
|Unstable third-party API|Use caching, backup API, or build internal wrapper|
|Tight deadlines|Use time buffers and prioritize critical tasks|
|Scope creep|Use change control process and strong documentation|

**Summary**

Reducing risk in software project management involves identifying potential problems and acting early to prevent or minimize their impact. Techniques include avoidance, mitigation, transferring responsibility, and preparing contingency plans. By reducing risks, project teams can deliver more predictable and successful outcomes.
#### Evaluating risk to schedule

Evaluating risks to the schedule involves analyzing how identified risks might impact the **timeline** or **delivery deadlines** of a software project. Since time overruns are common in software development, it's critical to assess and quantify how potential risks may affect the schedule.

**Purpose of Schedule Risk Evaluation**
- To understand which risks can delay key milestones
- To prioritize risks that affect the project timeline
- To make better decisions about resource allocation and planning
- To communicate realistic timelines to stakeholders

**Common Risks That Affect Schedule**
- Incomplete or changing requirements
    
- Underestimation of task durations
    
- Delays in third-party components or APIs
    
- Team member absence or turnover
    
- Slow feedback from clients or stakeholders
    
- Technical challenges or integration failures
    
- Inadequate testing time due to late development

**Methods to Evaluate Schedule Risk**
1. **PERT (Program Evaluation and Review Technique)**  
    Used to estimate task durations by considering uncertainty.
    Formula for Expected Time (TE):  
    TE = (Optimistic + 4 × Most Likely + Pessimistic) / 6
    
    Standard Deviation (σ):  
    σ = (Pessimistic – Optimistic) / 6
    
    Helps identify how variability affects the project timeline.
    
2. **Critical Path Method (CPM)**  
    Identifies the longest sequence of dependent tasks.  
    Any delay in the critical path directly delays the project.  
    Risk evaluation focuses on tasks along or near the critical path.
    
3. **Z-Value Calculation**  
    Measures the likelihood of completing the project within a desired time frame.
    
    Formula:  
    Z = (Desired Time – Expected Time) / Standard Deviation
    
    The Z-value is used with a Z-table to calculate probability.
    
4. **Monte Carlo Simulation**  
    A computerized method that simulates multiple project timelines using random inputs.  
    Produces a probability distribution for project duration.  
    Useful for large, complex projects with many uncertainties.
    
5. **Schedule Risk Analysis Using Tools**  
    Project management software like Microsoft Project, Primavera, or JIRA can simulate delays and forecast schedule impact.
    

---

**Schedule Risk Indicators**
- Number of tasks with high variability
- Tasks without backups or dependencies
- Tasks estimated without sufficient data
- Number of tasks on the critical path    
- Ratio of planned vs. actual time over similar past projects

**Strategies to Manage Schedule Risks**
- Add **time buffers** (contingency) to high-risk tasks
- Use **fast-tracking** or **crashing** to speed up the schedule
- Re-allocate skilled resources to critical tasks
- Break large tasks into smaller, trackable one
- Conduct regular status checks to catch early delays
- Use Agile sprints for faster delivery and feedback
**Summary**

Evaluating risks to the schedule helps in understanding how project timelines can be impacted by uncertainties. Techniques like PERT, critical path analysis, and Z-value calculation allow managers to estimate and mitigate potential delays. By identifying schedule risks early, teams can adjust plans, allocate resources wisely, and deliver projects more reliably.

### Resource Allocation

**Introduction**

Resource allocation is the process of assigning and managing available resources—such as team members, tools, budget, and time—to project tasks in the most efficient and effective way. Proper resource allocation ensures that project objectives are met within time and budget constraints.

It is a core component of project planning and plays a major role in meeting deadlines, maintaining quality, and avoiding overallocation or underutilization of team members.

**Nature of Resources**

![](../../statics/Pasted%20image%2020250420112013.png)
Resources in software projects are not just limited to people. They include:

1. **Human Resources**
    
    - Developers, testers, designers, project managers, analysts
        
    - Most critical and variable in productivity
        
2. **Software and Tools**
    
    - IDEs, testing frameworks, CI/CD pipelines, project management tools
        
3. **Hardware Infrastructure**
    
    - Servers, development machines, test environments
        
4. **Time**
    
    - Time is a non-renewable resource; managing it is crucial
        
5. **Financial Resources**
    
    - Budget for salaries, licenses, infrastructure, etc.

**Identifying Resource Requirements**

Before allocating, it's important to analyze what resources are needed, how much, and when.

Steps:

- Analyze the **Work Breakdown Structure (WBS)**
    
- Estimate time and effort for each task
    
- Determine the **type** and **quantity** of resources needed
    
- Identify **skill sets** required for technical tasks
    
- Consider availability and any **constraints** (e.g., holidays, sick leaves)
    

Example:  
If Module A requires frontend development, you may need:

- 1 React developer for 10 days
    
- 1 UI designer for 5 days
    
- 1 tester for 3 days
    

---

**Scheduling Resources**

Once resources are identified, they must be scheduled efficiently to avoid conflicts, delays, or overloading.

Techniques for scheduling resources:

- **Gantt Charts** – Visual timelines of who is doing what and when
    
- **Resource Histograms** – Show resource usage over time
    
- **Calendars** – Plan based on resource availability
    
- **Timeboxing (Agile)** – Fixed time intervals for tasks/sprints
    
- **Load Balancing** – Distribute workload evenly across the team
    

Key Goals:

- Ensure critical tasks have the required resources
    
- Avoid idle time or overallocation
    
- Handle resource conflicts across tasks/projects
    

---

**Creating Critical Paths**

The **Critical Path Method (CPM)** is used to identify the sequence of dependent tasks that determine the **minimum project duration**.

Steps to create a critical path:

1. List all tasks and their durations
    
2. Identify dependencies between tasks
    
3. Create a project network diagram
    
4. Calculate **Earliest Start (ES)** and **Latest Finish (LF)** for each task
    
5. Identify the **longest path** in the diagram — this is the critical path
    

Tasks on the critical path:

- Cannot be delayed without affecting the entire project
    
- Should receive top priority in resource allocation
    

If a task not on the critical path gets delayed, the project may still finish on time, depending on its slack or float.

Example:  
If the critical path is Task A → Task B → Task D and Task B is delayed, the whole project will be delayed unless action is taken.

---

**Summary**

- Resource allocation is essential for successful project delivery
    
- Resources include people, tools, time, and budget
    
- Identifying requirements helps assign the right resources to the right tasks
    
- Scheduling ensures efficient use without conflict or overload
    
- The critical path highlights tasks that must stay on track for the project to finish on time

# UNIT 4
# Contracts

## **1. Introduction (in context of SPM)**

In **Software Project Management**, a **contract** is a formal agreement between two parties — usually the **client (customer)** and the **software development organization**. The contract outlines **what software will be delivered**, **how**, **when**, **by whom**, and **under what terms and conditions** (including payment and liabilities). Contracts help manage expectations, responsibilities, and reduce risks in software projects.

## **2. Types of Contracts in SPM**
There are several types of contracts commonly used in software projects:
### a) **Fixed Price Contract (FPC)**
- The client pays a pre-agreed amount regardless of the actual effort/time spent.
- Best for well-defined requirements
- **Risk** is on the **vendor**.

### b) **Time and Material Contract (T&M)**

- The client pays for the time and resources used.
    
- Flexible for projects with evolving requirements.
    
- **Risk** is on the **client**.
    

### c) **Cost-Reimbursable Contract**

- Client pays the actual cost incurred plus a fee (profit margin).
    
- Used when exact requirements and costs are hard to define.
    
- Variants: **Cost plus Fixed Fee (CPFF)**, **Cost plus Incentive Fee (CPIF)**
    

### d) **Incentive-Based Contract**

- Rewards or penalties based on performance metrics (like early delivery).
    
- Encourages better performance.
    

### e) **Unit Price Contract**

- Payment is based on unit deliverables (e.g., per feature/module).
    
- Often used in Agile or modular development approaches.
    

---

## **3. Stages in Contract Placement (in SPM context)**

Contract placement involves several structured stages:

### 1. **Requirement Identification**

- Identify and define project scope, objectives, and deliverables.
    
- Basis for selecting the type of contract.
- Identifying mandatory and desirable needs
    

### 2. **Bidding / Tendering**

- Request for Proposal (RFP) or Invitation to Bid (ITB) is issued.
    
- Vendors prepare and submit proposals based on requirements.
    

### 3. **Proposal Evaluation**

- Proposals are evaluated based on technical capability, cost, timeline, experience, etc.
    

### 4. **Negotiation**

- Final terms and conditions, timelines, pricing, and deliverables are discussed.
    
- Aim is to reach mutual understanding and agreement.
    

### 5. **Contract Award and Signing**

- The chosen vendor is awarded the contract.
    
- Legal agreement is signed by both parties.
    

### 6. **Contract Execution and Monitoring**
- Project work starts; performance is monitored against the contract.
- May include periodic reviews, milestone validations, and audits.

### 7. **Contract Closure**
- Upon completion, the contract is formally closed.
- Final deliverables are accepted, and payments settled.