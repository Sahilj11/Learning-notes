### everything in JS happens inside an execution context 
- contains 2 component 
	- memory component (variable environment)
		- where all the variable and functions are stored as key value pair
	- code component (thread of execution)
		- place where code is executed one line at a time

## JS is synchronous single-threaded language
- single threaded :- means JS can execute one command at a time 
- synchronous single threaded :- JS can execute one command at a time and in specific order

## How JS code is executed 
- first global execution context is created 
	- created in 2 phase
		- creation phase (memory creation phase):- JS will allocate memory to all variable and function. in memory component , variable are stored as undefined(initially , even if in code value have been assigned to them) and function are stored with complete code
		  - 2nd phase is code execution , line by line code execution take place , if JS encounter a variable assigned value it  populated in memory component that variable value from undefined to the assigned value. if a function is defined then nothing happens as the code is already in memory component . but if a function is called in the code . a brand new execution context is created inside the code component with its own memory and code component
		  ![[Pasted image 20230623065903.png]]
		  - after creation of execution context inside the code component when function is declared , it goes through same process . first variable is stored as undefined in memory 
		  - after the function is done running this execution context of function will be deleted (whenever the same function is called again execution context will be created)
- Call stack (execution context stack , program stack ,control stack , runtime stack , machine stack)
	- at the bottom is global execution context 
	- after that function execution context (it is removed after function is done running) 

## Variable and function hoisting in JS 
- hoisting :- accessing the function and variable even before there initialization 
```javascript
getName();
console.log(x); // try console.log(getName);

var x = 5;
function getName(){
  console.log("Namaste");
}
const getName = () =>{   // Important , read the below explanation why this will through error on 2nd line of code for getName 
 console.log("Namaste");
}
```
- here console log of x will show undefined (even though the x is initalised after that line )
- if we try `console.log(getName)` the log will show the complete function written in logs .
- this is happening because even before code execution , memory allocation of each and every function and variable is done . (remember that variable is stored as undefined initially )
- in arrow function , the name of function behave like a variable  (so its value will initially be undefined)
- Hoisting is **the default behavior of moving all the declarations at the top of the scope before code execution**. Basically, it gives us an advantage that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.
	- Hoisting is indeed the default behavior in JavaScript where all variable and function declarations are moved to the top of their respective scopes before the code is executed.
	- When JavaScript code is executed, it goes through two phases: the compilation phase and the execution phase. During the compilation phase, the JavaScript engine scans through the code and identifies all variable and function declarations. It allocates memory for variables and creates references for functions. This process is called hoisting because it gives the illusion that these declarations are physically lifted to the top of their containing scope.
	- As a result of hoisting, you can use variables and invoke functions before they are actually written in the code. For example, you can call a function before it appears in the code, or reference a variable before it is declared. However, it's important to note that only the declarations are hoisted, not the initializations or assignments. So, while you can access variables and functions before their declarations, their values may be `undefined` until they are assigned or invoked.
	- Hoisting applies to both global scope and local scopes. In the global scope, variables and functions are hoisted to the top of the script. In local scopes (such as inside a function), variables and functions are hoisted to the top of their respective scope.
	- It's worth mentioning that although hoisting is a default behavior, it is recommended to declare variables and functions at the beginning of their scope to make the code more readable and avoid potential confusion. Understanding hoisting can help you better understand how JavaScript code is executed and the order in which declarations are processed.
- Hoisting in JavaScript is a mechanism where variable and function declarations are moved to the top of their respective scopes during the compilation phase. This allows them to be accessed before they are actually defined in the code. For variables declared with `var`, hoisting involves moving the declaration to the top, while their assignments remain in place. Function declarations are hoisted entirely, including their bodies. However, variables declared with `let` and `const` are hoisted but remain in a "temporal dead zone" until their declarations are encountered, preventing early access. It is important to note and understand hoisting to avoid potential issues and write more robust code.
- Here's an example to illustrate this behavior:
```javascript
console.log(myVariable); // Output: undefined var myVariable = 10;
console.log(myVariable); // Output: 10
```
- In the example above, the variable `myVariable` is declared and assigned the value of `10` later in the code. Even though the first `console.log` statement appears before the declaration, it does not throw an error. Instead, it prints `undefined` because the declaration is hoisted to the top, but the assignment occurs at its original position.

## How functions work in JS
- ![[Pasted image 20230623074418.png]]
- output was 10,100,1
- ![[Pasted image 20230623074830.png]]
- ![[Pasted image 20230623075038.png]]
- notice that GEC is on line 3 
- ![[Pasted image 20230623075128.png]]

