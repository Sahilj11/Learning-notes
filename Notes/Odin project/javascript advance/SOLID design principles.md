## Advantages of SOLID principle 
Following the SOLID principles brings several benefits to software development:
1. Maintainability: SOLID principles promote code that is easier to understand, modify, and maintain. Each principle focuses on a specific aspect of software design that contributes to code maintainability. By adhering to these principles, developers can easily locate and make changes to specific areas of the codebase without affecting unrelated parts.
2. Flexibility and Extensibility: SOLID principles encourage the creation of code that is open for extension and closed for modification (OCP). This allows new functionality to be added without altering existing code, reducing the risk of introducing bugs or unintended side effects. It promotes a modular and flexible design, making it easier to adapt to changing requirements and add new features.
3. Testability: SOLID principles contribute to writing testable code. Following the principles helps in isolating units of code and dependencies, making it easier to write unit tests. By having single responsibilities (SRP) and loosely coupled components (DIP), it becomes simpler to mock or substitute dependencies during testing, leading to more effective and comprehensive test coverage.
4. Reusability: SOLID principles encourage the creation of components that are decoupled, highly cohesive, and have clear responsibilities. This promotes code reuse as these components can be easily integrated into different projects or parts of the same project. The principles, such as the Liskov Substitution Principle (LSP) and Interface Segregation Principle (ISP), ensure that code is designed to be easily replaceable and adaptable.
5. Scalability: By following SOLID principles, software architecture becomes more scalable. The principles help in managing complexity, reducing dependencies, and keeping codebases modular and maintainable. This makes it easier to add new features, refactor existing code, and handle increased user load or system complexity without sacrificing stability or performance.
6. Collaboration: SOLID principles provide a common set of guidelines and best practices that facilitate collaboration among developers. When everyone follows these principles, the codebase becomes more consistent, easier to understand, and predictable. It improves teamwork, code reviews, and knowledge sharing within development teams.

Overall, the adoption of SOLID principles leads to higher-quality software with improved maintainability, flexibility, testability, reusability, scalability, and collaboration, ultimately resulting in reduced costs and enhanced customer satisfaction.

## Brief
The SOLID principles are a set of five design principles that help in developing maintainable and scalable software. Here are the full forms of each principle:
- Single Responsibility Principle (SRP): A class should have only one reason to change. It states that a class should have a single responsibility or job, and it should be focused on fulfilling that responsibility.
	- Every module or class should have responsibility over a single part of functionality provided by software , and that responsibility should be entirely encapsulated by the class
-  Open-Closed Principle (OCP): Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. It means that you should be able to add new functionality to a system without modifying its existing code.
-  Liskov Substitution Principle (LSP): Objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program. It ensures that subtypes must be substitutable for their base types.
-  Interface Segregation Principle (ISP): Clients should not be forced to depend on interfaces they do not use. It promotes the idea of segregating large interfaces into smaller and more specific interfaces so that clients only need to know about the methods that are relevant to them.
- Dependency Inversion Principle (DIP): High-level modules should not depend on low-level modules; both should depend on abstractions. It states that the dependency relationship between classes should be based on abstractions or interfaces rather than concrete implementations.
These principles, when followed, help in creating software that is easier to understand, maintain, and extend over time.

### Single responsiblity principle

The Single Responsibility Principle (SRP) states that a class should have only one reason to change or, in other words, it should have a single responsibility. It emphasizes the idea that a class should be focused on doing one thing well, which leads to more maintainable and modular code.

Here's an example to illustrate the Single Responsibility Principle:

Let's consider a hypothetical scenario where we have a `User` class that represents a user in a system. The `User` class may have several responsibilities, such as managing user authentication, handling user data persistence, and sending notification emails.

Without adhering to SRP:
```python
class User:
    def authenticate(self, username, password):
        # Code for user authentication
        
    def save(self):
        # Code for saving user data to the database
        
    def send_notification_email(self, message):
        # Code for sending notification emails to the user
```

In the above example, the `User` class has multiple responsibilities: authentication, data persistence, and sending emails. This violates the SRP because if any of these responsibilities change, it would require modifying the `User` class, affecting the overall stability and maintainability of the code.

By following the SRP, we can separate these responsibilities into separate classes, each with a single responsibility. Here's an improved version:

