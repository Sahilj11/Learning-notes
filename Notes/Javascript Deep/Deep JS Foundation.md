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