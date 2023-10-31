## Property getters and setters
There are two kinds of object properties.

The first kind is _data properties_(where value is set beforehand). We already know how to work with them. All properties that we’ve been using until now were data properties.

The second type of property is something new. It’s an _accessor property_. They are essentially functions that execute on getting and setting a value, but look like regular properties to an external code.
## Accessor or data property , one at a time 
In JavaScript, a property can either be an "accessor property" or a "data property," but not both simultaneously. This means that a property cannot have both a `get` or `set` method and a direct value assigned to it. Let's understand the difference between these two types of properties:

1. Accessor Property:
   - An accessor property is defined using `get` and/or `set` methods.
   - The `get` method is responsible for retrieving the value of the property when it is accessed.
   - The `set` method is responsible for assigning a new value to the property when it is modified.
   - Accessor properties do not have a direct value associated with them.

2. Data Property:
   - A data property is defined by assigning a value directly to the property.
   - The value of the property is stored directly in memory and can be accessed or modified directly.
   - Data properties do not have `get` and `set` methods associated with them.

To illustrate this, let's consider an example:

```javascript
const obj = {
  // Accessor property
  get accessorProp() {
    return // logic to retrieve the value
  },
  set accessorProp(value) {
    // logic to set the value
  },
  
  // Data property
  dataProp: "some value"
};
```

In the above example, `accessorProp` is an accessor property defined with `get` and `set` methods. It does not have a direct value associated with it. On the other hand, `dataProp` is a data property with a direct value assigned to it.

It's important to note that when you define a property using an object literal (`{}`), you can choose either an accessor property or a data property for that property name. However, you can mix accessor and data properties for different properties within the same object.

In cases where you need to have both custom behavior and a value associated with a property, you can use a combination of accessor properties and separate data properties to achieve the desired functionality.
## Getter and Setter 
In JavaScript, you can define properties with custom behavior using getter and setter methods. These methods are known as "accessor" properties. Accessor properties allow you to define custom logic for getting and setting the value of a property, providing more control and flexibility.

To create an accessor property, you can use the `get` and `set` keywords within an object literal or with `Object.defineProperty()`.

Here's an example using an object literal:

```javascript
const obj = {
  get propertyName() {
    // Getter logic
    return // return some value
  },
  
  set propertyName(value) {
    // Setter logic
    // process the assigned value
  }
};
```

In the example above, the `propertyName` is an accessor property. The `get` block defines the logic for retrieving the value, and the `set` block defines the logic for assigning a new value.

You can also use `Object.defineProperty()` to define accessor properties:

```javascript
const obj = {};

Object.defineProperty(obj, 'propertyName', {
  get() {
    // Getter logic
    return // return some value
  },
  
  set(value) {
    // Setter logic
    // process the assigned value
  }
});
```

With `Object.defineProperty()`, you can provide additional attributes for the property, such as configurability, enumerability, and more, by specifying them in the property descriptor object.

Accessor properties are useful when you want to perform additional operations or validations when getting or setting a property's value. They allow you to encapsulate the behavior within the object and provide a controlled interface for interacting with the property.

## Define property
`Object.defineProperty()` is a built-in method in JavaScript that allows you to define a new property directly on an object or modify an existing property on an object. It provides a way to define additional attributes for a property, such as configurability, enumerability, and writability.

The syntax for `Object.defineProperty()` is as follows:

```javascript
Object.defineProperty(object, property, descriptor)
```

- `object`: The object on which to define or modify the property.
- `property`: The name or symbol of the property to be defined or modified.
- `descriptor`: An object that contains the attributes and behavior of the property.

The `descriptor` object can have the following properties:

- `value`: The value of the property.
- `writable`: A boolean indicating whether the property's value can be changed. Default is `false`.
- `enumerable`: A boolean indicating whether the property can be enumerated. Default is `false`.
- `configurable`: A boolean indicating whether the property can be redefined or deleted. Default is `false`.
- `get`: A function that serves as a getter for the property, called when the property is accessed.
- `set`: A function that serves as a setter for the property, called when the property is assigned a new value.

By using `Object.defineProperty()`, you can have more fine-grained control over the properties of an object, including defining custom getters and setters, setting property attributes, and more.
## Smarter getters/setters
Getters/setters can be used as wrappers over “real” property values to gain more control over operations with them.

