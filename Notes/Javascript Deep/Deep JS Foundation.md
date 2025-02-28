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
- In a lexically scoped language like JS all identifier and lexical scope are determined at compile time
![](../statics/Pasted%20image%2020250228085718.png)
- Above is happening at compile time, even on line 10 reference is also resolved at compile time
- Scope plan is created here

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
- function declaration attach there marble to enclosing scope which in above case is global scope
- function expression add there marble to their own scope
![](../statics/Pasted%20image%2020250228094202.png)
![](../statics/Pasted%20image%2020250228094446.png)
- first is anonymous function expression where as second one is named function expression

### Named function expression
- Always prefer named function expression instead of anonymous function expression
- Reason
	- ![](../statics/Pasted%20image%2020250228094959.png)
	