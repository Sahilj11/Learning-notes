

### Destructing
Destructuring in JavaScript is a feature that allows you to extract values from arrays or objects and assign them to variables in a concise and convenient way. It provides an alternative syntax for extracting data, making it easier to work with complex data structures.

Destructuring can be performed on both arrays and objects, and it enables you to extract multiple values at once and assign them to separate variables.

#### Array Destructuring:
   With array destructuring, you can extract values from an array and assign them to variables. The pattern of the destructuring syntax matches the structure of the array, and values are assigned based on their respective positions.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   const [a, b, ...rest] = numbers;

   console.log(a); // Output: 1
   console.log(b); // Output: 2
   console.log(rest); // Output: [3, 4, 5]
   ```

   In this example, the array `numbers` is destructured into variables `a` and `b`, which capture the first and second elements of the array, respectively. The rest of the elements are captured in the `rest` variable using the spread syntax `...`.
   use it to combine two array
Array destructuring in JavaScript is a feature that allows you to extract values from an array and assign them to variables in a convenient and concise way. It provides a shorthand syntax for extracting data from arrays, making it easier to work with and manipulate array elements.

The basic syntax for array destructuring uses square brackets `[]` to define the pattern and variables on the left side of the assignment operator. The pattern matches the structure of the array, and the values are assigned based on their respective positions.

Here's an example to illustrate array destructuring:

```javascript
const numbers = [1, 2, 3, 4, 5];

const [a, b, c, d, e] = numbers;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 3
console.log(d); // Output: 4
console.log(e); // Output: 5
```

In this example, the array `numbers` is destructured into variables `a`, `b`, `c`, `d`, and `e`, which capture the corresponding elements of the array. The value `1` is assigned to `a`, `2` to `b`, `3` to `c`, and so on.

Array destructuring also supports the rest syntax (`...`) to capture the remaining elements of an array into a new array.

```javascript
const numbers = [1, 2, 3, 4, 5];

const [a, b, ...rest] = numbers;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(rest); // Output: [3, 4, 5]
```

In this example, the variables `a` and `b` capture the first and second elements of the array, respectively. The rest of the elements (`3`, `4`, and `5`) are captured in the `rest` variable using the spread syntax (`...`).

Array destructuring can also be used with default values. If an element in the array is `undefined` or absent, the default value will be used instead.

```javascript
const numbers = [1, 2];

const [a, b, c = 0] = numbers;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 0 (default value)
```

In this example, the variable `c` is assigned a default value of `0` since the third element in the `numbers` array is absent.

Array destructuring can be combined with other JavaScript features like swapping values, nested arrays, and functions that return arrays.

```javascript
let x = 10;
let y = 20;

[x, y] = [y, x]; // Swap values

console.log(x); // Output: 20
console.log(y); // Output: 10
```

```javascript
const nestedArray = [1, [2, 3]];

const [a, [b, c]] = nestedArray;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 3
```

```javascript
function getNumbers() {
  return [1, 2, 3];
}

const [a, b, c] = getNumbers();

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 3
```

Array destructuring is a powerful feature in JavaScript that simplifies working with arrays, providing a concise syntax for extracting values and assigning them to variables

. It is commonly used in scenarios like function returns, unpacking API responses, and manipulating array elements.


### Rest parameters
- In JavaScript, the `...args` syntax is known as the "rest parameter" or "rest syntax." It allows a function to accept an indefinite number of arguments as an array, regardless of the number of arguments passed during the function call.
- Here's an example to illustrate its usage:
```
function myFunction(...args) {
  console.log(args);
}

myFunction(1, 2, 3, 4);

```
- In this example, the `myFunction` function uses the rest parameter `...args` to accept any number of arguments. When called with `myFunction(1, 2, 3, 4)`, the function will collect all the arguments passed and store them in an array called `args`. The function then logs the `args` array to the console, which will output `[1, 2, 3, 4]`.
- The rest parameter can also be used along with other parameters. For example:
```
function addNumbers(initialValue, ...numbers) {
  let sum = initialValue;
  for (let number of numbers) {
    sum += number;
  }
  return sum;
}

