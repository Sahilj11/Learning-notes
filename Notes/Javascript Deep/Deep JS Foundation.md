## Types
- Everything in JS is not an object , they behave as obj but not an obj
- There are primitive datatype in JS 
	- Undefined
	- string
	- number 
	- boolean 
	- object
	- bigint
	- symbols
- Array and function are subtype of object type
- What is a type:- set of intrinsic charactersitics that we will be able to do with that value
- When we are using `typeof` we are looking what is the type of value that is in a variable not what is type of variable
- undefined does not implies it does not have a value yet , but it means it does not currently have a value. 

### Null giving Object as type 
The reason `typeof null` returns `"object"` in JavaScript is **due to a historical bug in the language that was never fixed for backward compatibility**.

**How `typeof` Works Internally**
- JavaScript stores values using **binary representations**.
- In early implementations, JavaScript used a **tagged representation** where the **lower bits of a value** indicated its type.
- Objects had a **type tag of `000`**, and `null` was mistakenly given the same **binary representation** as objects.

### BigInt
![](../statics/Pasted%20image%2020250226120640.png)
### Undefined vs Undeclared
- Undeclared: - it means it has never been created in any scope we have access to
- Undefined:- There is a variable that currently does not have a value.
- Typeof opertaor is only where it does not throw error if it reference which does not exist


### NaN & isNaN
- NaN does not essentialy means not a number but invalid number
- ![](../statics/Pasted%20image%2020250226121210.png)
- at line 4 it is returning NaN because for - we need number so it tries to turn it into a number and it fails so return NaN
- at line 6 it is false because NaN is not equal to each other
- at line 10 it return true because isNaN first tries to turn value to number and it return NaN so true
- `Number.isNaN` does not do that

### Negative Zero
- ![](../statics/Pasted%20image%2020250226121725.png)
- ![](../statics/Pasted%20image%2020250226121956.png)

### Fundamental Object

**Fundamental objects** are the core built-in objects in JavaScript from which most other objects derive. These include basic object constructors, prototypes, and utility objects.

#### **1️⃣ Core Fundamental Objects**

These are the foundation of JavaScript objects:

#### **1. `Object`**

- The base object from which all other objects inherit.
- Provides methods like `toString()`, `hasOwnProperty()`, and `valueOf()`.

```js
const obj = {};
console.log(obj.toString()); // "[object Object]"
```

#### **2. `Function`**

- Every function in JavaScript is an instance of `Function`.
- Functions are callable objects.

```js
function greet() { return "Hello"; }
console.log(greet instanceof Function); // true
```

#### **3. `Boolean`**

- Wraps a boolean value (`true` or `false`).

```js
const boolObj = new Boolean(false);
console.log(boolObj.valueOf()); // false
```

#### **4. `Symbol`**

- Represents unique, immutable values used as object property keys.

```js
const sym = Symbol("id");
console.log(typeof sym); // "symbol"
```

#### **5. `BigInt`**

- Represents arbitrarily large integers.

```js
const bigNum = 123456789012345678901234567890n;
console.log(typeof bigNum); // "bigint"
```

---

#### **2️⃣ Fundamental Objects for Data Handling**

These are used for working with numbers, strings, and dates.

#### **6. `Number`**

- Represents numerical values.

```js
const num = new Number(42);
console.log(num.valueOf()); // 42
```

#### **7. `String`**

- Wraps text as an object.

```js
const str = new String("Hello");
console.log(str.length); // 5
```

#### **8. `Date`**

- Represents dates and times.

```js
const now = new Date();
console.log(now.toISOString()); // "2025-02-27T14:30:00.000Z"
```

---

#### **3️⃣ Fundamental Utility Objects**

These provide utility functions and metadata.

#### **9. `RegExp`**

- Represents regular expressions.

```js
const regex = /hello/i;
console.log(regex.test("Hello")); // true
```

##### **10.`Error` and its Subtypes**

- Represents errors.
- Subtypes include `TypeError`, `SyntaxError`, etc.

```js
try {
  throw new TypeError("Invalid type");
} catch (error) {
  console.log(error.message); // "Invalid type"
}
```

---

### **Summary**

| Object     | Description                |
| ---------- | -------------------------- |
| `Object`   | Base object for all others |
| `Function` | Base object for functions  |
| `Boolean`  | Represents true/false      |
| `Symbol`   | Unique property keys       |
| `BigInt`   | Large integer numbers      |
| `Number`   | Numerical values           |
| `String`   | Text values                |
| `Date`     | Date and time              |
| `RegExp`   | Regular expressions        |
| `Error`    | Error handling             |

These **fundamental objects** form the building blocks of JavaScript.

## Coercion
### Abstract operation
Abstract operations are **internal helper functions** used in the ECMAScript specification. They are not actual JavaScript functions you can call in code, but rather conceptual operations used to define how JavaScript behaves.

#### Example: `ToNumber`

One of the most common abstract operations in JavaScript is `ToNumber`, which defines how different types are converted to numbers.

#### **`ToPrimitive` Abstract Operation in JavaScript**

`ToPrimitive` is an internal ECMAScript operation that **converts an object to a primitive value** (string, number, or symbol) by calling its `valueOf` or `toString` methods.

**How `ToPrimitive` Works**

1. If the object is already a primitive (`string`, `number`, `boolean`, `symbol`, `bigint`, or `null/undefined`), return it.
2. Otherwise:
    - If the **hint** is `"number"`, try `valueOf()` first, then `toString()`.
    - If the **hint** is `"string"`, try `toString()` first, then `valueOf()`.
    - If the **hint** is `"default"`, engines decide based on the operation.

#### `ToString`
![](../statics/Pasted%20image%2020250227074151.png)
![](../statics/Pasted%20image%2020250227074303.png)

![](../statics/Pasted%20image%2020250227074226.png)
![](../statics/Pasted%20image%2020250227074336.png)
#### `ToNumber` Abstract Operation
![](../statics/Pasted%20image%2020250227074502.png)
![](../statics/Pasted%20image%2020250227074547.png)
![](../statics/Pasted%20image%2020250227074938.png)
- Reason why null and undefined become zero is because it first become empty string and then become zero

#### `ToBoolean` Abstract Operation
![](../statics/Pasted%20image%2020250227075244.png)

