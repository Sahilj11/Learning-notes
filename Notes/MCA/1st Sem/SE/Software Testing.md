## Basics of testing

- Software testing is the process of executing a program (or a part of program) with the intent of finding errors
- Approaches of testing
  - Black box testing: in this tester does not have the knowledge of the coding . in this testing we only check the functionality of software that is input be pass and output the s/w produce
  - ![](../../../statics/Pasted%20image%2020231103144841.png)
  - White box testing: in this tester has knowledge of coding and internal structure of existing software wheather the internal structure is correct or not
  - ![](../../../statics/Pasted%20image%2020231103145019.png)
  - notice here box is transparent

### Necessities and obj of software testing

Software testing serves multiple necessities and objectives, crucial for ensuring the quality, reliability, and success of software applications. Here are the primary necessities and objectives of software testing:

### Necessities of Software Testing:

Software testing is essential for various reasons in the development process, ensuring the quality and reliability of the software. Here's an explanation for each of the listed points:

1. **Gaining Customer Confidence:** Thorough testing ensures that the software meets the specified requirements, functions as intended, and is reliable. This helps in gaining the trust and confidence of the customers in the software's performance and usability.

2. **Checking Software Adaptability:** Testing evaluates the software's adaptability to different environments, devices, and operating systems. It ensures that the software can function properly across various platforms and configurations.

3. **Identifying Errors:** Testing is crucial for identifying and fixing errors, bugs, and defects in the software. By uncovering these issues early in the development process, developers can address them before the software reaches the end-users.

4. **Avoiding Extra Costs:** Detecting and fixing issues during the development phase is less costly than dealing with problems after the software is deployed. Testing helps in identifying and rectifying issues before they escalate, saving time and resources.

5. **Accelerating Software Development:** While testing might seem to slow down the development process, it actually speeds it up in the long run. Catching and fixing issues early prevents delays and rework, leading to a more efficient and timely development cycle.

6. **Avoiding Risks:** Testing mitigates the risks associated with software malfunctions, security vulnerabilities, and potential failures. A thoroughly tested software product is less prone to unexpected errors, ensuring a more stable and secure user experience.

### Objectives of Software Testing:

- Finding defects which may get created by the programmer while developing the software.
- Gaining confidence in and providing information about the level of quality.
- To prevent defects.
- To make sure that the end result meets the business and user requirements.
- To ensure that it satisfies the BRS that is Business Requirement Specification and SRS that is System Requirement Specifications.
- To gain the confidence of the customers by providing them a quality product.

### Testing principles

- All tests should be traceable to customer requirements.(from customers point of view)
- **Tests should be planned** long before testing begins. (Begins as soon as the requirements model is complete)
- The **pareto** principle applies to software testing. ( implies that 80 percent of all errors uncovered during testing will likely be traceable to 20 percent of all program components)
- Testing should begin “in the small” and progress toward testing “in the large.” (from individual components and ultimately in the entire system)
- Exhaustive testing in not possible. (It is not possible to exhaustively test every program path because the number of paths is simple too large)
- To be most effective, testing should be conducted by an independent third party. (Most effective means highest probability of finding errors)

## Inspection vs testing

In simple words, **Software testing** is the process of evaluating the product that whether it’s working properly as per requirements. It is related to finding bugs in UI, functionality and as per end-user perspective of the product
while **Software inspection** is testing plus code review to ensure that it is correct, optimized and maintainable. It is mainly related to finding bugs in program’s code as per both requirements and test cases.

## Testing and debugging

- Software testing is a process of identifying defects in the software product. It is performed to validate the behavior of the software or the application compared to requirements.

### Debugging

- Debugging is the action where the development team or a developer implements after receiving the test report related to the bugs in the software from the testing team. In the software development process, it includes detecting and modifying code errors in a software program

#### Steps in debugging

- Identify error
- Finding error location
- Analyze error
- Prove the analysis
- Cover lateral damage
- Fix and validate