console.log(addNumbers(10, 1, 2, 3, 4)); // Output: 20

```
- In this case, the `addNumbers` function takes an `initialValue` parameter and a rest parameter `...numbers`. The `initialValue` is a regular parameter, while the rest parameter `...numbers` captures any additional arguments passed after the `initialValue`. The function then calculates the sum of the `initialValue` and all the numbers in the `numbers` array, returning the result. In the example above, `addNumbers(10, 1, 2, 3, 4)` returns `20`.
- The `arguments` object is **not a real array**, while rest parameters are array instances, meaning methods like sort(), map(), forEach() or pop() can be applied on it directly.
- The `arguments` object has the additional (deprecated) callee property.
- In a non-strict function with simple parameters, the `arguments` object syncs its indices with the values of parameters. The rest parameter array never updates its value when the named parameters are re-assigned.
- The rest parameter bundles all the _extra_ parameters into a single array, but does not contain any named argument defined _before_ the `...restParam`. The `arguments` object contains all of the parameters — including the parameters in the `...restParam` array — bundled into one array-like object.
- In non-strict mode, the behavior of the `arguments` object and the rest parameter (`...restParam`) in JavaScript differs when it comes to synchronizing indices with the values of parameters.
1. `arguments` object:
	- The `arguments` object is an array-like object that holds all the arguments passed to a function, including both named parameters and any additional arguments.
	- In non-strict mode, the indices of the `arguments` object automatically synchronize with the values of the named parameters. This means that if you change the value of a named parameter, the corresponding index in the `arguments` object will also be updated.
	- Here's an example to demonstrate this behavior:
```
function myFunction(a, b, c) {
  console.log(arguments[0], arguments[1], arguments[2]);
  a = 10;
  console.log(arguments[0], arguments[1], arguments[2]);
}

myFunction(1, 2, 3);

```
![[Pasted image 20230616063240.png]]
1. In this example, changing the value of `a` to `10` also updates the corresponding index in the `arguments` object.
2. Rest parameter (`...restParam`):
    - The rest parameter allows you to capture any extra arguments passed to a function as an array.
    - Unlike the `arguments` object, the rest parameter array does not update its value when the named parameters are reassigned.
    - Here's an example to illustrate this:
```
function myFunction(a, b, ...restParam) {
  console.log(restParam);
  a = 10;
  console.log(restParam);
}

myFunction(1, 2, 3, 4, 5);

```
- ![[Pasted image 20230616063335.png]]
- 1. In this example, even though the value of `a` is changed to `10`, the rest parameter `restParam` still retains its original value, which is `[3, 4, 5]`.
- To summarize, in non-strict functions, the `arguments` object synchronizes its indices with the values of named parameters, allowing changes in the parameters to reflect in the `arguments` object. On the other hand, the rest parameter bundles extra parameters into an array but does not update its value when named parameters are reassigned.

#### Object Destructuring:
   Object destructuring allows you to extract values from an object and assign them to variables. The destructuring pattern matches the structure of the object, and the assignment is based on the property names.

   ```javascript
   const person = {
     name: "John",
     age: 30,
     city: "New York"
   };

   const { name, age, city } = person;

   console.log(name); // Output: John
   console.log(age); // Output: 30
   console.log(city); // Output: New York
   ```

   In this example, the object `person` is destructured into variables `name`, `age`, and `city`, which directly capture the corresponding property values from the object.

Object destructuring in JavaScript allows you to extract values from an object and assign them to variables in a convenient and concise manner. It provides a shorthand syntax for extracting specific properties from an object, making it easier to work with and manipulate object data.

The basic syntax for object destructuring uses curly braces `{}` on the left side of the assignment operator. Inside the curly braces, you specify the variables you want to assign, which match the property names of the object.

Here's an example to illustrate object destructuring:

```javascript
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

const { name, age, city } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(city); // Output: New York
```

In this example, the object `person` is destructured into variables `name`, `age`, and `city`, which directly capture the corresponding property values from the object. The value of the `name` property is assigned to the `name` variable, the value of the `age` property is assigned to the `age` variable, and so on.

Object destructuring also allows you to assign the extracted values to variables with different names by using a colon `:` to specify the new variable names.

```javascript
const person = {
  firstName: "John",
  lastName: "Doe"
};

