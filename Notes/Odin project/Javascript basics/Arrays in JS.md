## Some important methods related to Array in JS

##### Array.every
In JavaScript, the `every` method is a higher-order array method that checks whether all elements in an array satisfy a specified condition. It tests each element against a provided callback function and returns `true` if the callback function returns `true` for every element, and `false` otherwise.

The syntax of the `every` method is as follows:

```javascript
array.every(callback(element, index, array));
```

The parameters of the `every` method are:

- `callback`: A function that is called for each element in the array. It takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (optional): The index of the current element being processed.
  - `array` (optional): The array on which `every` was called.

The `every` method returns a boolean value:
- `true` if the callback function returns `true` for every element in the array.
- `false` if the callback function returns `false` for at least one element in the array.

Here's an example that demonstrates the usage of the `every` method:

```javascript
const numbers = [1, 2, 3, 4, 5];

const allEven = numbers.every(number => number % 2 === 0);
console.log(allEven); // Output: false

const allPositive = numbers.every(number => number > 0);
console.log(allPositive); // Output: true
```

In the first example, `allEven` checks if all the numbers in the `numbers` array are even. Since the array contains odd numbers, the `every` method returns `false`.

In the second example, `allPositive` checks if all the numbers in the `numbers` array are positive. Since all numbers in the array are greater than 0, the `every` method returns `true`.

#### Converting String to array
In JavaScript, you can convert a string to an array using various methods. Here are a few common approaches:

1. `split()` method: The `split()` method splits a string into an array of substrings based on a specified separator.

```javascript
var string = "Hello, World!";
var array = string.split(""); // Split by each character

console.log(array); // Output: ["H", "e", "l", "l", "o", ",", " ", "W", "o", "r", "l", "d", "!"]
```

In this example, the `split("")` method splits the string into an array of individual characters.

2. `Array.from()` method: The `Array.from()` method creates a new array from an iterable object. By passing a string as the iterable, it converts each character into an element in the array.

```javascript
var string = "Hello, World!";
var array = Array.from(string);

console.log(array); // Output: ["H", "e", "l", "l", "o", ",", " ", "W", "o", "r", "l", "d", "!"]
```

The `Array.from()` method creates an array with each character of the string as an element.

3. Using a `for` loop: You can iterate over each character of the string and push them into a new array.

```javascript
var string = "Hello, World!";
var array = [];

for (var i = 0; i < string.length; i++) {
  array.push(string[i]);
}

console.log(array); // Output: ["H", "e", "l", "l", "o", ",", " ", "W", "o", "r", "l", "d", "!"]
```

In this example, the `for` loop iterates over each character of the string and uses the `push()` method to add it to the array.

All of these methods will convert a string into an array where each element represents a character of the string. Choose the method that suits your specific use case.

##### Array Length:- returns the length (size) of an array.  for example :- `array.length`

##### Array toString():- converts an array to a string of (comma separated) array values . for example `array.toString()`

##### Array join():- also joins all array elements into a string. It behaves just like `toString()`, but in addition you can specify the separator: for example `array.join("*")`

##### Array pop():- method removes the last element from an array, returns the value that was "popped out

##### Array push():- method adds a new element to an array (at the end): method returns the new array length:

##### Array shift():-  method removes the first array element and "shifts" all other elements to a lower index, method returns the value that was "shifted out"

##### Array unshift():- method adds a new element to an array (at the beginning), and "unshifts" older elements, returns the new array length

##### Array elements can be deleted using the JavaScript operator `delete`. Using `delete` leaves `undefined` holes in the array.Use pop() or shift() instead.

##### Array concat():-  method creates a new array by merging (concatenating) existing arrays,  method does not change the existing arrays. It always returns a new array, method can take any number of array arguments

##### Array flat():- process of reducing the dimensionality of an array.The flat() method creates a new array with sub-array elements concatenated to a specified depth.

##### Array splice():- method adds new items to an array. 
- For example:- `array.splice(2,0,"Lemon", "Kiwi");`
	- The first parameter (2) defines the position **where** new elements should be **added** (spliced in). The second parameter (0) defines **how many** elements should be **removed**. The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be **added**. The `splice()` method returns an array with the deleted items