#### +ves of debugging

- It supports the developer in minimizing the data.
- If the perform the debugging, we can report the error condition directly
- During the debugging process, the developer can avoid complex one-use testing code that helps the developer save time and energy.
- Debugging delivers maximum useful information of data structures and allows its informal understanding.

### Testing vs debugging

Sure, here's a markdown table presenting the differences between testing and debugging:
Certainly, here's the updated table with the additional three points:

| S.NO | Testing                                                                                                                                                                      | Debugging                                                                                                  |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| 1.   | It is the implementation of the software with the intent of identifying the defects.                                                                                         | The process of fixing and resolving the defects is known as debugging.                                     |
| 2.   | Testing can be performed either manually or with the help of some automation tools.                                                                                          | The debugging process cannot be automated.                                                                 |
| 3.   | A group of test engineers executes testing, and sometimes it can be performed by the developers.                                                                             | Debugging is done by the developer or the programmer.                                                      |
| 4.   | The test engineers perform manual and automated test cases on the application, and if they detect any bug or error, they can report back to the development team for fixing. | The developers will find, evaluate, and remove the software errors.                                        |
| 5.   | Programming knowledge is not required to perform the testing process.                                                                                                        | Without having an understanding of the programming language, we cannot proceed with the debugging process. |
| 6.   | Once the coding phase is done, we proceed with the testing process.                                                                                                          | After the implementation of the test case, we can start the Debugging process.                             |
| 7.   | Software Testing includes two or more activities such as validation and verification of the software.                                                                        | Debugging tries to match indication with cause, hence leading to the error correction.                     |
| 8.   | It is built on different testing levels such as Unit Testing, Integration Testing, System Testing, etc.                                                                      | It is built on different kinds of bugs because there is no such level of debugging possible.               |
| 9.   | Software testing is the presentation of defects.                                                                                                                             | It is a logical procedure.                                                                                 |
| 10.  | Software testing is the vital phase of SDLC (Software Development Life Cycle).                                                                                               | It is not a part of SDLC because it occurs as a subset of testing.                                         |

## Software testing life cycle

- sequence of specific activities conducted during the testing process to ensure software quality goals are met. STLC involves both verification and validation activities.
  There are following six major phases in every Software Testing Life Cycle Model (STLC Model):
- requirement Analysis
  - Requirement Phase Testing also known as Requirement Analysis in which test team studies the requirements from a testing point of view to identify testable requirements and the QA team may interact with various stakeholders to understand requirements in detail. Requirements could be either functional or non-functional.
  - Activities done in this step
    - Identify types of tests to be performed.
    - Gather details about testing priorities and focus.
    - Prepare Requirement Traceability Matrix (RTM)
  - Deliverables of this phase
    - RTM
    - Automation feasibility report
- Test Planning
  - Senior QA manager determines the test plan strategy along with efforts and cost estimates for the project. Moreover, the resources, test environment, test limitations and the testing schedule are also determined.
  - Activities
    - Preparation of test plan/strategy document for various types of testing
    - Test tool selection
    - Test effort estimation
    - Resource planning and determining roles and responsibilities.
    - Training requirement
  - Deliverables
    - Test plan
    - Effort estimation document
- Test case development
  - involves the creation, verification and rework of test cases & test scripts after the test plan is ready. Initially, the Test data is identified then created and reviewed and then reworked based on the preconditions. Then the QA team starts the development process of test cases for individual units.
  - Activities
    - Create test cases, automation scripts (if applicable)
    - Review and baseline test cases and scripts
    - Create test data (If Test Environment is available)
  - Deliverable
    - Test case
    - Test data
- Test Environment setup
  - decides the software and hardware conditions under which a work product is tested. It is one of the critical aspects of the testing process and can be done in parallel with the Test Case Development Phase.
  - Activities
    - Understand the required architecture, environment set-up and prepare hardware and software requirement list for the Test Environment.
    - Setup test Environment and test data
    - Perform smoke test on the build
  - Deliverable
    - Environment ready with test data setup
    - Smoke test results