### Cases of coercion 
- Using + before a variable invoke number coercion

### Boxing

**Boxing** is the process of converting a **primitive value** (like `number`, `string`, or `boolean`) into a **corresponding object wrapper** (`Number`, `String`, `Boolean`).

JavaScript does this **automatically** when calling object methods on primitives.

**Example: Automatic Boxing**

```js
const str = "hello";
console.log(str.toUpperCase()); // "HELLO"
```

 **What Happens Internally?**

1. The primitive `"hello"` is **temporarily wrapped** in a `String` object.
2. The method `toUpperCase()` is called on the temporary object.
3. The temporary object is **discarded**, and the result `"HELLO"` is returned.

 **Manual Boxing**

You can also explicitly box a primitive using object constructors:

```js
const num = new Number(42);
const bool = new Boolean(true);
const strObj = new String("hello");

console.log(typeof num);  // "object"
console.log(typeof bool); // "object"
console.log(typeof strObj); // "object"
```

---

**Unboxing (Unwrapping)**

Unboxing is the reverse process—converting an object wrapper back into a primitive using `.valueOf()`.

```js
const numObj = new Number(42);
console.log(numObj.valueOf()); // 42
console.log(typeof numObj.valueOf()); // "number"
```

**Why Avoid Explicit Boxing?**

- **Performance:** Objects are heavier than primitives.
- **Unexpected behavior:**
```js
const a = new Boolean(false);
if (a) console.log("Runs!"); // Runs! (object is truthy)
```
Even though `a` wraps `false`, the object itself is truthy.

### Corner cases of coercion
![](../statics/Pasted%20image%2020250227080539.png)
![](../statics/Pasted%20image%2020250227080907.png)

## Equality 
### Double and Triple equal
![](../statics/Pasted%20image%2020250227083928.png)
- Double and tripe equal perform essentially same if both value type are similar 
### Coercive equality

![](../statics/Pasted%20image%2020250227090036.png)

### Double equal algo
![](../statics/Pasted%20image%2020250227090515.png)
![](../statics/Pasted%20image%2020250227091012.png)
![](../statics/Pasted%20image%2020250227091510.png)

### Double equal corner cases
![](../statics/Pasted%20image%2020250227092010.png)
![](../statics/Pasted%20image%2020250227092021.png)
![](../statics/Pasted%20image%2020250227092156.png)
![](../statics/Pasted%20image%2020250227092442.png)

## Scope
- JS is not a interpreted language in true sense , but more like compiled or parsed.
- Some processing step happen before execution occur. for example if there is syntax error on line 10 and before executing line 1 - 9 it shows that error
- JS has a two pass system
- Units of scope are functions and blocks

### Compilation and scope
![](../statics/Pasted%20image%2020250228084514.png)
- In compilation phase we have scope manager and compiler
- Having two variable in different scope with same name is called shadowing
- In a lexically scoped language like JS all identifier and lexical scope are determined at compile time. 
- Variable declaration are identified not initalised (for let and const ) but it is initialized to undefined for (var)
- The **Temporal Dead Zone (TDZ)** is the time between when a variable is parsed() and when it is **initialized**(during runtime). During this period, trying to access the variable causes a **ReferenceError**.
![](../statics/Pasted%20image%2020250228085718.png)
- Above is happening at compile time, even on line 10 reference is also resolved at compile time
- Scope plan is created here

#### What gets initialized during parsing?
Function declarations are fully hoisted and initialized during parsing, meaning they can be used before their definition.

```js
greet(); // ✅ Works! Output: "Hello"

function greet() {
    console.log("Hello");
}
```

Variables declared with `var` are hoisted but initialized with `undefined`. Accessing them before assignment returns `undefined`.

```js
console.log(a); // ✅ undefined
var a = 10;
console.log(a); // ✅ 10
```

Variables declared with `let` and `const` are hoisted but not initialized. Accessing them before declaration results in a `ReferenceError` due to the Temporal Dead Zone (TDZ).

```js
console.log(b); // ❌ ReferenceError
let b = 20;
console.log(b); // ✅ 20
```

Class declarations are also hoisted but not initialized. Trying to use a class before its declaration results in a `ReferenceError`.

```js
const obj = new MyClass(); // ❌ ReferenceError

class MyClass {
    constructor() {
        console.log("Class Initialized");
    }
}
```

Function parameters are initialized when the function is called. Default parameters are also initialized at this point.

```js
function greet(name = "User") {
    console.log(name);
}

greet("Alice"); // ✅ Alice
greet();        // ✅ User
```

`this` is initialized based on execution context. In the global scope, it refers to `window` in browsers and `global` in Node.js. Inside functions, in strict mode, `this` is `undefined`.

```js
"use strict";

function showThis() {
    console.log(this);
}

showThis(); // ✅ undefined (strict mode)
```

ES6 `import` statements are hoisted and initialized before script execution begins.

```js
import { myFunc } from './module.js';
myFunc(); // ✅ Works
```

Function declarations are fully initialized and can be called before definition. `var` variables are hoisted with `undefined`, while `let`, `const`, and classes remain in the Temporal Dead Zone. Function parameters are initialized at call time. `this` depends on the execution context, and imports are processed before execution starts.
### Code execution
- Target reference means it is receiving an value or assignment
- else it is a source reference

### Dynamic global variables
![](../statics/Pasted%20image%2020250228092033.png)
- here on line 5 , there is no topic and engine ask the scope if it there there first in function scope , then go to global scope , but because of bad parts of js , JS create a global variable automatically , as the assignment is done here

### Strict Mode
![](../statics/Pasted%20image%2020250228092606.png)

### Nested Scope
- ![](../statics/Pasted%20image%2020250228093224.png)
- if you are in non strict mode at line 14 it is a source reference , so no auto global created and it gives reference error

### Lexical Scope

**Lexical scope** means that **a function can access variables from the place where it was defined, not where it is called**.

📌 **Think of it like a function "remembering" where it was written in the code.**

**How It Works?**
🔹 **Inner functions can access variables from outer functions.**  
🔹 **JavaScript looks for variables in the nearest scope first, then moves outward (Scope Chain).**
**Example 1: Simple Lexical Scope**
```js
function outer() {
    let message = "Hello from outer!";

    function inner() {
        console.log(message); // Can access `message` from `outer`
    }

    inner(); 
}

outer(); // Output: Hello from outer!

```