- Array slice():- slices out a piece of an array into a new array.method does not remove any elements from the source array. The `slice()` method can take two arguments like `slice(1, 3)`. The method then selects elements from the start argument, and up to (but not including) the end argument. If the end argument is omitted, like in the first examples, the `slice()` method slices out the rest of the array
- ![](../../statics/Pasted%20image%2020230614111420.png)
- In JavaScript, arrays are reference types. This means that when you assign an array to a variable or pass it as an argument to a function, you are actually working with a reference to the array's memory location, rather than a direct copy of the array's values. ^797caf
- When you assign an array to a variable or pass it as an argument, the variable doesn't contain the actual array data but rather a reference (or pointer) to the memory location where the array is stored. Multiple variables can refer to the same array in memory.
- Here's an example to illustrate how arrays are reference types:
```
const array1 = [1, 2, 3];
const array2 = array1;

array2.push(4);

console.log(array1); // Output: [1, 2, 3, 4]
console.log(array2); // Output: [1, 2, 3, 4]

```
- In this example, `array1` is assigned the array `[1, 2, 3]`. Then, `array2` is assigned the value of `array1`. Both `array1` and `array2` now refer to the same array in memory.
- When we modify `array2` by pushing the value `4`, the change is also reflected in `array1`. This happens because both variables are referencing the same underlying array.
- It's important to be aware of this behavior when working with arrays in JavaScript, as it can sometimes lead to unexpected results, particularly when dealing with mutable operations like modifying the array or passing it as a function argument.

##### Array sort()
- In JavaScript, the `sort()` method is used to sort the elements of an array in place, meaning it modifies the original array. It arranges the elements of the array according to their Unicode code point values by default.
	- The `sort()` method can be called on an array and does not take any parameters or arguments. Here's the general syntax:`array.sort();`
	- When the `sort()` method is called, it converts the elements of the array to strings and compares them based on their Unicode values. It then rearranges the elements of the array in ascending order (from the lowest value to the highest value).
	- Here's an example to illustrate the basic usage of `sort()`:
```javascript
const fruits = ['apple', 'banana', 'orange', 'grape'];
fruits.sort();

console.log(fruits); // Output: ['apple', 'banana', 'grape', 'orange']

```
- In this example, the `fruits` array is sorted alphabetically. The `sort()` method converts each element to a string and compares them based on their Unicode values. As a result, the array is sorted in ascending order.
- To sort an array in a custom order or based on specific criteria, you can pass a compare function as an argument to the `sort()` method. The compare function defines the sorting behavior by returning a negative, zero, or positive value.
- The compare function should have the following format:
```javascript
function compareFunction(a, b) {
  // Return a negative value if a should be sorted before b
  // Return zero if a and b are equal (no sorting needed)
  // Return a positive value if b should be sorted before a
// remember that no matter the condition returning one of these will have same impact , that is in case we return -1 a will be sorted before b.

  // Comparison logic goes here
}

```
```javascript
const numbers = [10, 5, 8, 2, 1];
numbers.sort(function(a, b) {
  return a - b;
});

console.log(numbers); // Output: [1, 2, 5, 8, 10]

```
- In this example, the compare function subtracts `b` from `a` (`a - b`). By returning the result, the `sort()` method arranges the numbers in ascending order.
- You can customize the compare function based on your sorting requirements, such as sorting objects based on a specific property or implementing complex sorting algorithms.
- It's important to note that the `sort()` method sorts the array in place and modifies the original array. If you need to preserve the original array, make a copy of it before calling the `sort()` method.
```javascript
let arr = [{first: "sahil" , last: "jalandhara" , year: 1993},
{first : "rahul" , last : "verma" , year : 1999}]
const sum = arr.sort((a,b)=>{
   return a.year > b.year ? -1 : 1;
});
console.table(sum);
```

##### Foreach vs map
The `forEach()` and `map()` methods in JavaScript are both used for iterating over arrays. However, there are some key differences between them:

1. Return value: 
   - `forEach()`: It doesn't return anything. The main purpose of `forEach()` is to execute a provided function for each element in the array.
   - `map()`: It returns a new array with the results of applying a provided function to each element in the original array. The function passed to `map()` should return a new value for each element.

2. Modifying the original array:
   - `forEach()`: It iterates over the elements of the array and executes a provided function for each element. It doesn't modify the original array.
   - `map()`: It creates a new array by applying a provided function to each element of the original array. The original array remains unchanged.

3. Usage:
   - `forEach()`: It is commonly used when you want to perform some action or side effect for each element in the array, such as logging, updating variables, or making API calls.
   - `map()`: It is used when you want to transform each element in the array and create a new array with the transformed values. It is often used for operations like data manipulation, extracting specific properties, or performing calculations.

Here's an example that demonstrates the differences between `forEach()` and `map()`:

```javascript
const numbers = [1, 2, 3, 4, 5];

// Using forEach()
numbers.forEach((num) => {
  console.log(num); // Logs each number to the console
});

// Using map()
const multipliedNumbers = numbers.map((num) => {
  return num * 2; // Creates a new array with each number multiplied by 2
});

console.log(multipliedNumbers); // [2, 4, 6, 8, 10]
```

In the example above, the `forEach()` method is used to iterate over the `numbers` array and log each number to the console.

The `map()` method is used to create a new array, `multipliedNumbers`, where each element is the result of multiplying the corresponding number in the `numbers` array by 2.

Note that `map()` returns a new array, allowing us to store and use the transformed values.

#### map() and filter()
- can use `map()` to do something to each item in a collection and create a new collection containing the changed items
```javascript
function toUpper(string) {
  return string.toUpperCase();
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const upperCats = cats.map(toUpper);

console.log(upperCats);
// [ "LEOPARD", "SERVAL", "JAGUAR", "TIGER", "CARACAL", "LION" ]
```
- Here we pass a function into `cats.map()`, and `map()` calls the function once for each item in the array, passing in the item. It then adds the return value from each function call to a new array, and finally returns the new array. In this case the function we provide converts the item to uppercase, so the resulting array contains all our cats in uppercase:
- You can use `filter()` to test each item in a collection, and create a new collection containing only items that match:
```
function lCat(cat) {
  return cat.startsWith("L");
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const filtered = cats.filter(lCat);

console.log(filtered);
// [ "Leopard", "Lion" ]
```
- This looks a lot like `map()`, except the function we pass in returns a boolean: if it returns `true`, then the item is included in the new array. Our function tests that the item starts with the letter "L", so the result is an array containing only cats whose names start with "L":
- Note that `map()` and `filter()` are both often used with _function expressions_, which we will learn about in the Functions module. Using function expressions we could rewrite the example above to be much more compact:
```
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const filtered = cats.filter((cat) => cat.startsWith("L"));
console.log(filtered);
// [ "Leopard", "Lion" ]
```
- Imagine you have a list of numbers written on a piece of paper, and you want to do something to each number and write down the results on a new piece of paper. That's what the `map()` method does
- The `map()` method is like having a special machine that takes each number from your list, does something to it, and gives you a new list with the results.
- Here's how it works:
	1. You start with an array, which is like a list of things. Let's say your array has these numbers: `[1, 2, 3, 4, 5]`.
	2. You use the `map()` method on the array, just like pressing a button on the machine.
	3. You tell the machine what to do with each number. You use a special function that you create. This function will be called for each number in the array.
	4. The machine takes the first number from your array, gives it to your special function, and asks, "What should I do with this number?" You tell the machine what to do in your function.
	5. The machine writes down the result from your function on a new piece of paper, which is a new array.
	6. The machine repeats this process for each number in the original array until it has gone through all the numbers.
	7. Finally, the machine gives you the new array with all the results.
- So, the `map()` method lets you take an array, do something to each item using a special function, and get a new array with the results. It's like having a magical machine that transforms one list into another!
##### Difference b/w map and filter 
In JavaScript, both the `map` and `filter` methods are array methods that operate on arrays and allow for data transformation and filtering. While they have similarities, they serve different purposes:

1. `map` method:
   - Purpose: The `map` method is used to transform each element of an array into a new element based on a provided callback function.
   - Execution: It iterates over each element of the array, calls the provided callback function on each element, and creates a new array with the returned values.
   - Return value: The `map` method returns a new array of the same length as the original array, where each element is the result of the callback function applied to the corresponding element of the original array.
   - Example:
     ```javascript
     const numbers = [1, 2, 3, 4, 5];
     const doubledNumbers = numbers.map((num) => num * 2);
     console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]
     ```

2. `filter` method:
   - Purpose: The `filter` method is used to create a new array that contains only the elements from the original array that meet a specified condition.
   - Execution: It iterates over each element of the array, calls the provided callback function on each element, and includes the element in the new array if the callback function returns `true`.
   - Return value: The `filter` method returns a new array that contains only the elements for which the callback function returned `true`.
   - Example:
     ```javascript
     const numbers = [1, 2, 3, 4, 5];
     const evenNumbers = numbers.filter((num) => num % 2 === 0);
     console.log(evenNumbers); // Output: [2, 4]
     ```

