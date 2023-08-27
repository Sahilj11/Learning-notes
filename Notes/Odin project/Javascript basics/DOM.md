## Spread selector
### In function calls
- what `...` does that it passes the string or array elements as separate argument in function calls
```
const temp = [33,667,7,78,67];
Math.min(...temp);
```
- in above case `...` is ensuring that each of element of array is passed as separate argument. it is usefull as we cannot just pass the whole array here . it is like doing `Math.min(33,667,7,78,67)`
- But now you have more flexibility 
- You can also use this in strings 
```
const text = "BANANA";
console.log(...text); 

// Output will be B A N A N A
```
- here spread selector is iterating through each character and passing it as separate argument in one go
### In array literals 
- as we know that array are reference type [[Arrays in JS#^797caf]]
- we can use `...` to join two array 
```
const a = ["a", "b","c"];
const L = [...a];
```
- this will make a copy of a in L
- you can also join two array
```
const a = ["a", "b","c"];
const L = ["j", "k", "l"];

const join = [...L,...a];

// this will join a and L array
```

## Element creation 
- document.createElement(tagName, [options]) creates a new element of tag type tagName. `[options]` in this case means you can add some optional parameters to the function. Don’t worry about these at this point.

```javascript
const div = document.createElement('div');
```
- This function does NOT put your new element into the DOM - it simply creates it in memory. This is so that you can manipulate the element (by adding styles, classes, ids, text, etc.) before placing it on the page. You can place the element into the DOM with one of the following methods.
- Append Elements
	- _parentNode_.appendChild(_childNode_) appends _childNode_ as the last child of _parentNode_
	- _parentNode_.insertBefore(_newNode_, _referenceNode_) inserts _newNode_ into _parentNode_ before _referenceNode_
- Remove Elements
	- _parentNode_.removeChild(_child_) removes _child_ from _parentNode_ on the DOM and returns a reference to _child_
#### Altering Elements
- When you have a reference to an element, you can use that reference to alter the element’s own properties. This allows you to do many useful alterations, like adding/removing and altering attributes, changing classes, adding inline style information and more.

```javascript
const div = document.createElement('div');                     
// creates a new div referenced in the variable 'div'
```
- Adding Inline Style
```javascript
div.style.color = 'blue';                                      
// adds the indicated style rule

div.style.cssText = 'color: blue; background: white;';          
// adds several style rules

div.setAttribute('style', 'color: blue; background: white;');    
// adds several style rules
```
- See DOM Enlightenment’s section on CSS Style rules for more info on inline styles.
- Note that if you’re accessing a kebab-cased CSS rule from JS, you’ll either need to use camelCase or you’ll need to use bracket notation instead of dot notation.
#### Editing Attributes
```javascript
div.setAttribute('id', 'theDiv');                              
// if id exists, update it to 'theDiv', else create an id
// with value "theDiv"

div.getAttribute('id');                                        
// returns value of specified attribute, in this case
// "theDiv"

div.removeAttribute('id');                                     
// removes specified attribute
```
#### Working with Classes
```javascript
div.classList.add('new');                                      
// adds class "new" to your new div

div.classList.remove('new');                                   
// removes "new" class from div

div.classList.toggle('active');                                
// if div doesn't have class "active" then add it, or if
// it does, then remove it
```
- It is often standard (and cleaner) to toggle a CSS style rather than adding and removing inline CSS.
#### Adding Text Content
```javascript
div.textContent = 'Hello World!'                               
// creates a text node containing "Hello World!" and
// inserts it in div
```
#### Adding HTML Content
```javascript
div.innerHTML = '<span>Hello World!</span>';                   
// renders the HTML inside div
```
- *_Note that textContent is preferable for adding text, and innerHTML should be used sparingly as it can create security risks if misused. Check out [this video](https://www.youtube.com/watch?v=ns1LX6mEvyM&ab_channel=WebDevSimplified) if you want to see an example of how._
- Let’s take a minute to review what we’ve covered and give you a chance to practice this stuff before moving on. Check out this example of creating and appending a DOM element to a webpage.

- Let’s take a minute to review what we’ve covered and give you a chance to practice this stuff before moving on. Check out this example of creating and appending a DOM element to a webpage.
```html
<!-- your HTML file: -->
<body>
  <h1>
    THE TITLE OF YOUR WEBPAGE
  </h1>
  <div id="container"></div>
</body>
```
```javascript
// your JavaScript file
const container = document.querySelector('#container');

const content = document.createElement('div');
content.classList.add('content');
content.textContent = 'This is the glorious text-content!';

container.appendChild(content);
```
- This JavaScript code creates a container element on a web page and adds some content to it.
- First, it selects an element with the ID "container" using the `querySelector` method from the `document` object. The `querySelector` method allows you to select an element on the page using a CSS selector.
- Next, it creates a new `div` element using the `createElement` method also from the `document` object. This `div` element represents the content that will be added to the container.
- The `classList.add` method adds a CSS class to the `div` element. In this case, it adds the class "content" to the newly created `div`.
- The `textContent` property is used to set the text content of the `div` element. In this example, the text content is set to "This is the glorious text-content!".
- Finally, the `appendChild` method is called on the `container` element, with the `content` element as its argument. This appends the `content` element as a child of the `container` element, making it visible on the web page within the container.
- Overall, this code creates a `div` element with the class "content" and the text "This is the glorious text-content!", and appends it to an element with the ID "container" on the web page.
- All in all it’s a simple process. After the JavaScript code is run, our DOM tree will look like this:

```html
<!-- The DOM -->
<body>
  <h1>
    THE TITLE OF YOUR WEBPAGE
  </h1>
  <div id="container">
  	<div class="content">
      This is the glorious text-content!
    </div>
  </div>
</body>
```

- Keep in mind that the JavaScript does _not_ alter your HTML, but the DOM - your HTML file will look the same, but the JavaScript changes what the browser renders
### DOM Loaded
- Your JavaScript, for the most part, is run whenever the JS file is run, or when the script tag is encountered in the HTML. If you are including your JavaScript at the top of your file, many of these DOM manipulation methods will not work because the JS code is being run _before_ the nodes are created in the DOM. The simplest way to fix this is to include your JavaScript at the bottom of your HTML file so that it gets run after the DOM nodes are parsed and created.
- Alternatively, you can link the JavaScript file in the `<head>` of your HTML document. Use the `<script>` tag with the `src` attribute containing the path to the JS file, and include the `defer` keyword to load the file _after_ the HTML is parsed, as such:
```html
<head>
  <script src="js-file.js" defer></script>
</head>
```
- Read the second bullet point in [this MDN article](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#applying_css_and_javascript_to_html) for more information, which also includes a link to additional script loading strategies.

## Events 
- There are three primary ways to go about this: You can specify function attributes directly on your HTML elements, you can set properties of form `on[eventType]` (`onclick`, `onmousedown`, etc.) on the DOM nodes in your JavaScript, or you can attach event listeners to the DOM nodes in your JavaScript. Event listeners are definitely the preferred method
- 1. Specifying function attributes directly on HTML elements: In this approach, you can define event handlers by adding attributes to your HTML elements that start with "on" followed by the name of the event you want to handle. For example, you can add an `onclick` attribute to a button element and set its value to the name of a JavaScript function. When the button is clicked, the specified function will be invoked. This approach is straightforward and easy to use, but it's not always the best choice for complex applications.
2. Setting properties of form on[eventType] on DOM nodes in JavaScript: This approach involves setting properties on DOM nodes directly in your JavaScript code. The properties are named after the event type you want to handle, prefixed with "on". For example, you can set the `onclick` property of a button element to a function reference. This method gives you more flexibility than the first approach, as you can dynamically assign event handlers based on certain conditions or manipulate the event handling behavior at runtime.
	- . Certainly! Let's delve into an example to illustrate the approach of setting properties of `on[eventType]` on DOM nodes in JavaScript
	- Consider an HTML button element that you want to associate with a click event and execute a function when it is clicked. You can achieve this using the `onclick` property in JavaScript. Here's an example:HTML:`<button id="myButton">Click Me!</button>`
	- JavaScript:
```// Get the button element 
var button = document.getElementById("myButton");  

// Define a function to be executed when the button is clicked 
function handleClick() {   console.log("Button clicked!"); }  

// Set the onclick property of the button to the defined function

button.onclick = handleClick;
```
- In the above example, we retrieve the button element using `document.getElementById()` and store it in the `button` variable. Then, we define a function named `handleClick()` that will be executed when the button is clicked.
- Next, we assign the function reference to the `onclick` property of the button element using the assignment operator (`=`). By doing so, we are instructing the browser to invoke the `handleClick()` function whenever the button is clicked.
- This approach provides flexibility, as you can dynamically change the event handler by assigning a different function to the `onclick` property based on certain conditions or user interactions. For example, you can update the `onclick` property inside another event handler or after an asynchronous operation completes.
`// Update the onclick property to a different function dynamically button.onclick = function() {   console.log("Different function executed!"); };`
- In the above example, we assign an anonymous function directly to the `onclick` property, effectively changing the behavior of the button when clicked.
- This approach allows you to manipulate event handling behavior at runtime and provides an alternative to defining event handlers directly in the HTML markup or using event listeners.
4. Attaching event listeners to DOM nodes in JavaScript: The third approach involves using the `addEventListener` method to attach event listeners to DOM nodes in your JavaScript code. With this method, you can specify the event type to listen for and provide a callback function that will be executed when the event occurs. This approach is highly flexible and allows you to add multiple event listeners to the same element, remove event listeners, and handle events in more complex scenarios.

## Understanding Callbacks
-  Put simply, callbacks are functions that are passed into another function as an argument.
#### Anatomy of a function 
- 
#### Normal Functions (Named Functions)
- Normal functions, probably the first way you learned about creating functions. Understanding the anatomy of these will help you understand the other types of functions as well.  
```
function funkyFunction(music, isWhiteBoy) {
  if (isWhiteBoy) {
    console.log('Play: ' +  music);
  }
}
```
- This is actually called a `function declaration` and is broken into a few parts.
1. The `function` keyword
    - This tells the JavaScript compiler you are making a named function
2. The name
    - This is the name of the function, and what you will use when you call it. It is also used in stack traces.
3. The parameters
    - everything between `(` and `)` is a parameter, these must be separated by commas if there is more than one. There may also be nothing between the `()` if the function does not take any parameters. The parenthesis are required.
4. The function body
    - This is where the function actually does something. This code gets run with whatever values are passed into the parameters.
Calling a function looks similar to declaring it. When you call the function, you type the name of the function and add `()` after. (without the `function` keyword and the body). Inside the `()` you may pass it the values you want the parameters you defined to represent. These `arguments` are used like variables inside the body of the function.

#### Anonymous Functions
- These are very similar to normal functions, with just a few differences. Anonymous functions are not 'named', and have a few different syntaxes. Even though they cannot have a name, they can be assigned to a variable. Even though when assigned to a variable they show up in stack traces, they are still considered an anonymous function. They may show up as 'anonymous function' in stack traces when passed into other functions as callbacks, however.
- Anonymous functions are mostly used by passing them into other functions as a `callback`. This will become more clear later.
- Each of the functions below are identical to the funky Function above in their 'funk-tionality'.
```
// This example is still an anonymous function even though we used the `function` keyword, as it doesn't have a name.
const funkyFunction = function(music, isWhiteBoy) {
  if (isWhiteBoy) {
    console.log('Play: ' +  music);
  }
}

// This is called an arrow function, we'll get into these soon.
const funkyFunction = (music, isWhiteBoy) => {
  if (isWhiteBoy) {
    console.log('Play: ' +  music);
  }
}
```
- An anonymous function is just a function that does not have a name, this doesn't mean that it cannot be called. Each of the above functions can be called exactly the same way:  

```
funkyFunction('that funky music', true);
```

**And this is because functions are 'first class citizens' in JavaScript and can be assigned to variables. Or passed as an argument to another function.**
- what is stack traces
	- A stack trace is a report that provides information about the sequence of function calls that led to an error or an exception in a program. It shows the order in which functions were called, starting from the point where the error occurred and going back through the call chain.
	- Think of it like a trail of breadcrumbs that helps you trace your steps back to where the problem originated. Each step represents a function call, and the stack trace shows the exact path through different functions leading up to the error.
	- When an error occurs in a program, such as a runtime error or an unhandled exception, the JavaScript engine or runtime environment generates a stack trace. This stack trace is typically displayed in the console or error log, and it includes information about the file names, line numbers, and function names involved in the call chain.
	- Here's a simplified example of a stack trace:

`Error: Something went wrong!     at functionC (myfile.js:25:12)     at functionB (myfile.js:15:8)     at functionA (myfile.js:5:4)     at main (myfile.js:2:1)`
	- In the above stack trace, the error occurred in the function `functionC`, which is called from `functionB`, which is called from `functionA`, which is ultimately called from the `main` function.
	- The stack trace provides information about the exact line numbers and file names where each function call occurred. This helps you identify the location of the error and understand the execution flow leading up to it. It can be valuable for debugging purposes, as it allows developers to pinpoint the cause of the error and trace it back to the specific code that needs to be fixed.
	- By examining the stack trace, you can identify which functions were in the call chain leading to the error and understand the order in which they were called. This information can assist in identifying the root cause of the error, finding potential issues in the code, and fixing the problem.
#### Arrow functions 
- These are just a shorter way to write a function. They do have some special rules however, and understanding the rules imposed by arrow functions will help you understand callbacks. We're going to ignore the `this` binding rules for these functions for now.
- If there is only one argument, the parenthesis `()` can be omitted
- if arrow functions are one line, the brackets `{}` can be omitted.
    - When omitting the brackets, the arrow function returns the evaluated expression without requiring the `return` keyword.
The functions below are variations of the rules above  
```
const playThe = (funky) => {
  return funky + " music";
}

const playThe = funky => {
  return funky + " music";
}

const playThe = funky => funky + " music";

// You can call all of these functions like: `playThe('blues')`
```
Below are some examples of an arrow function without an argument. These functions are all identical as well. Notice the `()` in place of any named arguments. It is required because there aren't any parameters.
- Below are some examples of an arrow function without an argument. These functions are all identical as well. Notice the `()` in place of any named arguments. It is required because there aren't any parameters.  
```
const playThat = () => "funky music";

const playThat = () => { return "funky music"; }

const playThat = () => {
  return "funky music";
}
```

#### What Callbacks Look Like
You most likely have seen, or even used, callbacks and not realized it. They are used frequently in JavaScript. Understanding JavaScript is impossible without understanding callbacks. Below is an example of something you may have run into before.  

```
const notes = ['do', 're', 'me'];

notes.forEach((note) => console.log(note));
```

This is the `forEach` array method. This method simply takes a `callback` function as its argument. (Don't forget that `forEach` is a function itself).

There are many other ways to do the same thing (as is tradition in JavaScript), below are a few more ways to write this code:  
```
const notes = ['do', 'ray', 'me'];

notes.forEach((note) => { 
  console.log(note);
});

notes.forEach(function(note) {
  console.log(note); 
});

// This one is tricky, but will make more sense later
notes.forEach(console.log); 
```
 - https://dev.to/i3uckwheat/understanding-callbacks-2o9e
#### Attaching listeners to groups of nodes
- This might seem like a lot of code if you’re attaching lots of similar event listeners to many elements. There are a few ways to go about doing that more efficiently. We learned above that we can get a nodelist of all of the items matching a specific selector with `querySelectorAll('selector')`. In order to add a listener to each of them we simply need to iterate through the whole list like so:
```html
<div id="container">
    <button id="1">Click Me</button>
    <button id="2">Click Me</button>
    <button id="3">Click Me</button>
</div>
```
```javascript
// buttons is a node list. It looks and acts much like an array.
const buttons = document.querySelectorAll('button');

// we use the .forEach method to iterate through each button
buttons.forEach((button) => {

  // and for each one we add a 'click' listener
  button.addEventListener('click', () => {
    alert(button.id);
  });
});
```
This is just the tip of the iceberg when it comes to DOM manipulation and event handling, but it’s enough to get you started with some exercises. In our examples so far we have been using the ‘click’ event exclusively, but there are _many_ more available to you.

## Keyboard event
```
window.addEventListener("keydown", e=>{

   const pElement = document.querySelector("p");

   pElement.textContent = `Keyboard key: ${e.key} | Keyboard code: ${e.code}`

});
```
## JavaScript Event Capture, Propagation and Bubbling
- https://www.youtube.com/watch?v=F1anRyL37lE
- tommorow 
