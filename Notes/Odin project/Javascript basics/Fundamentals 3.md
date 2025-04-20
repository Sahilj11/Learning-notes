# Functions
### Function vs methods
- **Functions** that are part of objects are called **methods**.

### Default parameters
- If you're writing a function and want to support optional parameters, you can specify default values by adding `=` after the name of the parameter, followed by the default value:
```
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
```
### Anonymous functions and arrow functions
- But you can also create a function that doesn't have a name:

```
(function () {
  alert("hello");
});
```
- This is called an **anonymous function**, because it has no name. You'll often see anonymous functions when a function expects to receive another function as a parameter. In this case the function parameter is often passed as an anonymous function.
- For example, let's say you want to run some code when the user types into a text box. To do this you can call the `addEventListener()`"addEventListenefunction of the text box. This function expects you to pass it (at least) two parameters:
- the name of the event to listen for, which in this case is `keydown`
- a function to run when the event happens.
- When the user presses a key, the browser will call the function you provided, and will pass it a parameter containing information about this event, including the particular key that the user pressed:
```
function logKey(event) {
  console.log(`You pressed "${event.key}".`);
}

textBox.addEventListener("keydown", logKey);
```
- Instead of defining a separate `logKey()` function, you can pass an anonymous function into `addEventListener()`:
```
textBox.addEventListener("keydown", function (event) {
  console.log(`You pressed "${event.key}".`);
});
```
### Arrow functions
- If you pass an anonymous function like this, there's an alternative form you can use, called an **arrow function**. Instead of `function(event)`, you write `(event) =>`:
```
textBox.addEventListener("keydown", (event) => {
  console.log(`You pressed "${event.key}".`);
});
```
- If the function only takes one parameter, you can omit the brackets around the parameter:
```
textBox.addEventListener("keydown", event => {
  console.log(`You pressed "${event.key}".`);
});
```
- Finally, if your function contains only one line that's a `return` statement, you can also omit the braces and the `return` keyword, and implicitly return the expression. In the following example we're using the `map()` method of `Array` to double every value in the original array:
```
const originals = [1, 2, 3];

const doubled = originals.map(item => item * 2);

console.log(doubled); // [2, 4, 6]
```
- The `map()` method takes each item in the array in turn, passing it into the given function. It then takes the value returned by that function and adds it to a new array.
- So in the example above, `(item) => item * 2` is the arrow function equivalent of:
```
function doubleItem(item) {
  return item * 2;
}
```

### Function return value 
- Some functions don't return any value. (In these cases, our reference pages list the return value as `void` or `undefined`.)
### Parameters and arguments 
![](../../statics/Pasted%20image%2020230613152615.png )

- parameters are the items listed between the parentheses in the function declaration
- Function arguments are the actual values we decide to pass to the function. In the example above, the function definition is written on the first line: `function favoriteAnimal(animal)`. The parameter, `animal`, is found inside the parentheses
- The last line, `favoriteAnimal('Goat')`, is where we are calling our `favoriteAnimal` function and passing the value `'Goat'` inside that function. Here, `'Goat'` is our argument. We are telling the `favoriteAnimal` function, “Please send `'Goat'` to the favoriteAnimal function and use `'Goat'` wherever the ‘animal’ placeholder is.”
- 