- Test Execution
  - carried out by the testers in which testing of the software build is done based on test plans and test cases prepared. The process consists of test script execution, test script maintenance and bug reporting. If bugs are reported then it is reverted back to development team for correction and retesting will be performed.
  - Activities
    - Execute tests as per plan
    - Document test results, and log defects for failed cases
    - Map defects to test cases in RTM
    - Retest the defect fixes
    - Track the defects to closure
  - Deliverable
    - Completed RTM with execution status
    - Test cases updated with results
    - Defect reports
- Test Cycle closure
  - completion of test execution which involves several activities like test completion reporting, collection of test completion matrices and test results. Testing team members meet, discuss and analyze testing artifacts to identify strategies that have to be implemented in future, taking lessons from current test cycle
  - Activities
    - Evaluate cycle completion criteria based on Time, Test coverage, Cost,Software, Critical Business Objectives, Quality
    - Prepare test metrics based on the above parameters.Document the learning out of the project
    - Prepare Test closure report
    - Qualitative and quantitative reporting of quality of the work product to the customer.
    - Test result analysis to find out the defect distribution by type and severity.
  - Deliverable
    - Test closure report
    - Test metrics

## Software testing strategies and techniques

- A test strategy is a concise statement that describes how the objectives of the software testing are met. The test strategy views the test event at a high level, concentrates on the objectives of the test event, the techniques that can be used and the resources that are required
- A testing technique can be defined as a process that ensures that the application being tested functions in a structured way.
- A testing strategy and technique is based on the method of testing adopted.

### Methods of testing

#### Structural vs functional testing

- If the test cases are developed to check the actual structure of the program code, then it is called structural testing. Structural testing is also known as white box testing, where the tester checks the actual code of the software. However, in functional testing(type of black-box testing), the tester checks only the behavior of the software and will not check the actual code. The tester only checks the response of the software for predefined inputs and tests whether the software produces the desired output

#### Static vs dynamic testing

- Static testing refers to the analysis of the program, which is carried out without executing the program. This is a typical white box testing technique, where the developer checks the code to find errors in it. It is preventive in nature and is completed in the verification phase. The common methods include feasibility review and code review.
- Dynamic testing refers to the analysis of the program in its executable form. This is performed by supplying valid entries and is validated against the expected results. It is a curative method and is performed during the validation phase.

#### Manual vs Automation testing

## V-Model

### Intro

- The V-model is an SDLC model where execution of processes happens in a sequential manner in a Vshape. It is also known as Verification and Validation model.
- The V-Model is an extension of the waterfall model and is based on the association of a testing phase for each corresponding development stage. This means that for every single phase in the development cycle, there is a directly associated testing phase.

### V-Model-Design

the corresponding testing phase of the development phase is planned in parallel. So, there are Verification phases on one side of the ‘V’ and Validation phases on the other side. The Coding Phase joins the two sides of the V-Model
![](../../../statics/Pasted%20image%2020231104090003.png)
first writing some explaination of verfication phase and then validation phase

### V-Model Application

- V- Model application is almost the same as the waterfall model, as both the models are of sequential type. Requirements have to be very clear before the project starts, because it is usually expensive to go back and make changes.
- Requirements are well defined, clearly documented and fixed.
- Product definition is stable.
- Technology is not dynamic and is well understood by the project team.
- There are no ambiguous or undefined requirements.
- The project is short

### Pros and Cons

The advantages of the V-Model method are as follows −

- This is a highly-disciplined model and Phases are completed one at a time.
- Works well for smaller projects where requirements are very well understood.
- Simple and easy to understand and use.
- Easy to manage due to the rigidity of the model. Each phase has specific deliverables and a review process
  The disadvantages of the V-Model method are as follows −