In summary, `map` is used to transform each element of an array and create a new array of the same length, while `filter` is used to create a new array containing only the elements that meet a specified condition. Both methods are powerful tools for working with arrays in JavaScript and can be used separately or in combination to manipulate and filter data.

##### Array reduce()
- Array reduce():- 
	- The `reduce()` method in JavaScript is used to reduce the elements of an array to a single value. It executes a provided callback function on each element of the array, resulting in a single output value.
	- The syntax for the `reduce()` method is as follows:
```javascript
array.reduce(callback, initialValue)
```
- Here's a breakdown of the parameters:
- `callback`: A function that is executed on each element of the array. It takes four arguments:
	- `accumulator`: The accumulated value from previous iterations or the `initialValue` if provided.
	- `currentValue`: The current element being processed.
	- `currentIndex` (optional): The index of the current element being processed.
	- `array` (optional): The array on which `reduce()` was called.
- `initialValue` (optional): An initial value for the accumulator. If not provided, the first element of the array will be used as the initial value and the callback function will start executing from the second element.
- The callback function should perform some operation using the `accumulator` and `currentValue` and return the updated `accumulator`. The final value of the accumulator at the end of the iteration is returned as the result of the `reduce()` method.
- Here's an example that demonstrates the usage of `reduce()`:
```javascript
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // Output: 15

```
- In the above example, we start with an array of numbers and use `reduce()` to calculate their sum. The initial value of the accumulator is set to 0, and in each iteration, the callback function adds the `currentValue` to the `accumulator`. The final result is the sum of all the numbers in the array, which is 15.
- Note that the `reduce()` method can be used for various operations, not just summation. By modifying the callback function, you can achieve different reductions, such as finding the maximum or minimum value, calculating averages, concatenating strings, or performing custom calculations based on your specific needs.
```javascript
let arr = [{first: "sahil" , last: "jalandhara" , year: 1993},
{first : "rahul" , last : "verma" , year : 1999}]
const sum = arr.reduce((total, currentValue) =>{
  return total + currentValue.year;
}, 0);
console.log(sum);
```
- ![]( ../../statics/Pasted%20image%2020230619081637.png )
- more problem related to reduce method

##### Array some
- The `some()` method in JavaScript is used to test whether at least one element in an array satisfies a given condition. It returns `true` if the condition is satisfied by at least one element, and `false` otherwise.
- Here's the syntax for the `some()` method:
```javascript
array.some(callback)

```
- The `callback` function takes three arguments:
	- `element`: The current element being processed in the array.
	- `index` (optional): The index of the current element being processed.
	- `array` (optional): The array on which `some()` was called.
- The `callback` function should return a boolean value indicating whether the condition is met for the current element.
- Here's an example that demonstrates the usage of `some()`:
```javascript
const numbers = [1, 2, 3, 4, 5];

const hasEvenNumber = numbers.some((element) => {
  return element % 2 === 0;
});

console.log(hasEvenNumber); // Output: true

```
- In the above example, we have an array of numbers, and we use the `some()` method to check if at least one element in the array is even. The `callback` function tests whether the `element` modulo 2 is equal to 0 (i.e., it checks if the element is even). The `some()` method returns `true` because there is at least one even number in the array.
- You can modify the `callback` function to check for different conditions based on your requirements, such as checking for specific values, using comparison operators, or accessing properties of objects within the array.
##### Array every()
- The `every()` method in JavaScript is used to test whether all elements in an array satisfy a given condition. It returns `true` if the condition is satisfied by all elements, and `false` otherwise.
- The syntax for the `every()` method is as follows:
```javascript
array.every(callback)
```
- The `callback` function takes three arguments:
	- `element`: The current element being processed in the array.
	- `index` (optional): The index of the current element being processed.
	- `array` (optional): The array on which `every()` was called.
- The `callback` function should return a boolean value indicating whether the condition is met for the current element. 
- Here's an example that demonstrates the usage of `every()`:
``` javascript
const numbers = [2, 4, 6, 8, 10];
const allEven = numbers.every((element) => {
  return element % 2 === 0;
});
console.log(allEven); // Output: true
```
- In the above example, we have an array of numbers, and we use the `every()` method to check if all elements in the array are even. The `callback` function tests whether the `element` modulo 2 is equal to 0 (i.e., it checks if the element is even). Since all elements in the array are even, the `every()` method returns `true`.
- You can modify the `callback` function to check for different conditions based on your requirements, such as checking for specific values, using comparison operators, or accessing properties of objects within the array.
##### Array find()
- The `find()` method in JavaScript is used to retrieve the first element in an array that satisfies a given condition. It returns the value of the first element found, or `undefined` if no element satisfies the condition.
- The syntax for the `find()` method is as follows:
```javascript
array.find(callback)
```
- The `callback` function takes three arguments:
	- `element`: The current element being processed in the array.
	- `index` (optional): The index of the current element being processed.
	- `array` (optional): The array on which `find()` was called.