For instance, if we want to forbid too short names for `user`, we can have a setter `name` and keep the value in a separate property `_name`:
```javascript
let user = { 
   get name() { 
     return this._name; 
     }, 
   set name(value) { 
       if (value.length < 4) { 
	       alert("Name is too short, need at least 4 characters"); 
	         return; 
        } 
        this._name = value; 
	}
}; 
user.name = "Pete"; 
alert(user.name); // Pete user.name = ""; // Name is too short...
```
So, the name is stored in `_name` property, and the access is done via getter and setter.

Technically, external code is able to access the name directly by using `user._name`. But there is a widely known convention that properties starting with an underscore `"_"` are internal and should not be touched from outside the object.

#### Compatibility 
In the provided code example, accessors (getter and setter) are used to take control over a "regular" data property (`age`) and tweak its behavior without having to modify the existing code that uses the `age` property.

Initially, the `User` constructor function was implemented with a `name` and `age` data property:

```javascript
function User(name, age) {
  this.name = name;
  this.age = age;
}

let john = new User("John", 25);

alert(john.age); // 25
```

Later, it was decided that storing the `birthday` instead of the `age` property would be more precise and convenient. However, there is existing code that still relies on the `age` property.

To address this, a getter for the `age` property is added in the `User` constructor function:

```javascript
function User(name, birthday) {
  this.name = name;
  this.birthday = birthday;

  Object.defineProperty(this, "age", {
    get() {
      let todayYear = new Date().getFullYear();
      return todayYear - this.birthday.getFullYear();
    }
  });
}

let john = new User("John", new Date(1992, 6, 1));

alert(john.birthday); // birthday is available
alert(john.age); // ...as well as the age
```

By using `Object.defineProperty()`, a getter is defined for the `age` property. The getter calculates the age based on the current date and the stored `birthday` property. Now, when you access `john.age`, the getter function is executed, returning the calculated age instead of the original `age` value.

This approach allows you to keep the existing code intact while providing a more precise and convenient `age` property based on the `birthday`. The getter provides a seamless transition, making the old code continue to work as expected, while also offering the additional benefit of the `age` property.

## Class
In JavaScript, classes are a syntactical construct introduced in ECMAScript 2015 (ES6) that provides a more familiar syntax for defining objects and their behavior in an object-oriented programming (OOP) style. Classes serve as blueprints for creating objects with shared properties and methods.

The basic definition of a class in JavaScript consists of the following components:

- `class` keyword: Classes are defined using the `class` keyword, followed by the name of the class.
- Constructor method: The `constructor()` method is a special method within a class that is called when a new instance of the class is created using the `new` keyword. It allows you to initialize the object's properties.
- Class methods: These are functions defined within the class that are accessible to the instances of the class. They define the behavior of the objects created from the class.
- Class properties: These are variables or values that are associated with the class and its instances. They can be accessed and modified by the class methods.
- `new` keyword: To create a new instance of a class, you use the `new` keyword followed by the class name and any necessary arguments passed to the constructor method.

Here's an example of a simple class definition:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}
```

In the above example, the `Person` class is defined with a constructor method that takes `name` and `age` as parameters and assigns them to the respective properties of the instance. The `sayHello()` method is defined within the class and can be called on instances of the `Person` class to log a greeting message.

To create a new instance of the `Person` class:

```javascript
const john = new Person("John", 25);
```

With classes, you can create multiple instances of objects with the same structure and behavior defined by the class. Classes in JavaScript provide a more organized and readable way to implement object-oriented programming concepts in the language.

## Class vs constructor 
Still, there are important differences.
1. First, a function created by `class` is labelled by a special internal property `[[IsClassConstructor]]: true`. So it’s not entirely the same as creating it manually.
    The language checks for that property in a variety of places. For example, unlike a regular function, it must be called with `new`:
    `class User {   constructor() {} }  alert(typeof User); // function User(); // Error: Class constructor User cannot be invoked without 'new'`
    Also, a string representation of a class constructor in most JavaScript engines starts with the “class…”
    `class User {   constructor() {} }  alert(User); // class User { ... }`
    There are other differences, we’ll see them soon.
