
## Closure
function bind together with its lexical scope forms closures 
- very important https://www.youtube.com/watch?v=qikxEIxsXco&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=12&ab_channel=AkshaySaini
- https://youtu.be/qikxEIxsXco?list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&t=887

```javascript
const FactoryFunction = string => {
  const capitalizeString = () => string.toUpperCase();
  const printString = () => console.log(`----${capitalizeString()}----`);
  return { printString };
};

const taco = FactoryFunction('taco');

printString(); // ERROR!!
capitalizeString(); // ERROR!!
taco.capitalizeString(); // ERROR!!
taco.printString(); // this prints "----TACO----"
```

The concept of closure is the idea that functions retain their lexical environment even if they are passed around and called outside of that scope. In this case, `printString` has access to everything inside of `FactoryFunction`, even if it gets called outside of that function.

Closures in JavaScript are a powerful concept that allows functions to remember and access variables from the parent scope, even after the parent function has finished executing. This behavior helps in preserving state and privacy within functions.

When a function is defined within another function, it forms a closure. The inner function has access to the variables and parameters of its outer (parent) function, as well as the global scope. This access is possible because the inner function maintains a reference to its parent's scope, even after the parent function has completed its execution.

Let's see an example to illustrate how closures help keep state and privacy within a function:

```javascript
function outerFunction() {
  var outerVariable = 'I am from the outer function';

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

var closure = outerFunction(); // Invoke outerFunction, and assign the returned innerFunction to the variable closure
closure(); // Invoke innerFunction
```

In this example, the `outerFunction` defines an inner function called `innerFunction`. The `innerFunction` has access to the `outerVariable` defined within its parent scope, even though the `outerFunction` has finished executing.

By returning the `innerFunction` from the `outerFunction` and assigning it to the variable `closure`, we create a closure. The closure preserves the reference to the `outerVariable`, allowing us to access it even when the `outerFunction` has completed its execution.

When we invoke `closure()`, it logs the value of `outerVariable`, which is "I am from the outer function", demonstrating that the closure retains access to the state (the value of `outerVariable`) from the `outerFunction`.

Closures are powerful because they enable functions to have private variables. Any variables defined within the scope of the outer function are not directly accessible from outside. They are only accessible through functions defined within the scope, like the `innerFunction` in the example above. This provides a level of privacy, as the variables can only be accessed and manipulated by the functions that form closures over them.

Closures are commonly used to create private data and encapsulated behavior in JavaScript. They allow for the implementation of modules, where variables and functions are kept private within a closure, and only selected parts are exposed for public use.

Overall, closures help maintain state and privacy within functions by allowing inner functions to retain access to variables in their parent scope even after the parent function has completed execution. This behavior enables the creation of private variables and encapsulated functionality in JavaScript.

Here’s another example:

```javascript
const counterCreator = () => {
  let count = 0;
  return () => {
    console.log(count);
    count++;
  };
};

const counter = counterCreator();

counter(); // 0
counter(); // 1
counter(); // 2
counter(); // 3
```

In this example, `counterCreator` initializes a local variable (`count`) and then returns a function. To use that function, we have to assign it to a variable (line 9). Then, every time we run the function it logs `count` to the console and increments it. Keep in mind, `counter()` is calling the return value of `counterCreator`. As above, the function `counter` is a closure. It has access to the variable `count` and can both print and increment it, but there is no other way for our program to access that variable

## Private variable and function 
In JavaScript, there is no built-in mechanism for defining private variables and functions at the language level. However, you can achieve a similar effect using various techniques such as closures or the module pattern.

Private variables and functions are essentially those that are only accessible within a particular scope, typically within an enclosing function or object. They cannot be accessed or modified directly from outside that scope.

Here's an example of creating private variables and functions using closures:

```javascript
function createCounter() {
  let count = 0; // private variable

  function increment() {
    count++; // private function
    console.log(count);
  }

  function decrement() {
    count--;
    console.log(count);
  }

  return {
    increment: increment,
    decrement: decrement
  };
}

const counter = createCounter();
counter.increment(); // Output: 1
counter.increment(); // Output: 2
counter.decrement(); // Output: 1
```

In the above example, the `createCounter` function encapsulates the `count` variable and the `increment` and `decrement` functions. The `count` variable is only accessible within the `createCounter` function, and the `increment` and `decrement` functions have access to that variable due to closures.