- The `callback` function should return a boolean value indicating whether the condition is met for the current element.
- Here's an example that demonstrates the usage of `find()`:
```javascript
const numbers = [1, 3, 5, 7, 9];

const foundNumber = numbers.find((element) => {
  return element > 5;
});
console.log(foundNumber); // Output: 7
```
- In the above example, we have an array of numbers, and we use the `find()` method to find the first number greater than 5. The `callback` function tests whether the `element` is greater than 5. The `find()` method returns the first number that satisfies the condition, which is `7`.
- You can modify the `callback` function to check for different conditions based on your requirements, such as checking for specific values, using comparison operators, or accessing properties of objects within the array.
## Loops

#### for...of loop
-  basic tool for looping through a collection is the `for...of` loop:
```
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

for (const cat of cats) {
  console.log(cat);
}
```
- In this example, `for (const cat of cats)` says:
	1. Given the collection `cats`, get the first item in the collection.
	2. Assign it to the variable `cat` and then run the code between the curly brackets `{}`.
	3. Get the next item, and repeat (2) until you've reached the end of the collection.


#### Skipping iterations with continue
- The [continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue) statement works similarly to `break`, but instead of breaking out of the loop entirely, it skips to the next iteration of the loop. Let's look at another example that takes a number as an input, and returns only the numbers that are squares of integers (whole numbers).
The HTML is basically the same as the last example — a simple numeric input, and a paragraph for output.

```
<label for="number">Enter number: </label>
<input id="number" type="number" />
<button>Generate integer squares</button>

<p>Output:</p>
```

The JavaScript is mostly the same too, although the loop itself is a bit different:
```
const para = document.querySelector("p");
const input = document.querySelector("input");
const btn = document.querySelector("button");

btn.addEventListener("click", () => {
  para.textContent = "Output: ";
  const num = input.value;
  input.value = "";
  input.focus();
  for (let i = 1; i <= num; i++) {
    let sqRoot = Math.sqrt(i);
    if (Math.floor(sqRoot) !== sqRoot) {
      continue;
    }
    para.textContent += `${i} `;
  }
});
```

#### New syntax
- const para = document.createElement('p'); output.appendChild(para);
### Regular expression
- It is a way to search through string text
- it is start with / and end with /  after this comes flags . one of the flag is global which search for all the occurs of a text in a string 
	- /a/g :- flag global 
	- /a/i :- search for a or A . you can also combine these flag like /a/gi :- here it will search all the a or A
- we can add certain thing in regular expression . like /e+/g :- match e or more than one e
- /ea?/g:- optional . ![](../../statics/Pasted%20image%2020230616052341.png )
	- you can see here it is ignoring the a's and only looking for ea
- /ea*/g:- match 0 or more of the preceding token ![[Pasted image 20230616052536.png]]
- /.at/g:- it matches anything at all , but it can't match a new line![[Pasted image 20230616052812.png]]
- /t./g:- here will search t and one character after t. you can also do /t../g :- but here you can see instead of continuing the search through next line it is not doing that 
	- ![](../../statics/Pasted%20image%2020230616052958.png )
- if you want to search for . or any special character than use /`\`./g :- here the `\` is a escape character that cancel the character that comes after it 
- /`\`w/g:- matches any word character. you can use W to do the opposite which is not matching the word character
- /`\`s/g :- any form of white spaces. you can use S to do the opposite
- /`\`w{4,}/g :- what if we want to search for word for a certain length , inside the {} we can put min and max value . this expression will search for 4 or more character . here , is playing the role 
- /[fc]at/g :- inside of [ ] the character which is mentioned . it will see all the word that start with f or c and ends with at 
	- ![](../../statics/Pasted%20image%2020230616053901.png )
- /[a-zA-Z]at/g:- we can also do ranges inside the square bracket from a to z and also in capital letters 
- /(t|T)he/g :- anything inside of () is a group . here in this example it is searching for uppercase and lowecase t
- good practice is to store the regular expression in a separate variable , for more readability
- [Learn Regular Expressions In 20 Minutes - YouTube](https://www.youtube.com/watch?v=rhzKDrUiJVk&t=269s)
- complete later
