## Script scope
In JavaScript, script scope refers to the visibility and accessibility of variables, functions, and objects within a specific script or JavaScript file.

When you define a variable or a function in the global scope (outside of any function or block), it becomes a part of the global object (`window` object in browsers or `global` object in Node.js). This means that variables and functions declared in the script scope are accessible throughout the entire script and can be accessed from any part of the code.

However, when variables or functions are defined inside a function or block, they have a narrower scope and are only accessible within that function or block. This is known as function or block scope, respectively.

For example:

```javascript
// Script scope
const globalVariable = "Hello, world!";

function foo() {
  // Function scope
  const localVariable = "Inside function";

  console.log(globalVariable); // Accessible
  console.log(localVariable); // Accessible
}

console.log(globalVariable); // Accessible
console.log(localVariable); // Not accessible (ReferenceError)
```

In the above code snippet, `globalVariable` is defined in the script scope, so it can be accessed both inside and outside the `foo` function. However, `localVariable` is defined inside the `foo` function, so it is only accessible within that function. Attempting to access `localVariable` outside the function would result in a `ReferenceError`.

Understanding the scope of variables and functions is important for managing the visibility and lifetime of variables, avoiding naming conflicts, and maintaining code organization and modularity.


## Difference b/w script and global scope
In JavaScript, the terms "script scope" and "global scope" are sometimes used interchangeably, but they can have slightly different meanings depending on the context. Let's explore the difference between these two concepts:

1. Script Scope:
   - Script scope refers to the overall scope of a JavaScript file or module. It encompasses the entire file and includes all the variables, functions, and objects defined within that file.
   - Variables and functions declared at the top level of a script (outside of any function or block) are considered to be in the script scope.
   - Script scope is also commonly referred to as the global scope because variables declared in the script scope become properties of the global object (`window` object in browsers or `global` object in Node.js).
   - Variables and functions in the script scope are accessible throughout the entire script and can be accessed from any part of the code.

2. Global Scope:
   - The global scope specifically refers to the scope outside of any function or block, where variables and functions are accessible from any part of the codebase.
   - In the browser environment, global scope refers to the scope within the global object (`window` object), where variables and functions declared outside of any function become properties of the global object.
   - In Node.js, global scope refers to the scope within the `global` object, which serves a similar purpose as the `window` object in the browser.
   - Variables and functions in the global scope are accessible by any code within the same script, as well as by other scripts or modules that have access to the global scope.

In summary, script scope generally refers to the scope of a specific JavaScript file or module, while global scope specifically refers to the scope outside of any function or block where variables and functions are accessible from anywhere in the codebase. However, depending on the context, these terms can be used interchangeably to refer to the same concept.

## LET vs VAR
In JavaScript, `var` and `let` are both used for variable declaration, but they have some differences in terms of scope and hoisting. Here are the key differences:

1. Scope: Variables declared with `var` have function scope, meaning they are accessible within the entire function in which they are defined, regardless of block boundaries. On the other hand, variables declared with `let` have block scope, meaning they are only accessible within the block (enclosed by curly braces) in which they are defined.

   ```javascript
   function example() {
     if (true) {
       var x = 10; // function-scoped
       let y = 20; // block-scoped
     }
     console.log(x); // 10
     console.log(y); // ReferenceError: y is not defined
   }
   ```

2. Hoisting: Variables declared with `var` are hoisted to the top of their function scope or global scope, which means they can be accessed before they are declared. However, their initial value will be `undefined` until the assignment is made. Variables declared with `let` are not hoisted, and trying to access them before the declaration will result in a ReferenceError.

   ```javascript
   function example() {
     console.log(x); // undefined
     console.log(y); // ReferenceError: y is not defined

     var x = 10;
     let y = 20;
   }
   ```

3. Re-declaration: Variables declared with `var` can be re-declared within the same scope without any error. On the other hand, variables declared with `let` cannot be re-declared within the same block scope.

   ```javascript
   var x = 10;
   var x = 20; // No error, x is re-declared

   let y = 10;
   let y = 20; // SyntaxError: Identifier 'y' has already been declared
   ```

Overall, using `let` provides more predictable scoping behavior and helps catch errors caused by variable re-declarations or accessing variables before they are declared. It is generally recommended to use `let` or `const` (for constants) over `var` in modern JavaScript.