When you invoke `createCounter`, it returns an object that exposes the `increment` and `decrement` functions. These functions can access and modify the private `count` variable, but the variable itself cannot be directly accessed or modified from outside the `createCounter` function.

Another approach to creating private variables and functions is using the module pattern. In this pattern, you can define a function that serves as a module and exposes only the necessary public API, keeping the rest of the variables and functions private. Here's an example:

```javascript
const counter = (function() {
  let count = 0; // private variable

  function increment() {
    count++; // private function
    console.log(count);
  }

  function decrement() {
    count--;
    console.log(count);
  }

  return {
    increment: increment,
    decrement: decrement
  };
})();

counter.increment(); // Output: 1
counter.increment(); // Output: 2
counter.decrement(); // Output: 1
```

In this example, the counter module is an immediately-invoked function expression (IIFE). The `count` variable and the `increment` and `decrement` functions are defined within the scope of the IIFE and are not directly accessible outside it. The IIFE returns an object with the public methods `increment` and `decrement`, which provide controlled access to the private variables and functions.

These are two common techniques to simulate private variables and functions in JavaScript. They allow you to encapsulate logic and data, restricting access to certain parts of your code and promoting encapsulation and data hiding principles.

## Object.assign
The `Object.assign()` method in JavaScript is used to copy the values of all enumerable properties from one or more source objects to a target object. It merges the properties from the source objects into the target object.

The syntax for `Object.assign()` is as follows:

```javascript
Object.assign(target, ...sources)
```

Here, `target` is the object to which the properties will be copied, and `sources` are one or more objects from which the properties will be copied. The method returns the modified `target` object.

Let's see an example to better understand how `Object.assign()` works:

```javascript
const target = { name: "John" };
const source = { age: 30, city: "New York" };

const mergedObject = Object.assign(target, source);

console.log(mergedObject); // Output: { name: "John", age: 30, city: "New York" }
console.log(target); // Output: { name: "John", age: 30, city: "New York" }
```

In the above example, we have a `target` object with a single property `name`, and a `source` object with properties `age` and `city`. We use `Object.assign()` to copy the properties from `source` to `target`. The resulting object is stored in the `mergedObject` variable.

After the merge, both `mergedObject` and `target` contain the merged properties. The properties from the `source` object are added to the `target` object, and any existing properties in the `target` object with the same names are overwritten.

It's important to note that `Object.assign()` performs a shallow copy, meaning that it only copies the property values at the top level. If the property values are objects themselves, they are not cloned but rather copied by reference. This means that changes to the source object will be reflected in the target object and vice versa.

`Object.assign()` is commonly used for object cloning, property merging, and creating a new object based on existing objects. If you want to perform a deep copy, including nested objects, you would need to implement a custom solution or use libraries like Lodash or Ramda.

Properties in the target object are overwritten by properties in the sources if they have the same [key](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys). Later sources' properties overwrite earlier ones.

The `Object.assign()` method only copies _enumerable_ and _own_ properties from a source object to a target object. It uses `[[Get]]` on the source and `[[Set]]` on the target, so it will invoke [getters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) and [setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set). Therefore it _assigns_ properties, versus copying or defining new properties. This may make it unsuitable for merging new properties into a prototype if the merge sources contain getters.

For copying property definitions (including their enumerability) into prototypes, use [`Object.getOwnPropertyDescriptor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor) and [`Object.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty) instead.

