### Adding JS in HTML
- `<script src="hello.js"></script> `

## Syntax
- conditionals `if (x < y) { } else { }`
- variables :- `let variable = 0;` , var is also used here
- When the name contains multiple words,  is commonly used. That is: words go one after another, each word except first starting with a capital letter: `myVeryLongName`.
- querySelecterAll :- gives list of all the element mentioned in parameters 
- loops :- `for (let i = 0 ; i < number ; i++){ }`
- Triple equals ( === ) **will do the same comparison as double equals (including the special handling for NaN , -0 , and +0 ) but without type conversion; if the types differ, false is returned**.
- 
- use can also use `=>` in JS to avoid writing function text again for example 
```
instead of 
document.querySelector('h1').addEventListner('click', function(){

});

you can use 
document.querySelector('h1').addEventListner('click', () => {

});

left side of arrow is the input function takes
```
- console.log is helpful to print values of variable in inspect function , console
- you can use `this.value` here this seek the value of the element that is been changed
- Imagine you have a room full of toys, and each toy has a different color. You want to find a specific toy based on its color.
	- `querySelector` is like looking for one specific toy in the room. You can ask for a toy using its color, and it will give you the first toy it finds with that color. If there are multiple toys with the same color, it will give you the first one it sees.
	- `querySelectorAll` is like looking for all the toys with a specific color in the room. It will give you a list of all the toys it finds with that color. If there are multiple toys with the same color, it will give you all of them.
		- It’s important to note that when using querySelectorAll, the return value is **not** an array. It looks like an array, and it somewhat acts like an array, but it’s really a “nodelist”. The big distinction is that several array methods are missing from nodelists. One solution, if problems arise, is to convert the nodelist into an array. You can do this with Array.from() or the spread operator.
	- So, if you use `querySelector`, you will get only one result (the first toy with the specified color), and if you use `querySelectorAll`, you will get multiple results (a list of all the toys with the specified color).
	- In programming, `querySelector` and `querySelectorAll` are used to find HTML elements on a webpage. Instead of colors, we use things like element names, classes, or IDs to find specific elements.
- The `addEventListener()` method is a way to tell a computer program to do something when a particular event happens. An event could be things like a button being clicked, a key on the keyboard being pressed, or the mouse moving.
	- Here's how it works:
		- Imagine you have a button on a webpage, and you want something to happen when that button is clicked. You can use the `addEventListener()` method to set up that action.
		- You provide two things to the `addEventListener()` method:
			- The type of event you want to listen for, like "click" for a button click event.
			- The function or object that you want to be called or executed when that event occurs.
		- When the event happens (in this case, when the button is clicked), the function or object you provided will be called or executed. It's like giving instructions to the computer program on what it should do when the event occurs.
		- If you use the `addEventListener()` method multiple times for the same event and provide the same function or object, it won't be added again to the list of event listeners. This is to make sure that the function or object is not accidentally triggered multiple times for the same event
- In JavaScript, you can call a function with or without parentheses, depending on whether you want to invoke the function and execute its code immediately or if you want to refer to the function itself.
	- this paradigm can be called functional programming 
	- passing function as values to a variable 
	- 
	- Calling a function with parentheses: When you call a function with parentheses, you invoke the function and execute its code. You pass any necessary arguments within the parentheses. Example:
	- Calling a function without parentheses: When you call a function without parentheses, you are referring to the function itself rather than executing its code. This is useful when you want to pass the function as a reference or assign it to a variable for later execution.Example:
```
function sayHello(name) 
{console.log('Hello, ' + name + '!');}
var helloFunc = sayHello; // Assign the sayHello function to the helloFunc variable 
helloFunc('Alice'); // Call the helloFunc
variable (which contains the function) with parentheses to
```
invoke it
Note that if you call a function without parentheses but try to use it as if it were a function (e.g., accessing its properties or trying to pass arguments), it won't execute as expected.
`const variable = ---` to ensure the value of variable not change

## Constant
- Being a “constant” just means that a variable’s value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are _calculated_ in run-time, during the execution, but do not change after their initial assignment.
- For instance:`const pageLoadTime = /* time taken by a webpage to load */;`
- The value of `pageLoadTime` is not known prior to the page load, so it’s named normally. But it’s still a constant because it doesn’t change after assignment.
- In other words, capital-named constants are only used as aliases for “hard-coded” values.