- High risk and uncertainty.
- Not a good model for complex and object-oriented projects.
- Poor model for long and ongoing projects.
- Not suitable for the projects where requirements are at a moderate to high risk of changing.
- Once an application is in the testing stage, it is difficult to go back and change functionality.
- No working software is produced until late during the life cycle.

## Type of testing , more specifically it is levels of testing

![](../../../statics/Pasted%20image%2020231103142031.png)

### Unit(individual blocks) testing

Unit testing is a fundamental practice in software engineering that involves testing individual units or components of a software application in isolation. These units are the smallest testable parts of an application, such as functions, methods, or classes. The primary objective of unit testing is to validate that each unit of the software performs as expected.

Unit testing is done by developers

Key aspects of unit testing include:

1. **Isolation**: Unit tests focus on isolating the specific unit being tested from the rest of the application. This is usually achieved through the use of mocks, stubs, or other test doubles to simulate dependencies.

2. **Automation**: Unit tests are typically automated, allowing developers to run them frequently without manual intervention. Automated testing ensures quick feedback during development and helps catch issues early.

3. **Independence**: Unit tests should be independent of each other, meaning the success or failure of one test should not impact the results of another. This independence helps pinpoint the specific causes of failures.

4. **Repeatability**: Unit tests should produce the same results every time they are run, regardless of when or where they are executed. This consistency is crucial for building confidence in the testing process.

5. **Fast Execution**: Unit tests should execute quickly. Their speed allows for rapid feedback during development, enabling developers to iterate on their code efficiently.

6. **Coverage**: Unit tests aim to cover various scenarios and edge cases for a particular unit, striving for high test coverage to ensure a broad range of conditions are validated.

Benefits of unit testing include:

- **Bug Identification**: Helps to catch bugs early in the development cycle, making them cheaper and easier to fix.
- **Refactoring Confidence**: Provides a safety net for refactoring code, ensuring that changes do not break existing functionality.
- **Documentation**: Serves as a form of documentation, illustrating how a unit should be used and what output is expected.
- **Improved Design**: Encourages writing modular, testable code by breaking it into smaller, more manageable units.

While unit testing is an integral part of software development, it's important to note that it's not a panacea. It should be part of a broader testing strategy that includes integration testing, system testing, and other approaches to ensure the overall quality of the software.

Adhering to good practices and investing time in creating effective unit tests can significantly improve the quality, maintainability, and reliability of software systems.

### Integration testing

Integration testing is the next phase after unit testing in the software testing process. It focuses on verifying the interactions and connections between different units (which have already been individually tested in unit testing) when combined or integrated as a group.

**Stubs and Drivers** are the dummy programs in Integration testing used to facilitate the software testing activity. These programs act as a substitute for the missing models in the testing. They do not implement the entire programming logic of the software module but they simulate data communication with the calling module while testing.
Stub: Is called by the Module under Test.
Driver: Calls the Module to be tested

As a step after unit testing, integration testing ensures that these units work together as expected and that the interfaces between them function correctly. It checks how these various units collaborate, share data, and interact with one another within the larger system.

Here’s how integration testing builds upon unit testing:

1. **Unit Testing Completion**: Before integration testing begins, individual units have already undergone testing in isolation during the unit testing phase. These units—such as functions, classes, or modules—have been tested to ensure they perform as intended.

2. **Combining Units**: Integration testing involves combining these individually tested units together into larger components or groups. These groups could be subsystems, layers, or any combination of units necessary for the system's functionality.

3. **Testing Interactions**: The primary focus of integration testing is to validate how these combined units interact with each other. It examines data flow, control flow, and the exchange of information between different components to ensure they work in sync.

4. **Integration Strategies**: There are different approaches to integration testing:

   - **Top-Down**: Starting from higher-level modules and gradually integrating lower-level modules.
   - **Bottom-Up**: Integrating from lower-level modules and progressively combining higher-level modules.
   - **Big Bang**: Integrating all components at once to test the system as a whole.
   - **Sandwich/Hybrid**: A mix of top-down and bottom-up approaches.