## Scope and function expression
### Function Expression
![](../statics/Pasted%20image%2020250228093948.png)
- Line 1 is a function declaration where as line 3 is function expression
- function declaration attach there marble to enclosing scope which in above case is global scope, The function is only available after the expression is executed.

```js
greet(); // ReferenceError: greet is not defined
const greet = function () {
    console.log("Hello");
};

```

- function expression add there marble to their own scope
![](../statics/Pasted%20image%2020250228094202.png)
![](../statics/Pasted%20image%2020250228094446.png)
- first is anonymous function expression where as second one is named function expression

### Named function expression
- Always prefer named function expression instead of anonymous function expression
- Reason
	- ![](../statics/Pasted%20image%2020250228094959.png)

## Lexical Scope
- Ideas of scope been nested within each other, and a idea that a parser ,compiler , is figuring out all those scope ahead of time
- It is decided at compile time not run time, bash script is dynamic scoped(scope depends on where that function is called)

### Function Scoping
![](../statics/Pasted%20image%2020250313080106.png)

### IIFE(Immediately Invoked Function Expression) Pattern
![](../statics/Pasted%20image%2020250313080621.png)
![](../statics/Pasted%20image%2020250313080631.png)
![](../statics/Pasted%20image%2020250313081238.png)

In JavaScript, `try...catch` is a **statement**, not an **expression**. This means:

 ❌ **You cannot use `try...catch` inside an expression.**

For example, this will throw a syntax error:

```js
const result = try { JSON.parse("invalid"); } catch (e) { "fallback"; }; 
// ❌ SyntaxError: Unexpected token 'try'
```

Because `try...catch` does not return a value like expressions do.

✅ **You must use it as a separate statement.**

```js
let result;
try {
    result = JSON.parse("invalid"); // Throws error
} catch (e) {
    result = "fallback"; // Assign fallback value
}
console.log(result); // "fallback"
```

 ✅ **Alternative: Use an IIFE (Immediately Invoked Function Expression)**

If you need `try...catch` inside an expression, wrap it in an IIFE:

```js
const result = (() => {
    try {
        return JSON.parse("invalid");
    } catch (e) {
        return "fallback";
    }
})();
console.log(result); // "fallback"
```

✅ **Using `?.` (Optional Chaining) for safer expressions**

For cases where an error might occur due to `undefined` or `null`, you can use **optional chaining (`?.`)** instead of `try...catch`:

```js
const obj = null;
console.log(obj?.property ?? "fallback"); // "fallback"
```

**Conclusion**

- `try...catch` **must be a separate statement**.
- It **cannot be directly used inside expressions**.
- Use an **IIFE** if you need it inside an expression.


### Block Scoping

![](../statics/Pasted%20image%2020250313082756.png)

![](../statics/Pasted%20image%2020250313082710.png)
- Blocks are statements and cannot be use at place of expression
- In strict mode, function declarations inside blocks are scoped to that block and are hoisted.

### Var vs Let
The difference between `var` and `let` in JavaScript mainly comes down to **scoping, hoisting, and re-declaration**.

**1. Scope**

- **`var` is function-scoped** → It is available throughout the function where it is declared.
- **`let` is block-scoped** → It is only available inside the `{}` block where it is defined.

 Example:

```js
function test() {
    if (true) {
        var x = 10;
        let y = 20;
    }
    console.log(x); // ✅ 10 (var is function-scoped)
    console.log(y); // ❌ ReferenceError (let is block-scoped)
}
test();
```

 **2. Hoisting**

- **`var` is hoisted but initialized as `undefined`** → You can reference it before declaration.Even though **`var` is hoisted**, hoisting only applies **within the function scope** in which the variable is declared. It does **not** hoist a function-scoped variable to the global scope.
- **`let` is hoisted but not initialized** → Accessing before declaration gives a **ReferenceError**.

Example:

```js
console.log(a); // ✅ undefined (var is hoisted)
var a = 10;

console.log(b); // ❌ ReferenceError (let is hoisted but not initialized)
let b = 20;
```

**3. Re-declaration**

- **`var` allows re-declaration** within the same scope.
- **`let` does not allow re-declaration** within the same scope.

 Example:

```js
var x = 10;
var x = 20; // ✅ No error

let y = 30;
let y = 40; // ❌ SyntaxError: Identifier 'y' has already been declared
```

**4. Attached to `window` Object (Global Scope)**

- **`var` creates a property on `window` if declared globally.**
- **`let` does not attach to `window`.**

Example:

```js
var globalVar = "Hello";
let globalLet = "World";

console.log(window.globalVar); // ✅ "Hello"
console.log(window.globalLet); // ❌ undefined
```

**Summary Table**

|Feature|`var`|`let`|
|---|---|---|
|**Scope**|Function-scoped|Block-scoped|
|**Hoisting**|Hoisted, initialized as `undefined`|Hoisted but not initialized (Temporal Dead Zone)|
|**Re-declaration**|Allowed|Not allowed in the same scope|
|**Attached to `window`**|Yes (if declared globally)|No|

**Which one to use?**

- Use **`let`** for block-scoping and avoiding accidental re-declarations.
- Use **`var`** only if you need function-scoping (rare cases).


### Explicit let scoping
![](../statics/Pasted%20image%2020250313085018.png)

### Const 
![](../statics/Pasted%20image%2020250313085627.png)
- Const means variable cannot be reassigned 

### Hoisting
**Hoisting** is a JavaScript behavior where **variable and function declarations** are **moved (hoisted) to the top** of their scope **before execution**. This means you can use functions and variables **before they are declared** in the code.

But this is just a methaphor to what is happening behind the scene during compile time , where scopes are been assigned to variables

![](../statics/Pasted%20image%2020250313091533.png)
ans is undefined

### Let Doesn't hoist? 
![](../statics/Pasted%20image%2020250313092643.png)
let also hoist just it does not get initialized
Temporal Dead Zone

## Closure
- ![](../statics/Pasted%20image%2020250313093935.png)
- ![](../statics/Pasted%20image%2020250313094054.png)