### Window and this in JS
- Window :- JS engine at start create an global object created with global execution context.  object is named window and this window object contains various function which can be accessed from anywhere in the code
- this :- this variable is also created with global execution context and window object automatically by JS . at global level it points to the window object.
- every browser or server have different name for JS engine like in chrome it is V8
- Global space :- anything which is not inside a function is in global space
- whenever we create function or variable in global space it gets attached to the window object

### JS is loosely typed language
- it does not attach its variable to any specific datatype. for example it let a = 10 , later you can do a = "10".

### Scope Chain, Scope & Lexical Environment
- Scope:- where you can access a variable or function 
### Lexical environment 
A lexical environment is a concept in JavaScript that refers to the environment or context in which variables and functions are defined and accessed. It consists of two main components: an environment record and a reference to the outer environment.

The environment record is a record of all the variables and their values within a particular scope. It holds the actual memory locations of variables and their current values.

The outer environment reference points to the lexical environment of the parent scope. It allows access to variables and functions defined in the outer (enclosing) scope.

Lexical environments are created during the compilation phase(memory phase) of JavaScript code. Each time a function is invoked or a block is entered, a new lexical environment is created, which forms a hierarchy of nested environments.

This lexical structure is important for variable scoping and function execution. When a variable is referenced, JavaScript looks for it in the current lexical environment. If it doesn't find the variable, it then checks the outer environment, and so on, until it either finds the variable or reaches the global scope.

Here's an example to illustrate lexical environments:

```javascript
function outer() {
  const outerVariable = 'Hello';

  function inner() {
    const innerVariable = 'World';
    console.log(outerVariable + ' ' + innerVariable);
  }

  inner();
}

outer();
```

In this example, we have two nested functions: `outer` and `inner`. Each function has its own lexical environment. When the `inner` function is executed, it first looks for the `outerVariable` in its own lexical environment and finds it in the outer environment. It then concatenates the values of `outerVariable` and `innerVariable` to output "Hello World" to the console.

Lexical environments help maintain variable scope and provide the necessary context for executing functions within their respective scopes. They play a crucial role in understanding how JavaScript code accesses and resolves variables in different scopes throughout the execution of a program.
- whenever execution context is created a lexical environment is also created . 
- Lexical environment is the local memory along the lexical environment of its parent
- Lexical means hierarchy 

- ![[Pasted image 20230623082656.png]]
- here the output will be 10 (`console.log(b)`) on last line
- ![[Pasted image 20230623082810.png]]
- here the orange is the reference to the lexical environment its of parent
- global lexical points to NULL
- ![[Pasted image 20230623083220.png]]
- here when c function is called , JS look for variable b , it is not there . then it use lexical environment reference to look in a's function execution context and it finds it there (reason why b is 10 in a context instead of undefined is because it was called in line 9, before the c function calling)
#### Scope chain
Certainly! The scope chain is a concept closely related to lexical environments in JavaScript.
Imagine you have a series of rooms, one inside the other, like a set of nested Russian dolls. Each room represents a different lexical environment, which holds variables and functions.

When JavaScript needs to find a variable or function while executing your code, it starts by looking in the current lexical environment. If it doesn't find the variable or function there, it moves up to the next outer lexical environment and continues searching. This process continues until the global scope is reached, which is the outermost environment.

The sequence of nested lexical environments that JavaScript traverses to find a variable or function is called the scope chain.

Here's an example to illustrate the concept:

```javascript
function outer() {
  var x = 10;

  function inner() {
    console.log(x); // Accessing variable 'x'
  }

  inner(); // Calling the inner function
}

outer(); // Calling the outer function
```

In this example, we have an outer function that defines a variable `x` and an inner function that tries to access `x`.

When the inner function is executed, JavaScript first looks for the variable `x` within its own lexical environment. If it doesn't find `x` there, it moves up the scope chain to the outer lexical environment (which belongs to the outer function) and checks if `x` is defined there. In this case, it finds `x` and logs its value, which is 10.

The scope chain allows functions to access variables defined in their outer environments. Each function has access to variables in its own lexical environment and all the surrounding outer environments, forming a chain of nested scopes.

By following the scope chain, JavaScript can maintain the correct scope and provide access to variables and functions defined in the appropriate lexical environments, even when they are nested inside each other.