```python
class UserAuthenticator:
    def authenticate(self, username, password):
        # Code for user authentication

class UserRepository:
    def save(self, user):
        # Code for saving user data to the database

class NotificationService:
    def send_notification_email(self, user, message):
        # Code for sending notification emails to the user

class User:
    def __init__(self, username, password):
        self.username = username
        self.password = password

# Usage
authenticator = UserAuthenticator()
repository = UserRepository()
notifier = NotificationService()

user = User("john_doe", "password")
authenticator.authenticate(user.username, user.password)
repository.save(user)
notifier.send_notification_email(user, "Welcome to our system!")
```

In this improved version, the responsibilities of authentication, data persistence, and sending emails are delegated to separate classes. The `User` class now only focuses on representing a user with its properties and doesn't have multiple reasons to change.

By separating responsibilities, we achieve code that is easier to understand, maintain, and extend. Changes to one responsibility, such as authentication, will not impact other parts of the codebase, promoting modularity and reducing the risk of introducing bugs in unrelated areas.

This description can be a little misleading as it would seem to suggest that an object should only do one thing. What is meant by this assertion, however, is that an object should have a cohesive set of behaviors, together comprising a single responsibility that, if changed, would require the modification of the object’s definition.  More simply, an object’s definition should only have to be modified due to changes to a single responsibility within the system.

This principle refers to the **idea of having a cohesive set of behaviors within an object, which collectively represent a single responsibility.** According to this principle, if any of these behaviors need to be modified, it should only require changes to the object's definition, rather than modifications throughout the entire system.

To understand this principle, let's take an example:

Consider a `Customer` class that represents a customer in an e-commerce system. This class may have behaviors such as registering a new customer, managing their personal information, and processing orders. These behaviors collectively define the responsibility of the `Customer` class.

If any changes are needed in the way customer orders are processed, it would be ideal if these modifications are confined to the `Customer` class. The modifications should not require changes in other parts of the system, such as the user interface or the database management.

Following the principle of having a cohesive set of behaviors and a single responsibility, the `Customer` class would be defined in a way that isolates and encapsulates the order processing functionality. This would allow modifications related to order processing to be made solely within the `Customer` class.

For instance:

```python
class Customer:
    def register(self, name, email):
        # Register the customer with the given name and email

    def updatePersonalInfo(self, info):
        # Update the personal information of the customer

    def processOrder(self, order):
        # Process the given order

    def calculateOrderTotal(self, order):
        # Calculate the total amount for the order
```

In the above example, the `Customer` class encapsulates behaviors related to customer registration, personal information management, order processing, and order total calculation. Each behavior represents a cohesive set of actions related to a specific responsibility within the system.

If there are changes in the order processing logic, such as introducing a new discount mechanism or modifying the calculation algorithm, the modifications can be made within the `processOrder()` or `calculateOrderTotal()` methods. These changes would be isolated within the `Customer` class, and other parts of the system would remain unaffected.

By adhering to this principle, an object's definition, such as the `Customer` class, only needs to be modified due to changes in a single responsibility, making the code more maintainable, modular, and easier to understand. It helps prevent unintended consequences and reduces the risk of introducing errors when making changes within a complex system.
### Open closed principle 

The Open-Closed Principle (OCP) states that software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. It encourages the creation of code that can be easily extended with new functionality without requiring changes to its existing code.

To understand the Open-Closed Principle, let's consider an example:

Imagine we have a `Shape` class hierarchy that represents different shapes like circles, rectangles, and triangles. Each shape has a `calculateArea()` method that calculates its area. Initially, we have implementations for circles and rectangles:

```python
class Shape:
    def calculateArea(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def calculateArea(self):
        return 3.14 * self.radius**2

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def calculateArea(self):
        return self.width * self.height
```

Now, suppose we want to add a new shape, a `Triangle`, and calculate its area. Without adhering to the OCP, we might be tempted to modify the existing `Shape` class hierarchy:

```python
class Shape:
    def calculateArea(self):
        pass

class Circle(Shape):
    # ...

class Rectangle(Shape):
    # ...

class Triangle(Shape):
    def __init__(self, base, height):
        self.base = base
        self.height = height

    def calculateArea(self):
        return 0.5 * self.base * self.height
```

However, modifying the existing code violates the OCP since it introduces changes to the original implementation. Instead, we can extend the code without modifying it by introducing an abstraction and leveraging polymorphism.