```js
function outer() {
    let count = 0; // Lexical scope

    return function inner() {
        count++; // Remembering `count` from outer scope
        console.log(count);
    };
}

const increment = outer(); // `outer` executes and returns `inner`
increment(); // ✅ 1
increment(); // ✅ 2
increment(); // ✅ 3
```

Even though `outer()` has finished execution, `inner()` still **remembers** the `count` variable from `outer()` due to **closure**. This happens because JavaScript does not garbage collect variables if they are still referenced by an inner function.

Closures are useful for **data encapsulation, private variables, and function factories**.

#### **Lexical Scope vs. Closure**

**Lexical Scope** and **Closure** are related but different concepts.

**Lexical Scope**

Lexical scope means that **a function can access variables from its outer scope based on where it is written in the code**. It does **not** require returning a function or keeping a reference to an outer variable.

```js
function outer() {
    let x = 10;  // Lexical scope

    function inner() {
        console.log(x); // ✅ Can access `x` from outer function
    }

    inner(); // `inner` is called inside `outer`
}

outer(); // ✅ 10
```

Here, `inner()` can access `x` because of **lexical scoping**, but once `outer()` finishes, everything inside it is gone.

**Closure**

A **closure** happens when a function **remembers its lexical scope even after the outer function has finished execution**. This occurs when an inner function is returned or stored outside its defining scope.

```js
function outer() {
    let x = 10;  // Lexical scope

    return function inner() {
        console.log(x); // ✅ Remembers `x` even after `outer()` is done
    };
}

const fn = outer(); // `outer()` runs and returns `inner`, but does NOT call it
fn(); // ✅ 10 (closure keeps `x` alive)
fn(); // ✅ 10
```

Here, `outer()` finishes execution, but since `inner()` is returned and stored in `fn`, it **remembers `x`**, forming a **closure**.

 **Key Differences**

| Feature                                         | Lexical Scope                               | Closure                                          |
| ----------------------------------------------- | ------------------------------------------- | ------------------------------------------------ |
| When does it exist?                             | Always (in any nested function)             | Only when an inner function is returned/stored   |
| Can access outer variables?                     | ✅ Yes                                       | ✅ Yes                                            |
| Keeps variables after outer function execution? | ❌ No                                        | ✅ Yes                                            |
| Example                                         | Calling an inner function inside its parent | Returning an inner function and calling it later |

Lexical scope **always exists**, but **closure only happens when an inner function escapes its scope and keeps access to outer variables**.

a **closure** is technically **per variable**, meaning each variable that is captured in the closure is remembered separately. However, **closures operate at the scope level**, meaning that if an inner function closes over a scope containing a large object, that object will **not be garbage collected** as long as the closure is still referenced.

 **Example: Closure Holding Big Data**

```js
function createClosure() {
    let bigData = new Array(1000000).fill("🚀"); // 1 million elements

    return function inner() {
        console.log(bigData[0]); // 🚀 (closure retains `bigData`)
    };
}

const fn = createClosure(); // Closure created
// `bigData` is NOT garbage collected because `fn` holds a reference
fn(); // ✅ Logs "🚀"

// `fn` still exists, so `bigData` is still in memory
```

Here, even though `createClosure()` has finished executing, the `bigData` array is **not garbage collected** because the inner function **still references it**.

 **Freeing Memory Manually**

If you **set the closure reference to `null`**, the garbage collector can free the memory.

```js
fn = null; // `bigData` is now eligible for garbage collection
```

Now, since no active reference exists to `inner()`, the closure **no longer holds `bigData` in memory**, allowing garbage collection.

 **Key Takeaways**

1. **Closures retain all variables they reference, even large objects.**
2. **If a closure references a big object, that object will not be garbage collected until the closure itself is removed.**
3. **Manually setting the closure reference to `null` can free up memory.**

This is why **unnecessary closures** holding large data structures can lead to **memory leaks** if not managed properly.

### Closing Over Variable
- There is no such thing as closing over value , you close over variable
- ![](../statics/Pasted%20image%2020250313095425.png)
- here it print suzy , because we close on variable not on value
![](../statics/Pasted%20image%2020250313095540.png)
![](../statics/Pasted%20image%2020250313095707.png)
we are declaring 3 j's so each time closure on different variable
![](../statics/Pasted%20image%2020250313095808.png)
if using let in loop , creates new i for each iteration


### Module Pattern
#### Namespace pattern
![](../statics/Pasted%20image%2020250313125756.png)
The **Namespace Pattern** in JavaScript is a way to organize code into a structured, modular format by grouping related functions, variables, and objects under a single global object. This helps prevent global namespace pollution and avoids naming conflicts.

This is not a module because properties and variables are public.

#### Module
![](../statics/Pasted%20image%2020250313130541.png)
![](../statics/Pasted%20image%2020250313130557.png)
purpose of module is to track state over time, 
The **Module Pattern** in JavaScript is a design pattern that allows you to create encapsulated, reusable, and self-contained pieces of code with private and public members. It is an improvement over the **Namespace Pattern** as it allows private variables and methods, which cannot be accessed directly from outside the module.
![](../statics/Pasted%20image%2020250313131004.png)

### ES6 Modules

**modules in JavaScript (using the Module Pattern or ES6 Modules) are singletons** by design. This means that when a module is imported or executed, it is **initialized only once**, and any subsequent imports or calls refer to the same instance.

![](../statics/Pasted%20image%2020250313131756.png)
![](../statics/Pasted%20image%2020250313131910.png)

## Objects 

### This
![](../statics/Pasted%20image%2020250313154314.png)
![](../statics/Pasted%20image%2020250313154403.png)
![](../statics/Pasted%20image%2020250313154507.png)
![](../statics/Pasted%20image%2020250313154534.png)

```js
function ask(question) {
    console.log(this.teacher, question);
}
function otherClass() {
    var myContext = {
        teacher: "Suzy"
    };
    ask.call(myContext, "Why?");
}
otherClass(); // Suzy, Why?
```
The `call` method lets you run a function and manually set what `this` should be inside that function.

**Example:**

```js
function sayHello() {
    console.log("Hello, " + this.name);
}

const person = { name: "Alice" };

sayHello.call(person); // Output: Hello, Alice
```

🔹 Normally, `this` inside `sayHello` would be `undefined` (or `window` in browsers).  
🔹 But with `.call(person)`, we tell JavaScript: "Run `sayHello`, but pretend `this` is `person`."

 **Another Example (With Arguments):**