### let & const in JS 🔥Temporal Dead Zone
In JavaScript, `let` and `const` declarations also exhibit hoisting, but with some differences compared to `var` declarations.
![[Pasted image 20230623095517.png]]
- although even before initializing the let or const variable , it is allocated undefined value but it is not in global space . they are allocated in separate memory space and we cannot access these until some value is initialized in them

1. `let` Hoisting:
   Variables declared with `let` are hoisted to the top of their block scope, but they are not initialized. This means that you cannot access a `let` variable before its declaration in the code, as it remains in the "temporal dead zone" until the point of declaration.

   Here's an example to illustrate `let` hoisting:

   ```javascript
   console.log(myVariable);  // Throws ReferenceError
   let myVariable = 10;
   console.log(myVariable);  // Output: 10
   ```

   In this example, the first `console.log` statement throws a `ReferenceError` because `myVariable` is in the temporal dead zone until its declaration is reached.

2. `const` Hoisting:
   Similarly to `let`, `const` declarations are also hoisted to the top of their block scope, but they are not initialized and remain in the temporal dead zone until the point of declaration. However, `const` variables must be assigned a value when they are declared and cannot be reassigned later.

   Here's an example to illustrate `const` hoisting:

   ```javascript
   console.log(myConstant);  // Throws ReferenceError
   const myConstant = 5;
   console.log(myConstant);  // Output: 5
   ```

   In this example, the first `console.log` statement throws a `ReferenceError` because `myConstant` is in the temporal dead zone until its declaration is reached.

Overall, the main difference between hoisting behavior of `var`, `let`, and `const` is related to the temporal dead zone. `var` declarations are hoisted and initialized with a value of `undefined`, allowing them to be accessed before the declaration. However, `let` and `const` declarations are hoisted but remain uninitialized until their actual declarations, resulting in a reference error if accessed before that point. Therefore, it's good practice to declare `let` and `const` variables at the beginning of their respective scopes to avoid any hoisting-related issues.
- temporal dead zone :- time b/w since this let variable was hoisted and till it is initalised some value
- const should be delcarated and initialised together , you cannot assign it later.

### ERROR types
In JavaScript, there are three common types of errors that can occur: ReferenceError, TypeError, and SyntaxError. Here's a brief explanation of each:

1. ReferenceError:
   A ReferenceError is thrown when you try to access a variable or function that is not declared or is out of scope. It occurs when the JavaScript engine cannot find a reference to the identifier you're trying to use.

   Example:
   ```javascript
   console.log(myVariable); // ReferenceError: myVariable is not defined
   ```

2. TypeError:
   A TypeError occurs when a value is not of the expected type and you perform an operation or access a property or method that is not supported for that type. It often happens when attempting to call functions on undefined or null values.

   Example:
   ```javascript
   var greeting = "Hello";
   greeting(); // TypeError: greeting is not a function
   ```

3. SyntaxError:
   A SyntaxError is raised when the JavaScript engine encounters code that violates the language's syntax rules. It usually occurs due to a mistake in the code structure, such as missing brackets, semicolons, or invalid variable names.

   Example:
   ```javascript
   if (x === 5 { // SyntaxError: missing closing parenthesis ')'
     // code block
   }
   ```

These errors are valuable as they provide information about what went wrong in your code, helping you identify and fix the issues. It's important to understand the differences between these error types to effectively debug your JavaScript programs.

### BLOCK SCOPE & Shadowing in JS
- block
	- it is defined by `{}` 
	- it is also known as compound statement 
	- used to combine multiple JS statement into one group
	- need to group these statement through so that we can pass multiple statement into place where JS expect a single statement 
		- for example in `if(true)` JS expect a single statement , but we use `{}` to create a block and give multiple statement
	- ![[Pasted image 20230623102025.png]]
	- you can see let and const are block scope where as var is in global
### Shadowing (not work with let and const)
In JavaScript, shadowing refers to a situation where a variable declared in a nested scope has the same name as a variable declared in an outer scope. This leads to the nested variable "shadowing" or overriding the outer variable within its scope, effectively hiding the outer variable from that particular scope.

When a variable is shadowed, any references to that variable within the inner scope will resolve to the inner variable, not the outer variable. The outer variable remains unaffected and retains its value in its own scope.

Here's an example to illustrate variable shadowing:

```javascript
var x = 10;

function myFunction() {
  var x = 20;  // Inner variable shadows the outer variable
  console.log(x);  // Output: 20
}

myFunction();
console.log(x);  // Output: 10 (outer variable is not affected)
```

