## Depenedency injection and inversion of control

**Inversion of Control (IoC):**

Inversion of Control (IoC) is a design principle where the control flow of a program is inverted, meaning that instead of the application code controlling the flow of execution, the control is handed over to an external container or framework. In a traditional program, the main function or method controls the flow and calls various functions to perform tasks. With IoC, the control is inverted, and a framework or container takes charge of managing the flow and execution of the application.

The primary benefit of IoC is that it promotes a more modular and loosely coupled architecture. Components in the application are decoupled from each other, making it easier to replace or modify individual components without affecting the entire system. IoC is often implemented using a container or framework, such as the Spring IoC container, which manages the lifecycle of objects and their dependencies.

**Dependency Injection (DI):**

Dependency Injection (DI) is a specific implementation of the IoC principle. In a software system, objects often depend on other objects or services to perform their tasks. Traditionally, these dependencies are created within the class that requires them. With dependency injection, dependencies are "injected" into a class from the outside, rather than the class creating them internally.

There are three common types of dependency injection:

1. **Constructor Injection:** Dependencies are provided through the class constructor. This is the most common form of DI.

    ```java
    public class MyClass {
        private MyDependency myDependency;

        public MyClass(MyDependency myDependency) {
            this.myDependency = myDependency;
        }

        // rest of the class...
    }
    ```

2. **Setter Injection:** Dependencies are set through setter methods.

    ```java
    public class MyClass {
        private MyDependency myDependency;

        public void setMyDependency(MyDependency myDependency) {
            this.myDependency = myDependency;
        }

        // rest of the class...
    }
    ```

3. **Method Injection:** Dependencies are injected through methods.

    ```java
    public class MyClass {
        public void doSomething(MyDependency myDependency) {
            // use myDependency to do something
        }

        // rest of the class...
    }
    ```

Dependency injection makes the code more modular, testable, and flexible. It allows for easier substitution of components, as the dependencies can be changed without modifying the class that uses them. The Spring Framework, for example, utilizes dependency injection as a core concept, and it's often referred to as an Inversion of Control container due to its IoC capabilities.