5. **Identifying Interface Issues**: Integration testing helps detect interface defects, communication problems, and inconsistencies that might arise when units interact. It verifies that the integrated components properly exchange information and function as expected.

6. **Verification of System Behavior**: It goes beyond individual unit behavior and assesses the behavior of the system as a whole, ensuring that the integrated units work together harmoniously.

Integration testing is a critical step to ensure that the system is cohesive, functions as intended, and is capable of handling various scenarios and interactions between different components. It provides confidence in the system’s reliability and robustness before proceeding to broader system-level testing.

#### Integration strategies

Integration testing strategies are methodologies used to combine and test various modules or components of a software system after individual units have been unit tested. These strategies focus on integrating these units in different ways to ensure that their interactions are tested thoroughly. Here are some common integration testing strategies:

1. **Top-Down Integration Testing:**
   - **Approach:** This strategy begins the testing process from the top layer (like testing module which is more important)(or high-level modules) and progressively integrates lower-level modules. It aims to test the integration from the user interface downwards.
   - **Advantages:** It allows for early testing of crucial functionalities, facilitating the identification of critical issues at the higher levels of the system.
     ![](../../../statics/Pasted%20image%2020231104103445.png)
2. **Bottom-Up Integration Testing:**

   - **Approach:** In contrast to top-down, bottom-up integration testing starts from the lower-level modules and gradually adds higher-level modules or components. It verifies the integration from the bottom layers up.
   - **Advantages:** It allows for the early testing of foundational functionalities and addresses critical issues at the lower levels.
     ![](../../../statics/Pasted%20image%2020231104103416.png)

3. **Big Bang Integration Testing:**

   - **Approach:** In this strategy, all or most of the modules are integrated simultaneously. This means the complete system is put together and tested in one go.
   - **Advantages:** It provides an overall view of system behavior and interaction in a shorter period. However, it can be complex and might make it harder to isolate issues due to the comprehensive integration.

4. **Sandwich (Hybrid) Integration Testing:**
   - **Approach:** This strategy combines both top-down and bottom-up integration testing. It involves integrating some modules from the top down while integrating others from the bottom up.
   - **Advantages:** It balances the advantages of both top-down and bottom-up approaches, allowing for a more comprehensive testing approach that addresses issues at various levels.

These integration strategies differ in their approach to combining modules and are chosen based on the project's needs

#### Regression testing

Whenever a change in a software application is made, it is quite possible that other areas within the application have been affected by this change. Regression testing is performed to verify that a fixed bug hasn't resulted in another functionality or business rule violation. The intent of regression testing is to ensure that a change, such as a bug fix should not result in another fault being uncovered in the application.

#### Smoke testing

Testing the basic and critical feature of software instead of going for regress testing

Smoke Testing comes into the picture at the time of receiving build software from the development team. The purpose of smoke testing is to determine whether the build software is testable or not. It is done at the time of "building software." This process is also known as "Day 0".
Smoke test activity is the final step before the software build enters the system stage. Smoke tests must be performed on each build that is turned to testing. This applies to new development and major and minor releases of the system

In the smoke testing, we only focus on the positive flow of the application and enter only valid data, not the invalid data. In smoke testing, we verify every build is testable or not; hence it is also known as Build Verification Testing

Smoke Testing is done whenever the new functionalities of software are developed and integrated with existing build that is deployed in QA/staging environment. It ensures that all critical functionalities are working correctly or not. In this testing method, the development team deploys the build in QA. The subsets of test cases are taken, and then testers run test cases on the build. The QA team tests the application against the critical functionalitie

**+ves**

- Easy to perform testing
- Defects will be identified in early stages.
- Improves the quality of the system
- Reduces the risk
- Progress is easier to access.
- Saves test effort and time
- Easy to detect critical errors and correction of errors.
- It runs quickly
- Minimises integration risks
  ![](../../../statics/Pasted%20image%2020231104105143.png)

### System testing

