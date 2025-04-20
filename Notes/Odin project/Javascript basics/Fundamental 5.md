## Objects 
- objects are used to store keyed collections of various data and more complex entities. In JavaScript, objects penetrate almost every aspect of the language. So we must understand them first before going in-depth anywhere else.
- An object can be created with figure brackets `{…}` with an optional list of _properties_. A property is a “key: value” pair, where `key` is a string (also called a “property name”), and `value` can be anything.
```
let user = new Object(); // "object constructor" syntax 
let user = {}; // "object literal" syntax
```
- Usually, the figure brackets `{...}` are used. That declaration is called an _object literal_.

### Literal and positions
- A property has a key (also known as “name” or “identifier”) before the colon `":"` and a value to the right of it.
- In the `user` object, there are two properties:
	1. The first property has the name `"name"` and the value `"John"`.
	2. The second one has the name `"age"` and the value `30`.
- The resulting `user` object can be imagined as a cabinet with two signed files labeled “name” and “age”.
- We can add, remove and read files from it at any time.
- ![](../../statics/Pasted%20image%2020230618052540.png )
- Property values are accessible using the dot notation:
```javascript
/ get property values of the object: 
alert( user.name );
John alert( user.age );
```
- The value can be of any type. Let’s add a boolean one: `user.isAdmin = true;`
- To remove a property, we can use the `delete` operator:
```javascript
delete user.age;
```
- We can also use multiword property names, but then they must be quoted:
```javascript
let user = 
	{ name: "John",   
	age: 30,   
	"likes birds": true  
			// multiword property name must be quoted };
```
- The last property in the list may end with a comma:
```javascript
let user = {   name: "John",   age: 30,}
```

- That is called a “trailing” or “hanging” comma. Makes it easier to add/remove/move around properties, because all lines become alike.
##### Object literal
In JavaScript, an object literal is a syntax for creating objects directly using curly braces `{}`. It is a convenient way to define and initialize objects with their properties and values in a concise manner.

Here's an example of an object literal:

```javascript
const myObject = {
  property1: 'Value 1',
  property2: 42,
  property3: true,
  method: function() {
    console.log('Hello!');
  }
};
```

In this example, `myObject` is created using an object literal. It has several properties (`property1`, `property2`, `property3`) with corresponding values (`'Value 1'`, `42`, `true`), and a method `method` that outputs `'Hello!'` to the console.

Object literals allow you to define properties and their values in a key-value pair format, separated by colons (`:`). The properties can be any valid JavaScript identifiers or strings. The values can be any valid JavaScript expressions, including other objects, arrays, functions, etc.

Object literals are commonly used for creating simple data structures, configuration objects, or as a means of organizing related data and behavior within a single entity.

### Square brackets 
- For multiword properties, the dot access doesn’t work:- `user.likes birds = true;`
- here’s an alternative “square bracket notation” that works with any string:
```javascript
let user = {};  // set 
user["likes birds"] = true;  // get 
alert(user["likes birds"]); // true  
// delete 
delete user["likes birds"];
```

- Now everything is fine. Please note that the string inside the brackets is properly quoted (any type of quotes will do).

- Square brackets also provide a way to obtain the property name as the result of any expression – as opposed to a literal string – like from a variable as follows:
```javascript
let key = "likes birds";  // same as 
user["likes birds"] = true; 
user[key] = true;
```
### Computed properties
- We can use square brackets in an object literal, when creating an object. That’s called _computed properties_.
- For instance:
```javascript
let fruit = prompt("Which fruit to buy?", "apple");  
let bag = { 
[fruit]: 5, // the name of the property is taken from the variable fruit_ 
};  
alert( bag.apple ); // 5 if fruit="apple"
```

- The meaning of a computed property is simple: `[fruit]` means that the property name should be taken from `fruit`.

- So, if a visitor enters `"apple"`, `bag` will become `{apple: 5}`.

- Essentially, that works the same as:
```javascript
let fruit = prompt("Which fruit to buy?", "apple"); 
let bag = {};  // take property name from the fruit variable 
bag[fruit] = 5;
```
- …But looks nicer.
- We can use more complex expressions inside square brackets:`let fruit = 'apple'; let bag = {   [fruit + 'Computers']: 5 // bag.appleComputers = 5 };`
- Square brackets are much more powerful than dot notation. They allow any property names and variables. But they are also more cumbersome to write.
- So most of the time, when property names are known and simple, the dot is used. And if we need something more complex, then we switch to square brackets.

