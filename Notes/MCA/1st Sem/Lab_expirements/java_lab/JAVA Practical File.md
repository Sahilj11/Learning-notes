
### 1. Method Overloading:

```java
class MathOperations {
    // Method to add two integers
    int add(int a, int b) {
        System.out.println("Adding two integers:");
        return a + b;
    }

    // Method to add three integers
    int add(int a, int b, int c) {
        System.out.println("Adding three integers:");
        return a + b + c;
    }

    // Method to add two doubles
    double add(double a, double b) {
        System.out.println("Adding two doubles:");
        return a + b;
    }

    // Method to add an array of integers
    int add(int[] numbers) {
        System.out.println("Adding an array of integers:");
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        return sum;
    }

    // Method to concatenate two strings
    String add(String str1, String str2) {
        System.out.println("Concatenating two strings:");
        return str1 + str2;
    }
}

public class MethodOverloadingExample {
    public static void main(String[] args) {
        MathOperations mathOps = new MathOperations();

        // Testing different overloaded methods
        System.out.println("Result 1: " + mathOps.add(5, 10));
        System.out.println("Result 2: " + mathOps.add(2.5, 3.5));
        System.out.println("Result 3: " + mathOps.add(1, 2, 3));

        int[] numbers = {1, 2, 3, 4, 5};
        System.out.println("Result 4: " + mathOps.add(numbers));

        System.out.println("Result 5: " + mathOps.add("Hello, ", "World!"));
    }
}

```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214192008.png)
### 2. Interface Implementation:

```java
// Interface for shape calculations
interface Shape {
    double calculateArea();

    double calculatePerimeter();
}

// Concrete class representing a rectangle
class Rectangle implements Shape {
    private double length;
    private double width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    public double calculateArea() {
        return length * width;
    }

    @Override
    public double calculatePerimeter() {
        return 2 * (length + width);
    }
}

// Interface for color information
interface Colorable {
    String getColor();
}

// Concrete class representing a colored rectangle
class ColoredRectangle extends Rectangle implements Colorable {
    private String color;

    ColoredRectangle(double length, double width, String color) {
        super(length, width);
        this.color = color;
    }

    @Override
    public String getColor() {
        return color;
    }
}

public class InterfaceImplementationExample {
    public static void main(String[] args) {
        Rectangle rectangle = new Rectangle(5, 10);
        System.out.println("Rectangle Area: " + rectangle.calculateArea());
        System.out.println("Rectangle Perimeter: " + rectangle.calculatePerimeter());

        ColoredRectangle coloredRectangle = new ColoredRectangle(4, 8, "Blue");
        System.out.println("Colored Rectangle Area: " + coloredRectangle.calculateArea());
        System.out.println("Colored Rectangle Perimeter: " + coloredRectangle.calculatePerimeter());
        System.out.println("Colored Rectangle Color: " + coloredRectangle.getColor());
    }
}
```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214192219.png)
### 3. Polymorphism and Method Overriding:

```java
// Base class Animal with method makeSound
class Animal {
    void makeSound() {
        System.out.println("Animal makes a generic sound");
    }
}

// Derived class Dog extending Animal and overriding makeSound
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }

    // Additional method specific to Dog
    void fetch() {
        System.out.println("Dog fetches the ball");
    }
}

// Derived class Cat extending Animal and overriding makeSound
class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat meows");
    }

    // Additional method specific to Cat
    void climb() {
        System.out.println("Cat climbs a tree");
    }
}

// Derived class Bird extending Animal and overriding makeSound
class Bird extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bird sings");
    }

    // Additional method specific to Bird
    void fly() {
        System.out.println("Bird flies away");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        // Creating an array of Animal objects
        Animal[] animals = new Animal[3];
        animals[0] = new Dog();
        animals[1] = new Cat();
        animals[2] = new Bird();

        // Demonstrating polymorphism and method overriding
        for (Animal animal : animals) {
            animal.makeSound();

            // Additional methods specific to subclasses
            if (animal instanceof Dog) {
                ((Dog) animal).fetch();
            } else if (animal instanceof Cat) {
                ((Cat) animal).climb();
            } else if (animal instanceof Bird) {
                ((Bird) animal).fly();
            }

            System.out.println(); // Adding a newline for clarity
        }
    }
}

```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214192409.png)
### 4. Multithreading:

```java
class Task implements Runnable {
    private String taskName;

    Task(String name) {
        this.taskName = name;
    }

    @Override
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(taskName + " - Count: " + i + " - Thread ID: " + Thread.currentThread().getId());
            try {
                Thread.sleep(1000); // Simulating some work
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class MultithreadingExample {
    public static void main(String[] args) {
        System.out.println("Main Thread ID: " + Thread.currentThread().getId());

        // Creating multiple threads
        Thread thread1 = new Thread(new Task("Task 1"));
        Thread thread2 = new Thread(new Task("Task 2"));
        Thread thread3 = new Thread(new Task("Task 3"));

        // Starting the threads
        thread1.start();
        thread2.start();
        thread3.start();

        // Wait for all threads to finish before exiting the main thread
        try {
            thread1.join();
            thread2.join();
            thread3.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Main Thread exiting.");
    }
}
```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214192600.png)

### 5. Various Types of Inheritance:

```java
// Base class
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }

    void sleep() {
        System.out.println("Animal is sleeping");
    }
}

// Derived class inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}

// Interface for flying behavior
interface Flyable {
    void fly();
}

// Interface for swimming behavior
interface Swimmable {
    void swim();
}

// Derived class inheriting from Animal and implementing Flyable and Swimmable
class Duck extends Animal implements Flyable, Swimmable {
    @Override
    void eat() {
        System.out.println("Duck is eating");
    }

    @Override
    void sleep() {
        System.out.println("Duck is sleeping");
    }

    @Override
    public void fly() {
        System.out.println("Duck is flying");
    }

    @Override
    public void swim() {
        System.out.println("Duck is swimming");
    }
}

// Derived class inheriting from Animal
class Cat extends Animal {
    void meow() {
        System.out.println("Cat is meowing");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        // Single Inheritance
        Dog dog = new Dog();
        dog.eat();
        dog.sleep();
        dog.bark();
        System.out.println();

        // Multiple Inheritance using Interfaces
        Duck duck = new Duck();
        duck.eat();
        duck.sleep();
        duck.fly();
        duck.swim();
        System.out.println();

        // Hierarchical Inheritance
        Cat cat = new Cat();
        cat.eat();
        cat.sleep();
        cat.meow();
    }
}
```

![](../../../../statics/Pasted%20image%2020231214192803.png)

### 6. Interface Inheritance:
```java
// Base interface
interface Shape {
    void draw();
}

// Extended interface inheriting from Shape
interface ColoredShape extends Shape {
    String getColor();
}

// Concrete class implementing ColoredShape
class Circle implements ColoredShape {
    private String color;

    Circle(String color) {
        this.color = color;
    }

    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }

    @Override
    public String getColor() {
        return color;
    }
}

// Extended interface inheriting from ColoredShape
interface BorderColoredShape extends ColoredShape {
    String getBorderColor();
}

// Concrete class implementing BorderColoredShape
class Square implements BorderColoredShape {
    private String color;
    private String borderColor;

    Square(String color, String borderColor) {
        this.color = color;
        this.borderColor = borderColor;
    }

    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }

    @Override
    public String getColor() {
        return color;
    }

    @Override
    public String getBorderColor() {
        return borderColor;
    }
}

public class InterfaceInheritanceExample {
    public static void main(String[] args) {
        // Using ColoredShape interface
        ColoredShape coloredCircle = new Circle("Red");
        coloredCircle.draw();
        System.out.println("Color: " + coloredCircle.getColor());
        System.out.println();

        // Using BorderColoredShape interface
        BorderColoredShape borderedSquare = new Square("Blue", "Black");
        borderedSquare.draw();
        System.out.println("Color: " + borderedSquare.getColor());
        System.out.println("Border Color: " + borderedSquare.getBorderColor());
    }
}
```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214193018.png)
### 7. Calculating Factorial:

```java
public class FactorialExample {
    static int factorial(int n) {
        if (n == 0 || n == 1) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }

    public static void main(String[] args) {
        int num = 5;
        System.out.println("Factorial of " + num + " is: " + factorial(num));
    }
}
```

### 8. Handling User-Defined Exceptions:

```java
// Custom exception class
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

// Class representing a person with an age validation method
class Person {
    private String name;
    private int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method to validate age and throw custom exception if age is invalid
    void validateAge() throws InvalidAgeException {
        if (age < 0 || age > 120) {
            throw new InvalidAgeException("Invalid age: " + age);
        }
        System.out.println("Age validation successful for " + name + ".");
    }
}

public class UserDefinedExceptionExample {
    public static void main(String[] args) {
        try {
            // Creating a person with an invalid age
            Person person1 = new Person("John", -5);
            person1.validateAge(); // This will throw an InvalidAgeException

        } catch (InvalidAgeException e) {
            System.out.println("Caught an exception: " + e.getMessage());
        }

        try {
            // Creating a person with a valid age
            Person person2 = new Person("Alice", 25);
            person2.validateAge(); // This will pass validation

        } catch (InvalidAgeException e) {
            System.out.println("Caught an exception: " + e.getMessage());
        }
    }
}

```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231214193247.png)
### 9. Abstract Classes:

```java
// Abstract class representing a Vehicle
abstract class Vehicle {
    private String brand;
    private String model;
    private int year;

    public Vehicle(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // Abstract method to get the vehicle type
    abstract String getVehicleType();

    // Concrete method to display vehicle information
    void displayInfo() {
        System.out.println("Vehicle Type: " + getVehicleType());
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}

// Concrete class representing a Car
class Car extends Vehicle {
    private int numDoors;

    public Car(String brand, String model, int year, int numDoors) {
        super(brand, model, year);
        this.numDoors = numDoors;
    }

    @Override
    String getVehicleType() {
        return "Car";
    }

    // Additional method specific to Car
    void start() {
        System.out.println("Car is starting");
    }
}

// Concrete class representing a Motorcycle
class Motorcycle extends Vehicle {
    private boolean hasSideCar;

    public Motorcycle(String brand, String model, int year, boolean hasSideCar) {
        super(brand, model, year);
        this.hasSideCar = hasSideCar;
    }

    @Override
    String getVehicleType() {
        return "Motorcycle";
    }

    // Additional method specific to Motorcycle
    void wheelie() {
        System.out.println("Motorcycle is doing a wheelie");
    }
}

public class AbstractClassExample {
    public static void main(String[] args) {
        // Creating instances of concrete classes
        Car myCar = new Car("Toyota", "Camry", 2022, 4);
        Motorcycle myMotorcycle = new Motorcycle("Harley-Davidson", "Sportster", 2021, false);

        // Using abstract class methods
        myCar.displayInfo();
        myCar.start();
        System.out.println();

        myMotorcycle.displayInfo();
        myMotorcycle.wheelie();
    }
}
```

![](../../../../statics/Pasted%20image%2020231214193457.png)
### 10. User-Defined Packages:

```java
// Assuming your package structure is like com.example
package com.example;

public class PackageExample {
    public static void main(String[] args) {
        System.out.println("This is an example of user-defined package");
    }
}
```


### 11. Creating a File:

```java
import java.io.File;
import java.io.IOException;

public class CreateFileExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            } else {
                System.out.println("File already exists.");
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

OUTPUT:
![](../../../../statics/Pasted%20image%2020231215081803.png)

### 12. Reading from a File:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFileExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("example.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

OUTPUT:

![](../../../../statics/Pasted%20image%2020231215081948.png)
### 13. Writing to a File:

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteFileExample {
    public static void main(String[] args) {
        try (FileWriter writer = new FileWriter("example.txt")) {
            writer.write("Hello, this is an example of writing to a file.");
            System.out.println("Write successful!");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

![](../../../../statics/Pasted%20image%2020231215082050.png)

### 14. Creating a Frame:

```java
import javax.swing.JFrame;

public class CreateFrameExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("My Frame");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

### 15. Adding a File Menu:

```java
import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;

public class FileMenuExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Menu Example");

        JMenuBar menuBar = new JMenuBar();
        JMenu fileMenu = new JMenu("File");
        JMenuItem newItem = new JMenuItem("New");
        JMenuItem openItem = new JMenuItem("Open");
        JMenuItem exitItem = new JMenuItem("Exit");

        fileMenu.add(newItem);
        fileMenu.add(openItem);
        fileMenu.add(exitItem);
        menuBar.add(fileMenu);

        frame.setJMenuBar(menuBar);

        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

![](../../../../statics/Pasted%20image%2020231214194007.png)
### 16. Adding a ComboBox:

```java
import javax.swing.JComboBox;
import javax.swing.JFrame;

public class ComboBoxExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("ComboBox Example");

        String[] items = {"Item 1", "Item 2", "Item 3", "Item 4", "Item 5"};

        JComboBox<String> comboBox = new JComboBox<>(items);
        comboBox.setBounds(50, 50, 100, 30);

        frame.add(comboBox);

        frame.setSize(400, 300);
        frame.setLayout(null);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

![](../../../../statics/Pasted%20image%2020231214194107.png)