System testing is a crucial phase in the software development life cycle that focuses on testing the entire software application as a complete and integrated system. It verifies that the software fulfills the specified requirements and functions as intended in the target environment before it is released to the end-users.

- It is a black box testing
- System testing categories based on : who is doing the testing
- System testing categories based on: Functional/Non-functional
- it is basically performed by testing team that is independent of development team that helps to test the quality of system impartial . it has both functional and non-functional testing.

#### Categories of system testing

System testing categories can be classified based on who is performing the testing and based on whether the testing is focusing on functional or non-functional aspects of the system.

##### System Testing Categories based on WHO is doing the testing:

1. **Alpha Testing:**
   Alpha Testing is a type of acceptance testing; performed to identify all possible issues and bugs before releasing the final product to the end users. Alpha testing is carried out by the testers who are internal employees of the organization. The main goal is to identify the tasks that a typical user might perform and test them. To put it as simple as possible, this kind of testing is called alpha only because it is done early on, near the end of the development of the software, and before beta testing. The main focus of alpha testing is to simulate real users by using a black box and white box techniques.
2. **Beta Testing:**
   Beta Testing is performed by “real users” of the software application in “real environment” and it can be considered as a form of external User Acceptance Testing. It is the final test before shipping a product to the customers. Direct feedback from customers is a major advantage of Beta Testing. This testing helps to test products in customer’s environment.

**Difference b/w Alpha testing and beta testing**
Difference between alpha and beta testing

- Alpha Testing is performed by the Testers within the organization whereas Beta Testing is performed by the end users.
- Alpha Testing is performed at Developer’s site whereas Beta Testing is performed at Client’s location.
- Reliability and Security testing are not performed in-depth in Alpha Testing while Reliability, Security and Robustness are checked during Beta Testing.
- Alpha Testing involves both White box and Black box testing whereas Beta Testing mainly involves Black box testing.
- Alpha Testing requires testing environment while Beta Testing doesn’t require testing environment.
- Alpha Testing requires long execution cycle whereas Beta Testing requires only few weeks of execution.
- Critical issues and bugs are addressed and fixed immediately in Alpha Testing whereas issues and bugs are collected from the end users and further implemented in Beta Testing.

Gamma Testing
Gamma Testing is done when software is ready for release with specified requirements, this testing done directly by skipping all the in-house testing activities. The software is almost ready for final release. No feature development or enhancement of the software is undertaken and tightly scoped bug fixes are the only code.

##### System Testing Categories based on Functional/Non-functional Aspects:

1. **Functional System Testing:**

   - Focuses on verifying that the software functions according to the defined functional requirements.
   - Includes tests that check specific functions, features, and operations of the system.

2. **Non-functional System Testing:**
   - Concentrates on aspects other than specific functions and operations.
   - Includes tests related to performance, load testing, stress testing, security, scalability.

##### Recovery testing

Recovery Testing is a system test that forces the software to fail in a variety of ways and verifies that recovery is properly performed. The purpose of Recovery Testing is to determine whether software operations can be continued after disaster or integrity loss. Recovery testing involves reverting back software to the point where integrity was known and reprocessing transactions to the failure point

##### Security testing

**Type of security testing**

- Vulnerability scanning
- security scanning
- penetration testing
- risk assessment
- Ethical hacking

##### Stress testing

Stress testing includes testing the behavior of software under abnormal conditions. For example, it may include taking away some resources or applying a load beyond the actual load limit. The aim of stress testing is to test the software by applying the load to the system and taking over the resources used by the software to identify the breaking point
These categories highlight not only the role and source of the testing but also whether the testing is directed towards the functionality of the system or its non-functional aspects. Both aspects are essential for ensuring the overall quality and reliability of the system.

##### Performance testing

Performance Testing is a software testing process used for testing the speed, response time, stability, reliability, scalability and resource usage of a software application under particular workload. The main purpose of performance testing is to identify and eliminate the performance bottlenecks in the software application. It is a subset of performance engineering and also known as “Perf Testing”.
The focus of Performance Testing is checking a software programs