2. Class methods are non-enumerable. A class definition sets `enumerable` flag to `false` for all methods in the `"prototype"`.
    That’s good, because if we `for..in` over an object, we usually don’t want its class methods.
3. Classes always `use strict`. All code inside the class construct is automatically in strict mode.
Besides, `class` syntax brings many other features that we’ll explore later.

### Static methods 
In JavaScript, static methods are methods that belong to a class rather than an instance of the class. Unlike regular methods, static methods are not accessed or called on objects created from the class, but are called directly on the class itself. Static methods are often used to perform utility functions or operations that are not dependent on specific instances of the class.

Here's an example that demonstrates the usage of static methods in JavaScript:

```javascript
class MathUtils {
  static square(x) {
    return x * x;
  }

  static sum(a, b) {
    return a + b;
  }
}

console.log(MathUtils.square(5)); // Output: 25
console.log(MathUtils.sum(3, 7)); // Output: 10
```

In the above example, `square()` and `sum()` are static methods defined within the `MathUtils` class. They can be accessed directly on the class itself, without the need to create an instance of the class. In this case, `MathUtils.square(5)` returns the square of 5, which is 25, and `MathUtils.sum(3, 7)` returns the sum of 3 and 7, which is 10.

Static methods cannot access instance-specific properties or methods of the class because they are not associated with any specific instance. They can only access other static members (methods or properties) of the class.

It's worth noting that static methods are not exclusive to JavaScript classes. They can also be defined in regular JavaScript objects or functions, allowing you to create standalone utility functions without the need for a class structure.


### Instance 
In JavaScript, an instance refers to an individual object that is created from a class or constructor function. When you create an instance, you are essentially creating a new object that inherits properties and methods from a class or constructor.

To create an instance in JavaScript, you can use the `new` keyword along with a constructor function. Here's an example:

```javascript
// Constructor function
function Person(name, age) {
  this.name = name;
  this.age = age;
}

// Creating instances
var person1 = new Person("John", 25);
var person2 = new Person("Jane", 30);
```

In the above example, the `Person` function acts as a constructor for creating person objects. The `new` keyword is used to instantiate new instances. The `person1` and `person2` objects are instances of the `Person` constructor.

Each instance created from the constructor function has its own set of properties. In this case, each `Person` instance has a `name` and `age` property, which can be accessed and modified independently. For example:

```javascript
console.log(person1.name); // Output: "John"
console.log(person2.age);  // Output: 30

person1.age = 26;
console.log(person1.age); // Output: 26
```

Instances also inherit methods from the constructor's prototype. You can define methods on the constructor's prototype property, and all instances created from that constructor will have access to those methods. For example:

```javascript
Person.prototype.sayHello = function() {
  console.log("Hello, my name is " + this.name);
};

person1.sayHello(); // Output: "Hello, my name is John"
person2.sayHello(); // Output: "Hello, my name is Jane"
```

In summary, an instance in JavaScript is an individual object created from a class or constructor function, with its own set of properties and the ability to inherit methods from the constructor's prototype.

### Class inheritance 
In JavaScript, class inheritance allows you to create a hierarchy of classes where child classes inherit properties and methods from parent classes. This is achieved using the `extends` keyword.

Here's an example that demonstrates class inheritance in JavaScript:

```javascript
// Parent class
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(this.name + " makes a sound.");
  }
}

// Child class inheriting from Animal
class Dog extends Animal {
  constructor(name) {
    super(name); // Calling the parent class constructor
    you can also do : super.speak(); // it will call the speak function of       parent class
  }

  speak() {
    console.log(this.name + " barks.");
  }
}

// Creating instances
var animal = new Animal("Generic Animal");
var dog = new Dog("Bobby");

animal.speak(); // Output: "Generic Animal makes a sound."
dog.speak();    // Output: "Bobby barks."
```

In the above example, we have a parent class `Animal` with a constructor and a `speak()` method. The child class `Dog` is defined using the `extends` keyword, indicating that it inherits from the `Animal` class. The `Dog` class also has its own constructor and a modified `speak()` method.

To establish inheritance, the child class constructor must call the parent class constructor using the `super` keyword. This ensures that the parent class's constructor is executed, allowing the child class to inherit its properties.