Both [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) and [`Symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) properties are copied.

In case of an error, for example if a property is non-writable, a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) is raised, and the `target` object is changed if any properties are added before the error is raised.

## Inheritance
JavaScript is often praised for its flexibility and expressive nature, particularly when it comes to creating and inheriting from objects without relying on traditional class-based inheritance. This is because JavaScript utilizes prototype-based inheritance, which provides a dynamic and powerful way to create and extend objects.

In JavaScript, objects can be created using constructor functions or object literals. When a constructor function is used with the `new` keyword, it creates a new object instance. The constructor function can define properties and methods on the object using the `this` keyword. Here's an example:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function() {
  console.log("Hello, my name is " + this.name);
};

const person = new Person("John");
person.sayHello(); // Output: Hello, my name is John
```

In the above example, we define a `Person` constructor function that takes a `name` parameter and assigns it to the `name` property of the object being created using `this.name = name;`. We also add a method `sayHello` to the prototype of `Person`, which can be shared by all instances of `Person`. When we create a new `Person` object with `new Person("John")`, it inherits the properties and methods defined in the constructor function.

JavaScript uses prototypal inheritance, where objects can inherit properties and methods from other objects. Each object in JavaScript has an internal link to another object called its prototype. If a property or method is accessed on an object and it doesn't exist, JavaScript checks the prototype chain to look for the property or method in the object's prototype and its parent prototypes.

To create an object that inherits from another object, you can use the `Object.create()` method. Here's an example:

```javascript
const person = {
  name: "John",
  sayHello: function() {
    console.log("Hello, my name is " + this.name);
  }
};

const employee = Object.create(person);
employee.jobTitle = "Engineer";

employee.sayHello(); // Output: Hello, my name is John
console.log(employee.jobTitle); // Output: Engineer
```

In this example, we have an object `person` with a `name` property and a `sayHello` method. We then create a new object `employee` using `Object.create(person)`. The `employee` object inherits the properties and methods from `person`. We can add new properties to `employee` directly, such as `jobTitle`.

This prototype-based approach in JavaScript allows for flexible object creation and inheritance. It allows objects to inherit from multiple prototypes, which is known as "object composition" or "mixins". Additionally, you can modify and extend prototypes dynamically at runtime, enabling powerful runtime modifications and customizations.

Overall, this prototype-based approach in JavaScript offers a more dynamic and flexible way to create and inherit from objects compared to traditional class-based inheritance found in many other programming languages.


## Module Design pattern 
The module design pattern in JavaScript is a way to encapsulate related variables, functions, and objects into a single, self-contained unit. It provides a structure for organizing and separating code into reusable modules, promoting modularity, encapsulation, and information hiding

![](../../statics/Pasted%20image%2020230708103752.png )

The module pattern typically involves creating a function that acts as a closure, defining private variables and functions within that closure. It then returns an object that exposes only the necessary properties and methods, effectively creating a public API for interacting with the module while keeping the internal implementation hidden.

Here's an example of implementing the module pattern in JavaScript:

```javascript
var MyModule = (function() {
  // Private variables and functions
  var privateVariable = 10;

  function privateFunction() {
    console.log('This is a private function.');
    console.log('Private variable:', privateVariable);
  }

  // Public API
  return {
    publicVariable: 20,

    publicFunction: function() {
      console.log('This is a public function.');
      console.log('Public variable:', this.publicVariable);
      privateFunction();
    }
  };
})();

// Usage
console.log(MyModule.publicVariable); // Output: 20
MyModule.publicFunction(); // Output: This is a public function.
                           //         Public variable: 20
                           //         This is a private function.
                           //         Private variable: 10
```

**accessing a module is actually accessing whatever it returns**.

Modules can house not only functions, but arrays, objects and primitives as well.
everything publicly exposed can be changed from the outside. This is one of the biggest module pattern drawbacks.

In this example, we define a module called `MyModule` using an immediately invoked function expression (IIFE). Inside the IIFE, we have private variables (`privateVariable`) and a private function (`privateFunction`). These variables and functions are only accessible within the closure and cannot be directly accessed from the outside.

The IIFE returns an object literal that serves as the public interface of the module. It exposes the `publicVariable` and `publicFunction` properties, which are accessible from outside the module. The `publicFunction` can also access the private variables and functions defined within the closure, creating a bridge between the public and private parts of the module.

By following the module pattern, we achieve encapsulation and information hiding. The private variables and functions are not accessible directly, ensuring data privacy and preventing external code from modifying or interfering with the internal state of the module. Only the properties and methods exposed through the public API can be accessed and utilized by other parts of the code.

The module pattern promotes modularity by allowing the codebase to be divided into smaller, focused modules. Each module can have its own private state and behavior, and can interact with other modules only through their public APIs. This makes the code easier to understand, maintain, and reuse.

It's worth noting that with the introduction of ES6 modules in modern JavaScript, there is a more standardized and native way to achieve module-based development. However, the module design pattern still holds value in scenarios where more fine-grained control over encapsulation and information hiding is required or in environments that don't support ES6 modules natively.

Overall, the module design pattern in JavaScript enables the creation of self-contained and reusable modules, providing encapsulation, information hiding, and modularity to the codebase.

#### Benefits 
- reusability 
- Composability
- Leverage 
- Isolation 
- Organisation 