```js
function introduce(greeting, punctuation) {
    console.log(greeting + ", " + this.name + punctuation);
}

const user = { name: "Bob" };

introduce.call(user, "Hi", "!"); // Output: Hi, Bob!
```

Here, `"Hi"` and `"!"` are passed as extra arguments to the function.

👉 **Think of `call` as a way to "borrow" a function and use it with a different object.**

### Different ways to call a function
#### Implicit and explicit binding
**Implicit Binding in JavaScript (`this`)**

**Implicit binding** is a rule that determines what `this` refers to inside a function **when the function is called through an object**.

 **Rule:**

📌 When a function is called using **dot notation (`obj.method()`)**, `this` inside the function refers to the object **before the dot**.

---

**Example of Implicit Binding**

```js
const person = {
    name: "Alice",
    greet: function () {
        console.log("Hello, " + this.name);
    }
};

person.greet(); // Output: Hello, Alice
```

👉 **Why?**

- The function `greet` is called on `person`, so `this` inside `greet` refers to `person`.

---

**Example with Nested Objects**

```js
const user = {
    name: "Bob",
    details: {
        age: 25,
        showAge: function () {
            console.log(this.age);
        }
    }
};

user.details.showAge(); // Output: 25
```

👉 **Why?**

- `showAge` is called using `user.details.showAge()`, so `this` refers to `user.details`.

---

**Breaking Implicit Binding**

If the function is assigned to a variable or passed as a callback, **implicit binding is lost**, and `this` becomes `undefined` (or `window` in non-strict mode).

```js
const person = {
    name: "Charlie",
    speak: function () {
        console.log("I am " + this.name);
    }
};

const talk = person.speak; // Function reference assigned
talk(); // Output: I am undefined (or "I am " in browsers)
```

👉 **Why?**

- `talk` is called **without an object**, so `this` defaults to `undefined` in strict mode (or `window` otherwise).

---

**Fixing Implicit Binding Loss**

1. **Use `.bind()`**

```js
const boundTalk = person.speak.bind(person);
boundTalk(); // Output: I am Charlie
```

2. **Use an arrow function** (for certain cases)

```js
const person2 = {
    name: "Diana",
    speak: () => console.log("I am " + this.name)
};

person2.speak(); // Output: I am undefined (arrow functions don't have their own `this`)
```

**Key Takeaway:** **Implicit binding works only when a function is directly called on an object (`obj.method()`). If assigned or passed around, `this` is lost.**
![](../statics/Pasted%20image%2020250313155808.png)
#### Explicit  binding
**Explicit Binding in JavaScript (`this`)**

**Explicit binding** means **manually setting** what `this` should refer to when calling a function. This is done using `.call()`, `.apply()`, or `.bind()`.

 **1️⃣ Using `.call()`**

📌 `.call(thisArg, arg1, arg2, ...)`  
Calls the function immediately, setting `this` to `thisArg`.

```js
function greet(greeting) {
    console.log(greeting + ", " + this.name);
}

const person = { name: "Alice" };

greet.call(person, "Hello"); // Output: Hello, Alice
```

👉 **Why?**

- `call(person, "Hello")` forces `this` to be `person`.

 **2️⃣ Using `.apply()`**

📌 `.apply(thisArg, [argsArray])`  
Like `call()`, but takes arguments as an array.

```js
greet.apply(person, ["Hi"]); // Output: Hi, Alice
```

👉 **Why use `apply`?**

- Useful when arguments are in an array.

 **3️⃣ Using `.bind()`**

📌 `.bind(thisArg, arg1, arg2, ...)`  
Returns a **new function** with `this` permanently set.

```js
const boundGreet = greet.bind(person, "Hey");
boundGreet(); // Output: Hey, Alice
```

👉 **Why?**

- Unlike `call()` and `apply()`, `bind()` **does not call the function immediately**. It returns a new function that you can call later.

**Example: Fixing `this` inside Callbacks**

When passing a function to an event handler or another function, `this` might get lost. **Use `.bind()` to fix it!**

```js
const user = {
    name: "Charlie",
    sayHello: function() {
        console.log("Hello, " + this.name);
    }
};

setTimeout(user.sayHello, 1000);  // Output: Hello, undefined

setTimeout(user.sayHello.bind(user), 1000); // Output: Hello, Charlie
```

👉 **Why?**

- `setTimeout(user.sayHello)` loses `this`.
- `bind(user)` ensures `this` always refers to `user`.

In JavaScript, when you pass a method like `workshop1.ask` directly to `setTimeout`, it loses its original object (`workshop1`) because **functions in JavaScript are first-class objects** and can be detached from their owners.

 Why Does `this` Get Lost?

1. **Function Reference Extraction:**
    
    ```js
    setTimeout(workshop1.ask, 10, "Can I ask a question?");
    ```
    
    Here, `workshop1.ask` is passed **as a reference** to `setTimeout`. This means `setTimeout` calls it as a **standalone function** rather than a method of `workshop1`.
    
2. **How `setTimeout` Calls the Function:**  
    Internally, `setTimeout` calls `workshop1.ask` like this:
    
    ```js
    function execute() {
        workshop1.ask("Can I ask a question?");
    }
    execute(); // "ask" runs as a normal function, not as `workshop1.ask`
    ```
    
    Since it's a standalone function call, `this` inside `ask` does **not** refer to `workshop1`, but instead:
    
    - In **strict mode** (`"use strict"`), `this` is `undefined`.
    - In **non-strict mode**, `this` defaults to the global object (`window` in browsers, `global` in Node.js).

How to Fix This?

Since JavaScript does **not automatically bind `this`**, you need to explicitly bind it:

1. **Use `.bind()`**

```js
setTimeout(workshop1.ask.bind(workshop1), 10, "Can I ask a question?");
```

- `.bind(workshop1)` creates a **new function** where `this` is permanently set to `workshop1`.

2. **Use an Arrow Function**

```js
setTimeout(() => workshop1.ask("Can I ask a question?"), 10);
```

- Arrow functions don’t have their own `this`; they inherit `this` from their surrounding scope, preserving the context.

3. **Store `this` in a Variable**

```js
var self = workshop1;
setTimeout(function() {
    self.ask("Can I ask a question?");
}, 10);
```