In this case, when we create an instance of `Dog` (`var dog = new Dog("Bobby")`), it calls the `Animal` constructor through `super(name)`, passing the name to the parent class. The `speak()` method is overridden in the `Dog` class, so when we invoke `dog.speak()`, it outputs `"Bobby barks."`.

It's important to note that JavaScript classes support single inheritance, meaning a class can only inherit from one parent class. However, you can create multiple levels of inheritance by extending child classes further.

```javascript
class Poodle extends Dog {
  constructor(name) {
    super(name);
  }

  speak() {
    console.log(this.name + " is a poodle and barks.");
  }
}

var poodle = new Poodle("Charlie");
poodle.speak(); // Output: "Charlie is a poodle and barks."
```

In this example, the `Poodle` class inherits from the `Dog` class, which in turn inherits from the `Animal` class. The `speak()` method is overridden in each class, resulting in different outputs when invoking the method.

Class inheritance in JavaScript allows for creating hierarchical structures, promoting code reuse and modularity. It enables child classes to inherit and override properties and methods from parent classes, providing flexibility in designing object-oriented systems.

### Inheritance vs Composition 
In object-oriented programming, both inheritance and composition are ways to establish relationships between classes. Let's explore each concept with an example:

Inheritance:
Inheritance is a mechanism where a class inherits properties and behaviors from another class, often referred to as the parent or base class. The derived class, also known as the child or subclass, extends or specializes the functionality of the base class.

Example:

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"
```

In this example, we have a base class `Animal` with a common property `name` and a common behavior `speak()`. The derived classes `Dog` and `Cat` inherit from the `Animal` class and provide their own implementation of the `speak()` method. They specialize the behavior of the base class to match the specific sounds made by dogs and cats.

Composition:
Composition is a design approach where a class contains one or more instances of other classes as member variables. It allows building complex objects by combining smaller, self-contained components.

Example:

```python
class Engine:
    def start(self):
        print("Engine started.")

    def stop(self):
        print("Engine stopped.")

class Car:
    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()

    def stop(self):
        self.engine.stop()
```

In this example, we have a `Car` class that has a composition relationship with the `Engine` class. The `Car` class contains an instance of the `Engine` class as a member variable. It delegates the start and stop operations to the `Engine` object.

With composition, the `Car` class can use the functionalities of the `Engine` class without the need for inheritance. It provides a way to build complex objects by combining simpler components, promoting code reuse and modularity.

In summary:
- Inheritance establishes an "is-a" relationship, where a derived class inherits from a base class to specialize or extend its functionality.
- Composition establishes a "has-a" relationship, where a class contains instances of other classes as member variables to create more complex objects.

Both inheritance and composition have their uses, and the choice depends on the specific needs and relationships between classes in the design of the system. Inheritance is useful for sharing common behavior and modeling class hierarchies, while composition is useful for building objects by combining smaller components.

### Super keyword 
In JavaScript, the `super` keyword is used to call functions on an object's parent. It is commonly used within classes and extends the functionality of the parent class or superclass within a child class or subclass.

The `super` keyword has two primary use cases:

1. **Accessing Parent Object's Properties:**
   - In a constructor of a child class, `super()` is used to call the constructor of the parent class, allowing the child class to inherit properties and behavior from its parent.

   ```javascript
   class Parent {
       constructor(name) {
           this.name = name;
       }
   }

   class Child extends Parent {
       constructor(name, age) {
           super(name);
           this.age = age;
       }
   }

   const childObj = new Child('Alice', 8);
   console.log(childObj.name); // Output: Alice
   console.log(childObj.age);  // Output: 8
   ```

2. **Calling Parent Object's Methods:**
   - When you want to access a method from the parent class within the child class, `super.methodName()` is used.

   ```javascript
   class Parent {
       greet() {
           return 'Hello, I am the parent.';
       }
   }

   class Child extends Parent {
       greet() {
           return super.greet() + ' And I am the child.';
       }
   }

   const childObj = new Child();
   console.log(childObj.greet()); // Output: Hello, I am the parent. And I am the child.
   ```

The `super` keyword provides a way to access and call the methods and properties of the superclass from a subclass while maintaining the inheritance hierarchy.