In this example, the variable `x` is declared in both the outer and inner scopes. Within the `myFunction` function, the inner variable `x` shadows the outer variable `x`, causing any references to `x` inside the function to resolve to the inner variable. As a result, the `console.log` statement within the function outputs `20`. Outside the function, the outer variable `x` retains its original value of `10`.

Variable shadowing can sometimes lead to confusion and bugs if not handled carefully. It's important to be aware of the scoping rules and consider the potential effects of shadowing when naming variables within nested scopes.

### Lexical block scope
In JavaScript, lexical block scope, also known as block-level scope, refers to the scope that is defined by a block of code, typically delimited by curly braces `{}`. This scope determines the visibility and lifetime of variables and functions declared within the block.

Before the introduction of ES6 (ECMAScript 2015), JavaScript only had function-level scope, meaning variables declared within a function were accessible within the entire function. However, with the introduction of `let` and `const` declarations, JavaScript gained lexical block scope.

Variables declared with `let` and `const` are block-scoped, meaning they are only accessible within the block in which they are defined, including any nested blocks. This ensures that variables declared within a block do not "leak" outside of that block, reducing potential naming conflicts and improving code clarity.

Here's an example to illustrate lexical block scope:

```javascript
function myFunction() {
  if (true) {
    let x = 10;  // Block-scoped variable
    const y = 20;  // Block-scoped constant

    console.log(x);  // Output: 10
    console.log(y);  // Output: 20
  }

  console.log(x);  // Throws ReferenceError: x is not defined
  console.log(y);  // Throws ReferenceError: y is not defined
}
```

In this example, the variables `x` and `y` are block-scoped within the `if` block. They are accessible within that block, including any nested blocks, such as the inner `console.log` statements. However, outside of the block, attempting to access `x` or `y` results in a `ReferenceError` because they are not defined in the outer scope.

Lexical block scope allows for better encapsulation and helps prevent unintended variable access and modification. It's important to understand and leverage lexical block scope when writing JavaScript code to ensure proper scoping and avoid potential issues.

## Closures
- function bind together with its lexical scope forms closures 
- very important https://www.youtube.com/watch?v=qikxEIxsXco&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=12&ab_channel=AkshaySaini

## Strict mode 
Strict mode is a feature in JavaScript introduced in ECMAScript 5 (ES5) that enforces stricter parsing and error handling, promoting safer and more reliable code. When strict mode is enabled, the JavaScript interpreter applies a stricter set of rules for language features and behaviors, which helps prevent common coding mistakes and enforces better coding practices. Here's an elaboration of the key aspects of strict mode:

1. Enabling Strict Mode:
   - Strict mode can be enabled for an entire script or a specific function.
   - To enable strict mode for an entire script, add the directive `"use strict";` at the beginning of the script.
   - To enable strict mode for a specific function, add the directive at the beginning of the function.

2. Changes Introduced by Strict Mode:
   - Strict mode disallows the use of undeclared variables. Assignments to undeclared variables or using variables that have not been explicitly declared will result in a `ReferenceError`.
   - Deleting variables, functions, or function arguments is not allowed in strict mode.
   - Duplicating parameter names in function declarations is not allowed.
   - Assignments that would silently fail or have unintended side effects, such as assigning a value to `NaN`, `Infinity`, or read-only properties, will throw an error in strict mode.
   - The `this` value inside functions depends on how the function is invoked. In strict mode, when a function is invoked without a specified context (`this` is `undefined` or `null`), it remains `undefined` rather than defaulting to the global object (`window` in browsers).

3. Error Handling:
   - In strict mode, certain types of common errors that would typically fail silently are converted into throwing errors. This behavior helps identify and fix issues early during development.
   - Examples include attempting to modify read-only properties or variables, or assigning values to undeclared variables.

4. Benefits of Strict Mode:
   - Helps catch common programming mistakes and errors, enhancing code reliability.
   - Promotes better coding practices by enforcing stricter rules and avoiding "silent" errors.
   - Makes JavaScript code more predictable and reduces the risk of unintentional bugs.
   - Prepares code for modern JavaScript features and ensures compatibility with future language versions.

To summarize, strict mode in JavaScript is a programming feature that enforces stricter rules and better error handling. It helps catch potential issues, promotes reliable code, and encourages best practices. Enabling strict mode by adding the `"use strict";` directive at the beginning of a script or function is highly recommended in modern JavaScript development.