- This is an older trick used before `.bind()` and arrow functions became popular.

Summary
- When you pass `workshop1.ask` to `setTimeout`, it becomes a detached function.
- Since it’s called as a normal function, `this` does not point to `workshop1`.
- Use `.bind()`, an arrow function, or store `this` in a variable to maintain context.

**🔹 Key Takeaways**

| Method     | Calls Function Immediately? | Accepts Arguments Individually? | Accepts Arguments as an Array? | Returns a New Function? |
| ---------- | --------------------------- | ------------------------------- | ------------------------------ | ----------------------- |
| `.call()`  | ✅ Yes                       | ✅ Yes                           | ❌ No                           | ❌ No                    |
| `.apply()` | ✅ Yes                       | ❌ No                            | ✅ Yes                          | ❌ No                    |
| `.bind()`  | ❌ No                        | ✅ Yes                           | ❌ No                           | ✅ Yes                   |

📌 **Use `call` when you know arguments beforehand.**  
📌 **Use `apply` when arguments are in an array.**  
📌 **Use `bind` when you need a function that remembers `this` for later.**


#### Hard Binding 
**Hard Binding in JavaScript (`this`)**

Hard binding is when we **permanently bind** a function to a specific `this` value so that it **cannot be overridden**.

This is done using `.bind()` or by manually wrapping the function in another function.

---

**1️⃣ Using `.bind()` (Most Common)**  
`.bind(thisArg)` creates a new function that **always** uses `thisArg` as `this`, no matter how it’s called.

```js
const person = {
    name: "Alice",
    sayHello: function() {
        console.log("Hello, " + this.name);
    }
};

const greet = person.sayHello.bind(person); 

greet(); // Output: Hello, Alice

setTimeout(greet, 1000); // Output: Hello, Alice (Still bound!)
```

Even if `greet` is called later or passed to another function, it **always uses `person` as `this`**.

---

**2️⃣ Using a Wrapper Function (Manual Hard Binding)**  
Another way to **manually** hard-bind `this` is by creating a wrapper function.

```js
function sayHello() {
    console.log("Hello, " + this.name);
}

const user = { name: "Bob" };

// Manually binding `this`
const hardBoundGreet = function() {
    return sayHello.call(user);
};

hardBoundGreet(); // Output: Hello, Bob

setTimeout(hardBoundGreet, 1000); // Output: Hello, Bob
```

The wrapper function **always calls `sayHello` with `user` as `this`**, so it can’t be changed.

---

**3️⃣ Hard Binding with Constructor Functions**  
Hard binding ensures that `this` always refers to a specific object, even when using `new`.

```js
function Person(name) {
    this.name = name;
}

function greet() {
    console.log("Hello, " + this.name);
}

const alice = new Person("Alice");

// Hard binding `this` to `alice`
const boundGreet = greet.bind(alice);

boundGreet(); // Output: Hello, Alice

const bob = new Person("Bob");
boundGreet.call(bob); // Output: Hello, Alice (hard binding ignores `call`!)
```

Even when trying to override `this` with `.call()`, `boundGreet` **always** uses `alice` as `this`.

---

**🔹 Key Takeaways**

|Method|Can Override `this`?|Creates a New Function?|Persistent?|
|---|---|---|---|
|`.call()`|✅ Yes|❌ No|❌ No|
|`.apply()`|✅ Yes|❌ No|❌ No|
|`.bind()`|❌ No|✅ Yes|✅ Yes|
|Wrapper Function|❌ No|✅ Yes|✅ Yes|

Use `.bind()` when you always want a function to use the same `this`, no matter how it’s called.  
Use a wrapper function when `.bind()` is not available (like in very old JS versions).


#### new keyword (third way to call function)
![](../statics/Pasted%20image%2020250313161437.png)

#### Default Binding
![](../statics/Pasted%20image%2020250313161925.png)

### Binding precendence
![](../statics/Pasted%20image%2020250324210017.png)
### Arrow Function & Lexical scope
![](../statics/Pasted%20image%2020250324210157.png)
- In arrow function there is no this context , so it treats teacher as a variable and try to resolve it lexically
- so here this.teacher is looked in ask , and ask this context is workshop so it resolve it to Kyle
![](../statics/Pasted%20image%2020250324210707.png)
here there is only two scope , one is ask function and other is global scope


### ✅ This **works**:

```js
setTimeout(() => console.log(this.teacher), 1000);
```

### ❌ But this **does not**:

```js
ask: (question) => console.log(this.teacher, question)
```

---



### 🔹 Arrow functions:

- **Don't have their own `this`**
    
- They "capture" `this` from the **lexical (outer) scope**
    
- Commonly used in callbacks like `setTimeout`, where you want to keep the outer `this`.
    

### 🔹 Regular functions:

- Their `this` is determined by **how they are called**
    
- When used as a method (like `obj.method()`), `this` refers to the object before the dot (`obj`)
    

---


```js
function Workshop(teacher) {
  this.teacher = teacher;
}

Workshop.prototype.ask = (question) => {
  console.log(this.teacher, question);
};
```

Here’s the issue:

- `ask` is an **arrow function assigned on the prototype**
    
- So `this` is **not bound dynamically**
    
- It captures `this` from the outer scope where it was defined — **not from the object like `deepJS` or `reactJS`**
    

And in most cases, that outer `this` is either:

- The **global object** (`window` in browser / `undefined` in strict mode), or
    
- Whatever `this` was in the script during the `Workshop.prototype.ask = ...` line
    

So:

```js
deepJS.ask("Hello"); // this.teacher is undefined ❌
```

---

#### ✅ But why does `setTimeout(() => ...)` work?

```js
Workshop.prototype.ask = function(question) {
  setTimeout(() => console.log(this.teacher), 1000);
};
```

- Here, `ask` is a **normal function**
    
- So when you do `deepJS.ask(...)`, `this` is correctly bound to `deepJS`
    
- Inside `setTimeout`, you're using an **arrow function**, which captures the `this` from `ask()` — i.e., `deepJS`
    

That’s why it works ✅

---

#### ✅ Fix: Use regular function for `ask`

```js
Workshop.prototype.ask = function(question) {
  console.log(this.teacher, question);
};
```

Now it works:

```js
const deepJS = new Workshop("Kyle");
deepJS.ask("Is prototype confusing?"); 
// Kyle Is prototype confusing?
```

---

#### 🔁 Summary

|Case|Works?|Why|
|---|---|---|
|`setTimeout(() => ...)` in method|✅|Arrow captures correct `this` from method|
|`ask: (question) => ...`|❌|Arrow captures `this` at assignment time, not call time|
|Regular method + arrow inside|✅|Proper `this` flow from method to callback|


## Prototype
### Intro
In JavaScript, **prototype** is a built-in mechanism that allows objects to inherit properties and methods from other objects. Every function in JavaScript automatically has a `prototype` property, which is used when creating new objects.

![](../statics/Pasted%20image%2020250324215412.png)
![](../statics/Pasted%20image%2020250513160823.png)

## 🔁 Linking to a Prototype (Inheritance by Reference)

When you use a constructor (or `Object.create()`), JavaScript **links the new object** to the prototype. This is not a copy — it’s a reference chain.

### Example:

```javascript
function Animal() {}
Animal.prototype.speak = function() {
  console.log("Generic sound");
};

const dog = new Animal();
dog.speak(); // Logs: "Generic sound"

// This comes from the prototype, not a copy
console.log(dog.speak === Animal.prototype.speak); // true
```

➡️ If you change `Animal.prototype.speak`, **all objects linked to it reflect the change**.

```javascript
Animal.prototype.speak = function() {
  console.log("Updated sound");
};

dog.speak(); // Logs: "Updated sound"
```

---

## 📋 Copying (Manual Property Copy)

Copying means taking all properties and methods from one object and physically adding them to another.

### Example:

```javascript
const animalMethods = {
  speak: function() {
    console.log("Generic sound");
  }
};

const dog = {};
Object.assign(dog, animalMethods);

dog.speak(); // Logs: "Generic sound"

// This is a copy
console.log(dog.speak === animalMethods.speak); // true (but a copy of reference)
```

➡️ Now, if you **change `animalMethods.speak`**, `dog.speak` won't change:

```javascript
animalMethods.speak = function() {
  console.log("Updated sound");
};

dog.speak(); // Still logs: "Generic sound"
```

---

## ✅ Summary: Prototype Linking vs Copying

|Feature|Prototype Linking (`new`, `Object.create`)|Copying (`Object.assign`, manual)|
|---|---|---|
|Behavior reuse|Yes (via reference to prototype)|Yes (copied once)|
|Reflects future changes|Yes (dynamic inheritance)|No (static copy)|
|Memory efficiency|More efficient (shared methods)|Less efficient (duplicate code)|
|Use case|Inheritance, shared behavior|Shallow clone, configuration|

### Prototype Chain

The **prototype chain** is the mechanism by which JavaScript objects inherit properties and methods from other objects via their `[[Prototype]]` (or `__proto__`) link.

```txt
dog
  ↓ __proto__
Animal.prototype
  ↓ __proto__
Object.prototype
  ↓ __proto__
null
```

### ✅ `Object` is a **function** in JavaScript — specifically, a **constructor function**.

You can verify it:

```javascript
console.log(typeof Object); // "function"
```

---

### 🔍 But `Object` is also an **object** in that it has its own properties and methods.

For example:

```javascript
console.log(Object.keys);         // function keys() { [native code] }
console.log(Object.prototype);    // { constructor: Object, ... }
console.log(Object.hasOwn);       // A method (as of ES2022)
```

This works because in JavaScript:

- **Functions are objects**.
    
- That means they can have properties and methods just like regular objects.
    

---

### 🔁 Quick Breakdown:

|Term|Is it a...?|Description|
|---|---|---|
|`Object`|✅ Function|Built-in constructor function for creating objects|
|`Object`|✅ Object|Has static methods like `Object.keys()`, `Object.create()`|
|`Object.prototype`|✅ Object|Prototype shared by all objects created via `Object`|
|`typeof Object`|`"function"`|Because it's a constructor|

---

### 🧠 Think of it like this:

> `Object` is a **function object**: it behaves like a function, but it is also an object with methods and a prototype.

---

### Bonus — Proof `Object` is a constructor:

```javascript
const obj = new Object();
console.log(obj); // {} — an empty object
```

### ✅ A **namespace** is a container that holds **identifiers** (like variable names, functions, classes, etc.) to avoid name **collisions** and **organize code**.

---

## 🧠 Think of a namespace as:

> "A labeled box where you group related items so they don't clash with other boxes."

---

### 📦 Why are namespaces useful?

Imagine two different libraries define a function called `init()`:

```javascript
// Without namespace
function init() { console.log("Library A Init"); }
function init() { console.log("Library B Init"); } // This overwrites the previous one!
```

### ✅ With namespaces:

```javascript
var LibraryA = {
  init: function () { console.log("Library A Init"); }
};

var LibraryB = {
  init: function () { console.log("Library B Init"); }
};

LibraryA.init(); // "Library A Init"
LibraryB.init(); // "Library B Init"
```

Now both `init()` functions coexist without conflict.

---

### 🔍 In JavaScript, there’s no built-in `namespace` keyword

But you simulate namespaces using:

1. **Objects**
    
2. **Modules (ES6+)**
    
3. **IIFEs (Immediately Invoked Function Expressions)**
    

---

### ✅ Examples

#### 1. **Namespace using an object**

```javascript
var MyApp = {};

MyApp.utils = {
  sayHello: function(name) {
    console.log("Hello, " + name);
  }
};

MyApp.utils.sayHello("John"); // "Hello, John"
```

#### 2. **Namespace using ES6 modules**

```js
// file: mathUtils.js
export function add(a, b) { return a + b; }
export function subtract(a, b) { return a - b; }

// file: main.js
import * as MathUtils from './mathUtils.js';

console.log(MathUtils.add(5, 3)); // 8
```

---

### 🧾 Summary

|Concept|What it does|Example|
|---|---|---|
|Namespace|Groups related code|`MyApp.utils.sayHello()`|
|Purpose|Avoids name conflicts|No overwriting `init()`|
|Simulated via|Objects, modules, or IIFEs|`var MyApp = {}`|

```js
console.log(typeof Object)
// function
console.log(typeof Object.prototype)
// object
console.log(typeof Object.prototype.constructor)
// function
```