- Speed – Determines whether the application responds quickly
- Scalability – Determines maximum user load the software application can handle.
- Stability – Determines if the application is stable under varying loads

Types of performance testing

- Load testing – checks the application’s ability to perform under anticipated user loads. The objective is to identify performance bottlenecks before the software application goes live.
- Endurance testing – is done to make sure the software can handle the expected load over a long period of time.
- Spike testing
- etc.
  Process of performance testing
  ![](../../../statics/Pasted%20image%2020231104114747.png)

### Acceptance testing

Acceptance testing, a testing technique performed to determine whether or not the software system has met the requirement specifications. The main purpose of this test is to evaluate the system's compliance with the business requirements and verify if it is has met the required criteria for delivery to end users.

## Software Test report

Software Test Report is a document which contains a summary of all test activities and final test results of a testing project. Test report is an assessment of how well the testing is performed

### Structure

1. Project Information All information of the project such as the project name, product name, and version should be described in the test report.
2. Test Objective Test Report should include the objective of each round of testing, such as Unit Test, Performance Test, System Test …Etc.
3. Test Summary This section includes the summary of testing activity in general. Information detailed here includes, number of test cases executed , number of test cases passed, pass percentage etc.
4. Defects:- like total number of bugs , status of bugs, number of bugs (open,closed ,resolved)

## Test Artifacts

Test artifacts are also known as test deliverables. These are the reports or documents created while the testing is being carried out.

1. **Test Plan:** A document that outlines the scope, approach, resources, and schedule of testing activities. It includes the objectives, strategies, and test estimation for a particular project.

2. **Test Cases:** Detailed descriptions of test scenarios, test conditions, inputs, execution steps, and expected results for specific functionalities or features of the software.

3. **Test Scripts:** A set of instructions or code used for automated testing. It defines the sequence of actions to be executed and validates whether the actual outcomes match the expected results.

4. **Test Scenarios:** High-level descriptions of the end-to-end functionality or behavior to be tested. They define the scope and aim of the testing and are used to derive detailed test cases.

5. **Test Data:** Specific sets of data used to test the software under various conditions, including valid, invalid, and edge cases. It helps in validating the behavior and performance of the software.

6. **Test Logs/Reports:** Records of test execution, including details such as test case status, defects found, issues encountered, and test environment configurations. These reports help in assessing the quality of the software.

7. **Traceability Matrix:** A document that traces and links test artifacts to the corresponding requirements. It ensures that each requirement is covered by test cases and helps in tracking the test coverage.

8. **Defect/Bug Reports:** Documentation of issues found during testing. It includes details like the description of the defect, steps to reproduce, severity, priority, and status of the defect.

9. **Test Summary Report:** A comprehensive report summarizing the overall testing efforts, including test coverage, pass/fail rates, critical defects, and recommendations for further actions.

10. **Test Strategy:** A document that defines the testing approach for the entire project, outlining the overall testing objectives, methods, and resources.

## Testing tools

There are two broad categories of software testing tools i.e. static and dynamic. Most of the tools fall clearly into one of these categories

### Static software testing tools

Static software testing tools are those that perform analysis of the programs without executing them at all.

- Complexity analysis tools:- A popular measure of complexity is the cyclomatic complexity(The concept behind cyclomatic complexity is rooted in the control flow of a program. It counts the number of decision points in the code, such as loops, conditional statements (if, else, switch), and other control structures). Tools are available which are based on any of the complexity measures. These tools may take the program as an input, process it and produce a complexity value as output.
- Syntax and semantic analysis tools:- There are tools in the market that may analyze the program and find errors. Non-declaration of a variable, double declaration of a variable,
- Flow graph generator tools:- These tools are language dependent and take the program as an input and convert it to its flow graph
- Code comprehension tools:- These tools may help us to understand unfamiliar source code. They may also identify dead source code, duplicate source code and areas that may require special attention and should be reviewed seriously
- Code inspector:- Source code inspectors do the simple job of enforcing standards in a uniform way for many programs. They inspect the programs and force us to implement the guidelines of good programming practices.