```python
class Shape:
    def calculateArea(self):
        pass

class Circle(Shape):
    # ...

class Rectangle(Shape):
    # ...

class Triangle(Shape):
    def __init__(self, base, height):
        self.base = base
        self.height = height

    def calculateArea(self):
        return 0.5 * self.base * self.height

class AreaCalculator:
    def calculate(self, shape):
        return shape.calculateArea()
```

In the updated code, we introduce the `AreaCalculator` class responsible for calculating the area of any shape. It takes advantage of polymorphism by accepting any `Shape` object as a parameter and calling its `calculateArea()` method.

```python
calculator = AreaCalculator()
circle = Circle(5)
rectangle = Rectangle(4, 6)
triangle = Triangle(3, 4)

print(calculator.calculate(circle))     # Output: 78.5
print(calculator.calculate(rectangle))  # Output: 24
print(calculator.calculate(triangle))   # Output: 6
```

By following the OCP, we've extended the behavior of the system by introducing a new shape, `Triangle`, without modifying the existing code. We achieved this by depending on abstractions (the `Shape` base class) and leveraging polymorphism, making the system open for extension but closed for modification.

### Liskov substitution principle 

if you an have an superclass lets say animal and a subclass named lion then every single place where are using animal class , you should also be able to use the lion subclass without breaking the functionality.

The Liskov Substitution Principle (LSP) is a principle in object-oriented programming that defines a relationship between a base class and its derived classes. It states that objects of a superclass should be substitutable with objects of its subclasses without affecting the correctness of the program.

To understand the LSP, let's consider an example involving a class hierarchy of shapes:

```python
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Square(Shape):
    def __init__(self, side_length):
        self.side_length = side_length

    def area(self):
        return self.side_length * self.side_length
```

In the above example, we have a base class `Shape` and two derived classes, `Rectangle` and `Square`. Each class defines an `area()` method to calculate the area of the respective shape.

According to the Liskov Substitution Principle, instances of the derived classes (`Rectangle` and `Square`) should be able to substitute instances of the base class (`Shape`) without affecting the correctness of the program. This means that wherever a `Shape` object is expected, we should be able to use a `Rectangle` or `Square` object interchangeably.

Let's see how the LSP applies:

```python
def print_area(shape):
    print("Area:", shape.area())

rectangle = Rectangle(4, 6)
square = Square(4)

print_area(rectangle)  # Output: Area: 24
print_area(square)    # Output: Area: 16
```

In the example above, the `print_area()` function expects a `Shape` object as an argument. However, we pass both a `Rectangle` object and a `Square` object to the function, demonstrating that instances of the derived classes can be substituted for the base class.

The LSP guarantees that the program will behave correctly regardless of whether a `Shape`, `Rectangle`, or `Square` object is passed to the `print_area()` function. This is because the `area()` method is defined consistently across the class hierarchy, and the behavior is specialized but consistent with the base class.

However, if we were to violate the LSP by changing the behavior of the derived classes in a way that breaks the substitution, issues may arise:

```python
class Square(Shape):
    # ...

    def area(self):
        return self.side_length ** 2 + 1  # Violates LSP

print_area(square)  # Output: Area: 17 (incorrect)
```

In the modified `Square` class, the `area()` method returns an incorrect calculation. As a result, when we pass a `Square` object to `print_area()`, it produces an incorrect area value. This violates the LSP because the derived class behavior no longer aligns with the expectations of the base class.

By adhering to the Liskov Substitution Principle, we ensure that derived classes can be used interchangeably with the base class, allowing for extensibility, polymorphism, and predictable behavior within the system.

### Interface segregation principle 

The Interface Segregation Principle (ISP) is a principle in object-oriented design that emphasizes the importance of defining fine-grained interfaces that are specific to the needs of clients. It states that clients should not be forced to depend on interfaces they do not use.

In simpler terms, the ISP suggests that interfaces should be tailored to the exact requirements of the client, rather than having large, monolithic interfaces that encompass every possible method. This helps in avoiding unnecessary dependencies and ensuring that clients only depend on the parts of an interface that are relevant to them.

Let's consider an example to understand the ISP better:

Imagine a scenario where we have an interface called `Printer` that provides printing functionality. It has methods like `print()`, `scan()`, and `fax()`. However, not all clients or classes need all of these methods. Some clients may only need to print, while others may need to scan and fax as well.

Without applying the ISP, we might have a single monolithic interface like this:

```python
class Printer:
    def print(self):
        pass

    def scan(self):
        pass

    def fax(self):
        pass
```

Now, let's say we have two different clients: `PhotoPrinter` and `OfficeScanner`. The `PhotoPrinter` class only needs the `print()` method, while the `OfficeScanner` class only needs the `scan()` and `fax()` methods.

Applying the ISP, we would segregate the interface into more specialized interfaces based on the needs of clients:

```python
class Print:
    def print(self):
        pass

class Scan:
    def scan(self):
        pass

class Fax:
    def fax(self):
        pass
```

With the segregated interfaces, the clients can now depend only on the specific interfaces they require:

```python
class PhotoPrinter(Print):
    def print(self):
        # Print photo implementation

class OfficeScanner(Scan, Fax):
    def scan(self):
        # Scan document implementation

    def fax(self):
        # Fax document implementation
```

By using the segregated interfaces, the `PhotoPrinter` class only needs to implement the `Print` interface, and the `OfficeScanner` class implements both the `Scan` and `Fax` interfaces. This approach ensures that each client is not burdened with unnecessary methods that they don't use.

The benefits of the Interface Segregation Principle include:
- Reducing the risk of tight coupling between classes.
- Promoting a clearer and more focused design by tailoring interfaces to specific needs.
- Enhancing modularity and flexibility as clients can depend on smaller and more specific interfaces.
- Facilitating easier maintenance and evolution of code as changes in one interface do not affect unrelated clients.

In summary, the Interface Segregation Principle guides us to design interfaces that are specific to the requirements of clients, avoiding the burden of unnecessary dependencies and promoting a more modular and maintainable codebase.

### Dependency Inversion principle 
The Dependency Inversion Principle (DIP) is a principle in object-oriented design that suggests high-level modules should not depend on low-level modules directly. Instead, both should depend on abstractions. It promotes loose coupling, flexibility, and easier maintenance of software systems.

Let's consider an example of an e-commerce store that integrates with payment processors like PayPal and Stripe. The traditional approach would involve the e-commerce store directly depending on the specific implementations of the PayPal and Stripe APIs.

Without applying the DIP:
```python
class PayPalAPI:
    def process_payment(self, amount):
        # Code for processing payment via PayPal

class StripeAPI:
    def process_payment(self, amount):
        # Code for processing payment via Stripe

class ECommerceStore:
    def __init__(self):
        self.paypal = PayPalAPI()
        self.stripe = StripeAPI()

    def checkout(self, payment_method, amount):
        if payment_method == 'paypal':
            self.paypal.process_payment(amount)
        elif payment_method == 'stripe':
            self.stripe.process_payment(amount)
```

In the above code, the `ECommerceStore` directly depends on the concrete implementations of the PayPal and Stripe APIs. This leads to tight coupling between the store and the payment processors, making it difficult to switch or introduce new payment processors in the future. It violates the DIP.

Applying the DIP, we introduce an abstraction layer to decouple the high-level module (`ECommerceStore`) from the low-level modules (payment processors) using interfaces or abstract classes:

```python
class PaymentProcessor:
    def process_payment(self, amount):
        pass

class PayPalAPI(PaymentProcessor):
    def process_payment(self, amount):
        # Code for processing payment via PayPal

class StripeAPI(PaymentProcessor):
    def process_payment(self, amount):
        # Code for processing payment via Stripe

class ECommerceStore:
    def __init__(self, payment_processor):
        self.payment_processor = payment_processor

    def checkout(self, amount):
        self.payment_processor.process_payment(amount)
```

In this updated code, we introduce the `PaymentProcessor` abstract class (or interface) that defines the common `process_payment()` method. The `PayPalAPI` and `StripeAPI` classes implement this abstract class.

Now, the `ECommerceStore` class depends on the `PaymentProcessor` abstraction rather than the concrete implementations. During initialization, the store receives the desired payment processor, allowing for easy swapping or addition of new payment processors without modifying the store's code.

Here's an example of using the updated code:

```python
paypal_processor = PayPalAPI()
stripe_processor = StripeAPI()

store = ECommerceStore(paypal_processor)
store.checkout(100)

store = ECommerceStore(stripe_processor)
store.checkout(200)
```

By applying the DIP, the e-commerce store now depends on the abstraction (`PaymentProcessor`), making it flexible and decoupled from the specific payment processors. It allows for easier maintenance, testing, and future extension of the system with different payment processors or updates to existing ones.