### ✅ Code Breakdown

```js
function Workshop(teacher) {
  this.teacher = teacher;
}

Workshop.prototype.ask = function(question) {
  console.log(this.teacher, question);
};

var deepJS = new Workshop("Kyle");
var reactJS = new Workshop("Suzy");

deepJS.ask("Is 'prototype' a class?");
reactJS.ask("Isn't 'prototype' ugly?");
```

---

## 🧠 1. What happens when you do `new Workshop("Kyle")`?

This creates an object `deepJS` and links it to `Workshop.prototype`.

Under the hood:

```js
deepJS = {
  teacher: "Kyle",
  __proto__: Workshop.prototype
};
```

So:

```js
deepJS.ask === Workshop.prototype.ask; // true
```

This means the method is **not copied**, it’s **inherited via the prototype chain**.

---

## 🔁 2. How does the prototype chain work here?

When you do:

```js
deepJS.ask("Is 'prototype' a class?");
```

Here's what JS does behind the scenes:

1. Look for `ask` on `deepJS` itself — ❌ not found
    
2. Look at `deepJS.__proto__`, which is `Workshop.prototype` — ✅ found
    
3. Calls `Workshop.prototype.ask` with `this = deepJS`
    

So it logs:

```
Kyle Is 'prototype' a class?
```

Same logic for `reactJS`, which logs:

```
Suzy Isn't 'prototype' ugly?
```

---

## 📚 3. Now link this with:

```js
console.log(typeof Object);                  // "function"
console.log(typeof Object.prototype);        // "object"
console.log(typeof Object.prototype.constructor); // "function"
```

This shows how JavaScript treats functions and their prototypes:

- `Object` is a **function** (used to create objects).
    
- `Object.prototype` is an **object** — the base object for all others.
    
- `Object.prototype.constructor` points back to the function: `Object`.
    

In fact:

```js
Object.prototype.constructor === Object; // true
```

---

## 🧬 4. Visual of Prototype Chain for `deepJS`

```txt
deepJS
  ↓ __proto__
Workshop.prototype
  ↓ __proto__
Object.prototype
  ↓ __proto__
null
```

So:

```js
deepJS.ask            // from Workshop.prototype
deepJS.toString()     // from Object.prototype
```

---

## ✅ Summary

| Concept                  | Meaning                                           |
| ------------------------ | ------------------------------------------------- |
| `new Workshop()`         | Creates an object linked to `Workshop.prototype`  |
| `Workshop.prototype.ask` | Shared method for all instances                   |
| `deepJS.ask(...)`        | Uses prototype chain to find `ask`                |
| `Object`                 | A constructor function                            |
| `Object.prototype`       | The top-level prototype object                    |
| Prototype chain          | A lookup chain via `__proto__` or `[[Prototype]]` |

### Object and Function relation

This is one of the most **mind-bending but powerful** aspects of JavaScript:  
functions are objects, and objects are created by functions — they are deeply interconnected.

---

## 🔁 TL;DR: Circular Nature of `Object` and `Function`

- ✅ `Object` is a **function**.
    
- ✅ `Function` is a **function**.
    
- ✅ Both have a `.prototype` object.
    
- ✅ All objects ultimately link back to `Object.prototype`.
    
- ✅ All functions (including `Object` and `Function`) are created by `Function`.
    

---

## 🧠 Think of it like this:

```js
typeof Object            // "function"
typeof Function          // "function"
typeof Object.prototype  // "object"
typeof Function.prototype// "object"
```

---

## 🔍 Let's explore the **back-and-forth link** in key steps:

### 1. `Function` creates `Object`:

```js
Object instanceof Function; // ✅ true
```

> This means `Object` is created by `Function`.

---

### 2. `Object.prototype` is the **root** of all objects

```js
Function.prototype.__proto__ === Object.prototype; // ✅ true
```

> Even the `Function.prototype` object inherits from `Object.prototype`.

---

### 3. `Function` is also created by itself! 🤯

```js
Function instanceof Function; // ✅ true
```

> JavaScript bootstraps itself: `Function` is a constructor function that creates itself.

---

### 4. `Object` is also an object:

```js
Object instanceof Object; // ✅ true
```

> Because `Object` is a function (which is an object), it was constructed by `Function`, and inherits from `Object.prototype`.

---

## 🔗 Summary in Diagram

```txt
┌──────────────────────────────────────┐
│             Function                 │
│  (a function, created by Function)   │
└──────────────────────────────────────┘
             ▲             ▲
             │             │
    .__proto__       .constructor
             │             │
             ▼             ▼
┌────────────────┐   ┌────────────────┐
│ Function.prototype│ ─▶ Function     │
│   (object)       │   (function)     │
└────────────────┘   └────────────────┘
        ▲
        │
.__proto__ = Object.prototype
        │
        ▼
┌────────────────┐
│ Object.prototype│
│   (root object) │
└────────────────┘
        │
      null
```

---

### 🧪 Code to test these relationships:

```js
console.log(Function instanceof Function); // true
console.log(Function instanceof Object);   // true
console.log(Object instanceof Function);   // true
console.log(Object instanceof Object);     // true

console.log(Function.prototype.__proto__ === Object.prototype); // true
console.log(Object.prototype.__proto__ === null);               // true
```

---

## 🚀 Final Analogy

> **`Function` is the creator. `Object` is the base.**  
> Everything in JavaScript — even `Function` itself — is an object created by a function.

Let me know if you want a live JS visualizer link to explore this in real time.


### Dunder Prototype 
```js
deep.__proto__
```
above is called dunder prototype 
it is a function which is a getter on the Global Object.prototype and it return `this`.

```js
function Workshop(teacher) {
  this.teacher = teacher;
}

Workshop.prototype.ask = function(question) {
  console.log(this.teacher, question);
};

var deepJS = new Workshop("Kyle");
var reactJS = new Workshop("Suzy");
deepJS.__proto__ == Workshop.prototype // true
deepJS.ask("Is 'prototype' a class?");
reactJS.ask("Isn't 'prototype' ugly?");
```
above deepJS does not have this dunder so it goes above , Workshop.prototype also do not have this , so it goes above . Object.prototype has this . which is a getter function and its this context will be deepJS as it is called.


### Shadowing Prototypes