## Role in DOM manipulations 
- it can add , remove, change element in DOM 
- [[HTML AND CSS#^dcee8b]]

## It is client side 

## Greet
- In JavaScript we can listen to various type of events like 
- ![[events.png]]
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>
            function greet()
            {
                let name = document.querySelector('#name').value;
                alert('hello, '+ name);
            }
        </script>
       <title>Hello</title>
    </head>
    <body>
        <form onsubmit="greet(); return false;">
            <input autocomplete="off" autofocus id="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>
    </body>
</html>
```
- script tag is used to add some javascript code in the html file 
- 'function' word is used to define a custom function in JS. 
- `<form>` tag explained [[HTML AND CSS#Form]] 
- Understanding ID through [[HTML AND CSS#ID Selector]]
- 
- `alter()` In JavaScript, the `alert()` function is a built-in function that displays a modal dialog box with a message to the user. It is commonly used for displaying simple informational messages or alerts to the user in a web browser.
	- The `alert()` function is a blocking function, which means that it pauses the execution of the JavaScript code until the user closes the dialog box by clicking the OK button. This can be useful for getting the user's attention or providing immediate feedback.
	- However, it's worth noting that the use of `alert()` for general-purpose messaging is considered somewhat obtrusive and can disrupt the user experience. For more advanced and customizable dialog boxes, developers often use alternative methods such as modal windows or custom user interface components
- breakdown of the code `let name = document.querySelector('#name').value;`:
	- `document` refers to the Document object, which represents the HTML document loaded in the browser.
	- `querySelector('#name')` is a method of the Document object that allows you to select an element from the document using a CSS selector. [[HTML AND CSS#ID Selector]] In this case, `#name` is the selector, which targets an element with the ID attribute equal to "name".
	- `.value` is a property of an input element that represents the current value entered by the user.
	- Putting it all together, `document.querySelector('#name').value` selects an input element with the ID "name" and retrieves the value that the user has entered into that input field
### Learning features through code

#### 1
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>            document.querySelector('form').addEventListener('submit', function(event){
                let name = document.querySelector('#name').value;
                alert('Hello, ' + name);
                event.preventDefault();
            });
        </script>
       <title>Hello</title>
    </head>
    <body>
        <form>
            <input autocomplete="off" autofocus id="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>
    </body>
</html>
```
- here `addEventListener` is listening the event in form tag , event of submit . thereafter applying the `function(event)` (Note :- In JS we need not name the custom function , also here this function taking event as argument which is called)
- `event.preventDefault` ensure that default behaviour of the event is avoided (which in this case would have been reloading the page)
- Important thing to note that heirarchy of code matter , this code is not valid because the form tag is below the JS code so it wont get executed
- To tackle this issue we can use `.addEventListner('DOMContentLoaded' , function(){ -- adding the above code under script tag here});`
	- here when the whole DOM is loaded the function is getting executed

#### 2
```
document.addEventListener('DOMContentLoaded', function(){
    let input = document.querySelector('input');
    input.addEventListener('keyup' , function(event){
        let name = document.querySelector('p');
        if (input.value)
        {
            name.innerHTML = `hello , ${input.value}`; -- notice that all of the string in convered by ``
        }
        else
        {
            name.innerHTML = 'hello , Whoever is there';
        }
    });
});
```
- Using `${---}` to put a value . also cover the whole string with ``instead of '' , ""

### 3
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>
            hello
        </title>
        <script>
            document.addEventListener('DOMContentLoaded', function(){
                document.querySelectorAll('button').forEach(function(button){
                    button.onclick = function(){                       document.querySelector('#color_change').style.color = button.dataset.color;
                    }      
                });
            });
        </script>
    </head>
    <body>
        <h1 id="color_change">Hello</h1>
        <button data-color="red">Red</button>
        <button data-color="green">green</button>
        <button data-color="blue">blue</button>
    </body>
</html>
```
- here button.dataset helps in getting the data value of element 

### 4
```
setInterval(count, 1000); -- here count function will get executed ever 1000ms
```

## local storage
- `local.storage.getItem(key)`
- `local.storage.setItem(key, value)`
- You can access this local storage , by going to inspect -> application -> local storage
- Using JS to store data in the user browser and then retriving it in later visit to refer
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>
            hello
        </title>
        <script>
            if(!localStorage.getItem('count')){
                localStorage.setItem('count', 0);
            }
            function counter(){
                let count = localStorage.getItem('count');
                count++;
                document.querySelector('h1').innerHTML = count;
                localStorage.setItem('count',count);
            }
            document.addEventListener('DOMContentLoaded', function(){
                document.querySelector('h1').innerHTML = localStorage.getItem('count');
                document.querySelector('button').onclick = counter;
            });
        </script>
    </head>
    <body>
        <h1>0</h1>
        <button>Submit</button>
    </body>
</html>
```
## Console 
- on inspect function to check javascript error 
- you can also write JS code on console
- console.log is helpful to print values of variable in inspect function , console

## Data attribute
[Using data attributes - Learn web development | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

## 5 (can take inspiration for making single page application using flask, by looking at showpage function. like api we can use fetch to fetch data from our server instead of loading whole html of 3 pages at once )
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>single page</title>
        <style>
            div {
                display: none;
            }
        </style>
        <script>
            function showpage(page){
                document.querySelectorAll('div').forEach(div => {
                    div.style.display = 'none';
                });
         document.querySelector(`#${page}`).style.display = 'block';
            }
          document.addEventListener('DOMContentLoaded', function() {
            document.querySelectorAll('button').forEach(button => {
                    button.onclick = function() {
                        showpage(this.dataset.page);  --- t`this`is used to listen to closed event here it is one line above
                    }
                });
            });
        </script>
    </head>
    <body>
        <button data-page="page1">Page 1</button>
        <button data-page="page2">Page 2</button>
        <button data-page="page3">Page 3</button>
        <div id="page1">
             <h1>This is page 1</h1>
        </div>
        <div id="page2">
            <h1>This is page 2</h1>
        </div>
        <div id="page3">
            <h1>This is page 3</h1>
        </div>
    </body>
</html>
```

## History API
- The JavaScript History API is like a tool that helps us keep track of the pages we visit on a website and allows us to go back and forth between those pages.
- Imagine you are reading a book and you want to remember the pages you have already read. The History API works similarly but for web pages. It keeps a record of the pages you have visited in your web browser.
- With the History API, we can do a few things:
	1. We can add a new page to the history record: Just like putting a bookmark in your book, we can add a new entry to the browser's history. This allows us to go back to that page later.
	2. We can change the current page's URL: It's like changing the page number in your book. The API lets us change the URL of the current page, so it looks like we are on a different page, but without actually loading a new page.
	3. We can go back to the previous page: Just like turning back a few pages in your book, the History API lets us go back to the page we visited before the current one. It's like clicking the back button on the web browser.
	4. We can go forward to the next page: Similar to moving forward a few pages in your book, we can use the API to go to the next page in the history if we have gone back earlier. It's like clicking the forward button on the web browser.
	5. We can go to a specific page in the history: Imagine if you had a bookmark for a particular page in your book. The History API lets us go directly to a specific page in our browsing history without going back or forward multiple times.
- Overall, the History API helps us navigate through the pages we have visited on a website, just like bookmarks help us find the pages we want to read in a book. It allows us to create more interactive and dynamic web experiences.
- without clicking any link or loading the page , but you are changing what is written. you are adding the entry in history array 
- The JavaScript History API provides methods and properties to interact with the browser's history. It allows you to manipulate the browser's URL, navigate between different states, and handle navigation events.
- The main component of the History API is the `window.history` object, which provides access to the user's session history. Here are some important methods and properties provided by the History API:
	1. **`history.pushState(state, title(ignored by most browser,so put "" here), URL)`**: This method adds a new entry to the history stack and changes the URL of the current page. It takes three parameters: `state` (an object representing the state associated with the new history entry), `title` (the new title for the page), and `URL` (the new URL for the page).
	2. **`history.replaceState(state, title, URL)`**: This method modifies the current entry in the history stack without adding a new one. It works similar to `pushState()` but replaces the current URL instead of adding a new entry.
	3. **`history.back()`**: This method moves the browser back to the previous page in the history stack. It is equivalent to the user clicking the browser's back button.
	4. **`history.forward()`**: This method moves the browser forward to the next page in the history stack. It is equivalent to the user clicking the browser's forward button.
	5. **`history.go(delta)`**: This method allows you to navigate to a specific position in the history stack relative to the current page. The `delta` parameter specifies the number of steps to move (positive or negative) in the stack. For example, `history.go(-2)` will move back two pages.
	6. **`history.length`**: This property returns the number of entries in the history stack    
- Additionally, the History API provides an event called `popstate`, which is triggered when the user navigates through the history using the back or forward buttons. You can listen for this event using the `window.addEventListener()` method to perform actions when the state changes.
- The History API is commonly used in modern web applications that utilize client-side routing, where the URL changes dynamically without a full page reload. It enables you to create more interactive and responsive web experiences by managing the browser history and updating the content accordingly.
```
 window.onpopstate = function(event) {
                console.log(event.state.section);
                showsection(event.state.section);
            }
            function showsection(section){
                fetch(`section/${section}`)
                .then(response => response.text())
                .then(text =>{
              document.querySelector('#content').innerHTML = text;
                });
            }
```
- here window.onpopstate is providing user functionality to go back to previosuly visited webpage using browsing history
- window object
	- how is it different from document object :- document is every thing on a single page , whereas window is what is visible on screen without scrolling
	- ![[www.png]]
	- ![[scrol.png]]
	- ![[daa.png]]
	- document.body.offsetHeight means total height
	- window.innerWidth also available
	- ![[master.png]]
	- ` window.onscroll = () =>{ }` to apply these things

# React
- Imperative programming:- Imperative programming is a programming paradigm where programs are structured around a sequence of statements that explicitly define how to perform computations and modify the program state. In imperative programming, the focus is on specifying the step-by-step instructions or commands to be executed by the computer
- ![[imperative.png]]
- React is a declarative programming:- 
- ![[dec.png]]
- react allow to divide application into components 
- include React , ReactDOM , Babel(translate code from jsx to JS)