const { firstName: fName, lastName: lName } = person;

console.log(fName); // Output: John
console.log(lName); // Output: Doe
```

In this example, the properties `firstName` and `lastName` of the `person` object are assigned to variables `fName` and `lName`, respectively.

Object destructuring can also be used with default values. If a property in the object is `undefined` or absent, the default value will be used instead.

```javascript
const person = {
  name: "John",
  age: 30
};

const { name, age, city = "Unknown" } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(city); // Output: Unknown (default value)
```

In this example, the `city` property is absent in the `person` object. By using the `city = "Unknown"` syntax, we assign a default value of `"Unknown"` to the `city` variable.

Object destructuring can be combined with other JavaScript features like nested objects, rest properties, and computed property names.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York"
  }
};

const { name, address: { city } } = person;

console.log(name); // Output: John
console.log(city); // Output: New York
```

```javascript
const person = {
  name: "John",
  age: 30,
  hobbies: ["reading", "gaming", "coding"]
};

const { name, ...rest } = person;

console.log(name); // Output: John
console.log(rest); // Output: { age: 30, hobbies: ["reading", "gaming", "coding"] }
```

```javascript
const prop = "name";
const { [prop]: value } = { name: "John" };

console.log(value); // Output: John
```

Object destructuring is a powerful feature in JavaScript that simplifies working with objects, providing a concise syntax for extracting values and assigning them to variables. It is commonly used in scenarios like unpacking API responses, manipulating object properties,

#### Renaming Variables:
   With destructuring, you can also assign values to variables with different names by using a colon `:` to specify the new variable name.

   ```javascript
   const person = {
     firstName: "John",
     lastName: "Doe"
   };

   const { firstName: fName, lastName: lName } = person;

   console.log(fName); // Output: John
   console.log(lName); // Output: Doe
   ```

   In this example, the properties `firstName` and `lastName` of the `person` object are assigned to variables `fName` and `lName`, respectively.

Destructuring in JavaScript simplifies the process of extracting values from arrays and objects, providing a more concise and readable syntax. It is widely used to work with data returned from APIs, function parameters, or complex data structures, making the code more expressive and reducing the need for manual value extraction.

## Shallow copy vs Deep copy 
In JavaScript, the terms "shallow copy" and "deep copy" refer to different ways of duplicating objects or arrays. The distinction lies in how nested objects and arrays within the original object are handled.

1. Shallow Copy:
   - A shallow copy duplicates the top-level structure of an object or array, but it does not create completely independent copies of nested objects or arrays.
   - Changes made to the nested objects or arrays within the copied object will affect the original object, and vice versa.
   - Shallow copy methods often include `Object.assign()`, the spread operator (`...`), and `Array.prototype.slice()`.

Example of a shallow copy using `Object.assign()`:

```javascript
const original = { a: 1, b: { c: 2 } };
const shallowCopy = Object.assign({}, original);

shallowCopy.b.c = 3; // This also changes original.b.c to 3
```

2. Deep Copy:
   - A deep copy duplicates both the top-level and all nested objects or arrays, creating completely independent copies.
   - Changes made to the copied object or its nested structures do not affect the original object, and vice versa.
   - Deep copy methods often involve recursive functions or libraries like lodash's `_.cloneDeep()`.

Example of a deep copy using a recursive function:

```javascript
function deepCopy(obj) {
  if (typeof obj !== 'object' || obj === null) {
    return obj;
  }

  const copy = Array.isArray(obj) ? [] : {};
  for (const key in obj) {
    if (Object.hasOwnProperty.call(obj, key)) {
      copy[key] = deepCopy(obj[key]);
    }
  }
  return copy;
}

const original = { a: 1, b: { c: 2 } };
const deepCopied = deepCopy(original);

deepCopied.b.c = 3; // This does not affect original.b.c
```

Keep in mind that creating deep copies can be more memory and time-intensive, especially for complex and deeply nested structures. Depending on your use case, you may choose between shallow or deep copying to achieve the desired behavior.