### Dynamic software testing tools

Dynamic software testing tools select test cases and execute the program to get the results. They also analyze the results and find reasons for failures (if any) of the program. They will be used after the implementation of the program and may also test non-functional requirements like efficiency, performance, reliability, etc

- Coverage analysis tools:- These tools are used to find the level of coverage of the program after executing the selected test cases. They give us an idea about the effectiveness of the selected test cases. They highlight the unexecuted portion of the source code and force us to design special test cases for that portion of the source code.
- Performance testing tools:-
- Functional / Regression Testing Tools:- These tools are used to test the software on the basis of its functionality without considering the implementation details.Some of the popular available tools are IBM Rational’s Robot

## CASE

### What is it

- CASE stands for computer aided software engineering . it means , development and maintenance of software projects with help of various automated software tools
- CASE tools are set of software application programs , which are used to automate SDLC activities . CASE tools are used by software manager , analysts and engineers to develop software system
- There are number of tools like analysis tools , design tools

### Component of CASE tools

![](../../../statics/Pasted%20image%2020231105081456.png)

- It can be divided into following parts
- Central repository :- CASE tools require a central repository , which can serve as a source of common , integrated and consistent information. Central repository is a central place of storage where product specifications , requirement document , related reports and diagrams , other useful info regarding management is stored
- Upper Case tools :- Used in planning , analysis and design stages of SDLC
- Lower Case tools:- Lowe CASE tools are used in implementation , testing and maintenance
- Integrated Case tools:- helpful in all stages of SDLC , from requirement gathering to testing and documentation

### Advantages and Disadvantages of CASE Tools

a) Advantages

- Produce system with a longer effective operational life.
- Produces system that more closely meet user needs and requirements.
- Produces system with excellent documentation.
- Produce more flexible system.
  b) Disadvantages
- Produce initial system that is more expensive to build and maintain
- Require more extensive and accurate definitions of user needs and requirements.
- May be difficult to customize.
- Require training of maintenance staff
- May be difficult to use with existing system

### CASE environment

CASE environment is a collection of CASE tools and other
components together with an integration ... Although individual CASE tools are useful, the true power of a tool set can be realized only when these set of tools are integrated into a common framework or
environment
![](../../../statics/Pasted%20image%2020231105081949.png)
Since totally different tools covering different stages share common data, it’s needed that they integrate
through some central repository to possess an even read of data related to the package development

### Architecture of CASE

![](../../../statics/Pasted%20image%2020231105082219.png)

#### User Interface

- user interface provides a regular framework for accessing the various tools so creating it easier for the users to act with the different tools and reducing the overhead of learning however the different tools are used.

#### Object Management System (OMS) and repository

Different case tools represent the product as a group of entities like specification, design, text data, project arrange, etc. the thing management system maps these logical entities such into the underlying
storage management system (repository).

### types of CASE tools

top five types of CASE (Computer-Aided Software Engineering) tools:

1. **Diagramming Tools:** Used for creating visual representations of system structures, processes, and data flows, such as Entity-Relationship Diagrams (ERD), Data Flow Diagrams (DFD), and Unified Modeling Language (UML) diagrams.

2. **Modeling Tools:** Support the creation of models representing different aspects of a system, including process models, data models, and object models. They aid in visualizing and documenting the system's architecture and design.

3. **Requirement Management Tools:** Assist in managing and documenting requirements, capturing user needs, and ensuring traceability between requirements and system design. These tools aid in requirement gathering, analysis, and tracking changes.

4. **Version Control Tools:** Help manage different versions and iterations of software, enabling collaboration among developers, tracking changes, and managing source code repositories.

5. **Testing Tools:** Aid in planning, executing, and managing the testing process, including unit testing, integration testing, system testing, and performance testing.