### Property value shorthand
- In real code, we often use existing variables as values for property names.For instance:
```javascript
function makeUser(name, age) 
{   return 
{     name: name,     
age: age,     // ...other properties   
}; }  
let user = makeUser("John", 30); 
alert(user.name); // John
```
- In the example above, properties have the same names as variables. The use-case of making a property from a variable is so common, that there’s a special _property value shorthand_ to make it shorter.
- Instead of `name:name` we can just write `name`, like this:
```javascript
function makeUser(name, age) 
{   return {     name, // same as name: name     
			age,  // same as age: age     // ...   
			}; }
```
- We can use both normal properties and shorthands in the same object:`let user = {   name,  // same as name:name   age: 30 };`
### Property instance test "in" operator
- A notable feature of objects in JavaScript, compared to many other languages, is that it’s possible to access any property. There will be no error if the property doesn’t exist!
- Reading a non-existing property just returns `undefined`. So we can easily test whether the property exists:
```javascript
let user = {};  
alert( user.noSuchProperty === undefined ); // true means "no such property"
```
- There’s also a special operator `"in"` for that.The syntax is:`"key" in object`
- For instance:
```javascript
let user = { name: "John", age: 30 };  
alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist

```
- Please note that on the left side of `in` there must be a _property name_. That’s usually a quoted string.

## Array manipulation on a website
- ![](../../statics/Pasted%20image%2020230619071824.png )
- here in this code , first we visited the https://en.wikipedia.org/wiki/Category:Boulevards_in_Paris
- then here the objective is to create a list with all element having De in them 
- to do this first we need to find the div name in which all these name are in it . which is mw-category 
- then we find all the `<a>` tags (remember it is used to create hyperlinks). you can see the queryselector is been applied on category (you can apply queryselector on an element also). now we convert the returned node list into array.
- now we need to read the text on each of these links 
- then on the result we apply filter()

## Event bubbling
Event bubbling is a mechanism in JavaScript where an event triggered on a specific element will also trigger the same event on all its parent elements, propagating up the DOM tree until it reaches the root element (usually the `document` object). This allows events to be handled at different levels of the DOM hierarchy.

Here's an example to illustrate event bubbling:

```html
<div id="parent">
  <div id="child">Click me!</div>
</div>
```

```javascript
const parentElement = document.getElementById('parent');
const childElement = document.getElementById('child');

parentElement.addEventListener('click', function(event) {
  console.log('Parent element clicked');
});

childElement.addEventListener('click', function(event) {
  console.log('Child element clicked');
});
```

In the above code, if you click on the "child" element, the event will trigger on the child element first. Then, due to event bubbling, the same event will propagate up to the parent element, triggering the event listener attached to it as well. Therefore, you will see both console log messages in the output:

```
Child element clicked
Parent element clicked
```

Event bubbling allows you to handle events at different levels in the DOM hierarchy without attaching event listeners to each individual element. It simplifies event handling and provides flexibility in managing event behavior throughout the document.

## Event capturing
Event capturing is another event handling mechanism in JavaScript that works in the opposite direction of event bubbling. With event capturing, the event is first captured by the outermost ancestor element and then propagates inward toward the target element.

To use event capturing, you can pass a third parameter to the `addEventListener` method as `true`. This parameter specifies that the event should be captured instead of following the default behavior of event bubbling.

Here's an example to illustrate event capturing:

```html
<div id="parent">
  <div id="child">Click me!</div>
</div>
```

```javascript
const parentElement = document.getElementById('parent');
const childElement = document.getElementById('child');

parentElement.addEventListener('click', function(event) {
  console.log('Parent element clicked');
}, true);

childElement.addEventListener('click', function(event) {
  console.log('Child element clicked');
}, true);
```

In this example, when you click on the "child" element, the event capturing phase triggers first on the parent element, and then on the child element. The event listeners specified with the `true` parameter capture the event during the capturing phase, resulting in the following console log output:

```
Parent element clicked
Child element clicked
```

Event capturing is less commonly used than event bubbling, but it can be useful in specific scenarios where you need to handle events in a particular order from outermost to innermost elements.
