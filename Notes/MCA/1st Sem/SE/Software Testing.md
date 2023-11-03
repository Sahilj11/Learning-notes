## Basics of testing
- Testing means software testing . it is done to find discrepancy in the developed software or existing software
- Approaches of testing
	- Black box testing: in this tester does not have the knowledge of the coding . in this testing we only check the functionality of software that is input be pass and output the s/w produce
	- ![[Pasted image 20231103144841.png]]
	- White box testing: in this tester has knowledge of coding and internal structure of existing software wheather the internal structure is correct or not
	- ![[Pasted image 20231103145019.png]]
	- notice here box is transparent
### Necessities and obj of software testing 
Software testing serves multiple necessities and objectives, crucial for ensuring the quality, reliability, and success of software applications. Here are the primary necessities and objectives of software testing:
### Necessities of Software Testing:
1. **Error Detection:**
   - Identifying and rectifying errors, defects, or bugs in the software before it reaches the end-users.
2. **Quality Assurance:**
   - Ensuring that the software meets predefined quality standards and fulfills user expectations.
3. **Risk Mitigation:**
   - Reducing the risks associated with software failures, which could result in financial losses, damage to reputation, or safety concerns.
4. **Compliance:**
   - Ensuring that the software adheres to regulatory, legal, and industry standards.
5. **Customer Satisfaction:**
   - Improving user experience by delivering a product that functions as intended and meets user needs.
6. **Cost Reduction:**
   - Identifying and rectifying issues early in the development cycle reduces the cost of fixing defects at later stages of development or after the software is released.
### Objectives of Software Testing:
1. **Validation and Verification:**
   - Ensuring that the software meets the specified requirements and that it functions as expected.

2. **Identifying Defects:**
   - Detecting and reporting defects and issues in the software to improve its quality and reliability.

3. **Improving Quality:**
   - Enhancing the overall quality of the software by eliminating errors and ensuring reliability.

4. **Risk Assessment:**
   - Evaluating and mitigating risks associated with the software's performance, security, and functionality.

5. **Assuring Functionality:**
   - Ensuring that all intended functionalities work correctly and meet user expectations.

6. **Documentation and Compliance:**
   - Providing documentation of the testing process and ensuring the software complies with necessary standards and regulations.

7. **Enhancing User Experience:**
   - Focusing on usability and user-friendliness to improve the overall user experience.

Software testing is essential to mitigate risks, assure quality, and provide confidence in the software's performance. By meeting these objectives and addressing these necessities, software testing contributes to delivering reliable, high-quality software that satisfies end-user requirements.
## Inspection vs testing
- Software inspection:- concerned with analysis of static system representation to discover problem (static verification)
	- May be supplement by tool based document and code analysis
- Software testing:- Concerned with excersising and observing product behaviour (dynamic verfication)
	- The system 
## Type of testing , more specifically it is levels of testing

![[Pasted image 20231103142031.png]]
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

2. **Bottom-Up Integration Testing:**
   - **Approach:** In contrast to top-down, bottom-up integration testing starts from the lower-level modules and gradually adds higher-level modules or components. It verifies the integration from the bottom layers up.
   - **Advantages:** It allows for the early testing of foundational functionalities and addresses critical issues at the lower levels.

3. **Big Bang Integration Testing:**
   - **Approach:** In this strategy, all or most of the modules are integrated simultaneously. This means the complete system is put together and tested in one go.
   - **Advantages:** It provides an overall view of system behavior and interaction in a shorter period. However, it can be complex and might make it harder to isolate issues due to the comprehensive integration.

4. **Sandwich (Hybrid) Integration Testing:**
   - **Approach:** This strategy combines both top-down and bottom-up integration testing. It involves integrating some modules from the top down while integrating others from the bottom up.
   - **Advantages:** It balances the advantages of both top-down and bottom-up approaches, allowing for a more comprehensive testing approach that addresses issues at various levels.

These integration strategies differ in their approach to combining modules and are chosen based on the project's needs

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
   - Testing performed by a select group of potential users or within the development team.
   - Usually carried out at the developer's site.

2. **Beta Testing:**
   - A broader user acceptance testing (UAT) stage where the software is released to a larger set of external users or customers.
   - Provides real-world feedback and often takes place at the customer's site.
##### System Testing Categories based on Functional/Non-functional Aspects:
1. **Functional System Testing:**
   - Focuses on verifying that the software functions according to the defined functional requirements.
   - Includes tests that check specific functions, features, and operations of the system.

2. **Non-functional System Testing:**
   - Concentrates on aspects other than specific functions and operations.
   - Includes tests related to performance, load testing, stress testing, security, scalability.

These categories highlight not only the role and source of the testing but also whether the testing is directed towards the functionality of the system or its non-functional aspects. Both aspects are essential for ensuring the overall quality and reliability of the system.