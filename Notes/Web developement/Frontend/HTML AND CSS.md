# HTML
- Essentially it contains only tags and attributes
```
	<!DOCTYPE html> -- implicit indicator To let browser know you are using latest html version
	<html lang="en"> -- 'html' is a tag(they start and closed mostly , some like <br> need not be closed) , 'lang='en'' here is an attribute which change the behaviour of a tag
		<head> -- text on tab
			<title>
				hello,world
			</title>
		</head>
		<body>
			hello,body
		</body>
	</html>
```

## Document Object model

- The Document Object Model (DOM) is a programming interface that represents the structure of an HTML or XML document as a hierarchical tree-like structure. It provides a way for programs or scripts to access and manipulate the elements, attributes, and content of a web page.
- In a web application, when a web page is loaded in a browser, the browser parses the HTML or XML code and creates a DOM tree that represents the structure of the document. Each element in the document, such as headings, paragraphs, images, and forms, is represented by a corresponding node in the DOM tree. These nodes can be accessed and manipulated using scripting languages like JavaScript.
- The DOM tree has a hierarchical structure, with the root node representing the entire document and other nodes representing elements, attributes, and text content. Nodes are interconnected based on their parent-child relationships. For example, a `<div>` element may contain multiple `<p>` elements as its children, and those `<p>` elements may have text nodes as their children.
- The DOM provides various methods and properties to interact with the nodes in the tree. Using JavaScript, developers can traverse the DOM tree, access individual nodes, modify their attributes and content, create new nodes, and remove existing nodes. This allows developers to dynamically update and change the content and appearance of a web page in response to user interactions or other events.
- By using the DOM, developers can build interactive web applications that can respond to user input, update content dynamically, and create dynamic effects. It serves as a bridge between the web page's structure and its programming logic, enabling developers to create powerful and dynamic web experiences.![[DOM.png]]
- When working with the Document Object Model (DOM) in JavaScript, selectors are used to target specific nodes or elements within an HTML document. Selectors allow you to identify and manipulate elements based on their attributes, classes, IDs, or relationships to other elements. ^dcee8b
- CSS-style selectors are commonly used in JavaScript to target DOM elements. These selectors resemble the syntax used in CSS for styling web pages. Here are some examples of CSS-style selectors and their explanations:
	1. `div.display`: This selector targets `div` elements with the class name "display". It selects all `div` elements that have the class attribute set to "display".
	2. `.display`: This selector targets elements with the class name "display". It selects all elements that have the class attribute set to "display", regardless of the element type.
	3. `#container > .display`: This selector targets elements with the class name "display" that are direct children of an element with the ID "container". It selects elements that have the class attribute set to "display" and are immediate children of an element with the ID "container".
	4. `div#container > div.display`: This selector targets `div` elements with the class name "display" that are direct children of a `div` element with the ID "container". It selects `div` elements that have the class attribute set to "display" and are immediate children of a `div` element with the ID "container".
- In addition to CSS-style selectors, you can also use relational selectors or special properties owned by the nodes. These relational selectors allow you to target specific relationships between elements. Some common relational selectors include:
	- `firstElementChild`: Targets the first child element of a parent element.
	- `lastElementChild`: Targets the last child element of a parent element.
	- `nextElementSibling`: Targets the next sibling element following a given element.
	- `previousElementSibling`: Targets the previous sibling element preceding a given element.
- These relational selectors provide a way to navigate and target specific elements based on their relationships within the DOM tree.
- By combining CSS-style selectors and relational selectors, you can effectively target and manipulate specific elements in the DOM to perform various operations, such as updating content, applying styles, or attaching event listeners.
### Tags 

#### Video tag
```
 <!DOCTYPE html>

<!-- Demonstrates video -->

<html lang="en">
    <head>
        <title>video</title>
    </head>
    <body>
        <!-- https://www.harvard.edu/ -->
        <video autoplay loop muted playsinline width="1280">
            <source src="halloween.mp4" type="video/mp4">
        </video>
    </body>
</html>
```

#### Link
```
<a href="link here">Text</a>
```

#### Meta 
```
<meta name="viewport" content="initial-scale=1, width=device-width">
```
- This tag is used to make the content of web page more mobile friendly
- name="viewport" , here name (attribute of meta tag) refer to the feature of browser and viewport is the big rectangular region / body of the page
- content="initial-scale=1, initial scale =1 means that initially the web page should not be zoomed in or out but it should be at default
- width=device-width, show text proportional to the size of screen
- ![[meta.png]]


#### Form
```
<form action="https://www.google.com/search" method="get">
   <input autocomplete="off" autofocus placeholder="Query" name="q" type="search">
   <input type="submit" value="Google search">
</form>
```
- here the action attribute used to set on what url this form should be submitted
- `<form onsubmit='greet(); return false;>'`
- In the HTML code you provided, the `return false;` statement is used within the `onsubmit` attribute of a `<form>` element.
- The `onsubmit` attribute is an event handler that specifies the JavaScript code to be executed when the form is submitted. In this case, when the form is submitted, the `greet()` function will be called.
- The `return false;` statement is commonly used in event handlers to prevent the default behavior of the event from occurring. In the context of a form submission, the default behavior is to refresh the page or navigate to a new page.
- By including `return false;` at the end of the event handler code, it prevents the default behavior of the form submission from happening. This is often used when you want to handle the form submission using JavaScript and perform custom actions without reloading or navigating away from the current page.
- In summary, `return false;` in this context is used to prevent the form from being submitted in the default way and to allow the `greet()` function to handle the form submission using JavaScript code.
- `<form action="/greet" method="get">`
	- The HTML `<form>` element is used to create an interactive form on a web page. The `action` attribute specifies the URL or server-side script that will process the form data when the user submits it. In this case, the `action` attribute is set to `/greet`, which means that when the form is submitted, the form data will be sent to the server-side script or resource located at the `/greet` URL.
	- When a user submits the form, the browser sends an HTTP request to the server at the specified URL, along with the form data. The server-side script or resource at `/greet` will receive this request and process the form data accordingly. The exact behavior of the server-side script or resource will depend on how it is implemented.
	- For example, if the server-side script is written in a programming language like PHP or Python, it may process the form data, perform some actions, and generate a response that is sent back to the browser. The server-side script could use the form data to greet the user, perform a database query, or execute any other relevant functionality.
	- It's important to note that the `action` attribute is just one part of the `<form>` element, and there are other attributes and elements that can be used to define the structure and behavior of the form, such as `<input>` elements for form fields, `<label>` elements for field labels, and the `method` attribute to specify the HTTP method to be used when submitting the form (e.g., GET or POST)

#### Data attribute
- In HTML, a data attribute is an attribute that can be added to HTML elements to store custom data or information. It is used to provide additional information about an element that is not represented by standard HTML attributes.
- Data attributes are prefixed with "data-" followed by a descriptive name that you define. For example, if you want to store a custom piece of data called "price" for a product element, you can use the data attribute as follows:
```
<div data-price="49.99">Product Name</div>
```
- In this example, the "data-price" attribute is added to the `<div>` element, and its value is set to "49.99". The data attribute can store any string value.
- Data attributes can be accessed and manipulated using JavaScript. You can retrieve the value of a data attribute using the `getAttribute()` method, like this:
```
var price = document.querySelector('div').getAttribute('data-price');
console.log(price); // Output: 49.99
```
- Data attributes are commonly used to store additional information that can be used for scripting or styling purposes. They provide a way to associate custom data with HTML elements without affecting the standard attributes or semantics of the element.
#### Style 
- to add style to page 

#### Link files 
```
<link href="styles.css" rel="stylesheet">
```
- allow to import or include secondary files in the HTML 
- In the HTML `<link>` element, the `rel` attribute stands for "relationship" and specifies the relationship between the current document and the linked resource. It tells the browser how to interpret the linked resource.
- In the context of linking a CSS file, the `rel` attribute is set to "stylesheet" to indicate that the linked resource is a CSS file that should be used to style the current HTML document.

#### Div
- Meaning is division of a page , it is used to divide the page in rectangle boxes 
- It can be powerfull to make changes to large amount of data
```
<div style="text-align: center;">
	<div style="font-size: large;"> -- here header tag can be used
		Sahil jalandhara
	</div>
	<div style="font-size: medium;"> -- can use main tag
		Welcome
	</div>
	<div style="font-size: small;"> -- can use footer tag
		Jolly
	</div>
</div>
```
- Here the parent div used to apply style to all the divs
- more effective way [[#Separating CSS and HTML]]

### Select 
```
<select name="sport">
            <option disabled selected>Sport</option>
            <option value="Basketball">Basketball</option>
            <option value="Soccer">Socerr</option>
            <option value="Badminton">Badminton</option>
</select>
```
- it generate a drop down box and option tag is used to define each option in that drop box
- const selectedSort = sortingSelect.options[e.selectedIndex].text; javascript to read value of selected option
```
{% for sport in sports %}
            <option value="{{ sport }}">{{ sport }}</option>
{% endfor %}
```
- You can also use for loop here , sports is the name of list 

### Input 
- `<input type = 'text' name = 'full_name'>`
- here name (RHS) represent the name we can use to later reference this input form
- `<input type="hidden">`:
	- The `<input type="hidden">` element is used to create an input field in an HTML form that is not visible to the user.
	- It is typically used to store data that needs to be passed along with the form submission but does not need to be displayed or edited by the user.
	- The value of a hidden input field is not visible on the page and remains hidden from the user's view.
	- Hidden fields are commonly used to transmit additional information or metadata related to the form submission, such as session tokens, identifiers, or other data that the server-side processing script may require
	- ![[Pasted image 20230612075659.png]]
	- ![[Pasted image 20230612075750.png]]
	- 

### Data attributes
[Using data attributes - Learn web development | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

## HTML attribute reference
- https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes
# CSS
- Cascading style sheets 
- Here cascading means if we attributes properties to the parent or grandparents it will cascade down to the child elements

## Properties
- terminology for key ,value pairs 
- it is same as attributes in HTML
- `<h1 style="color: blue; text-align: center;">`  it is example of **inline styling**
- we dont need to apply same css to every element , applying a css to parent tag result in change in child element . means add the above in body tag  and it gets applied to whole body
- Alternative is using this [[#Separating CSS and HTML]] 


## Separating CSS and HTML 
```
<head>
	<style>
	   body {
	     text-aling: center;
	   }
	   header {
	      font-siz: large;
	   }
		main {
		   font-siz: medium;
		}
		footer {
		    font-size: small;
		    font-weight: bold;
		}
		-- alternate --
		main,footer {
		}
	</style>
</head>
```
- Using style tag to separate the CSS
- in above case [[#Type selector]] is used because here the type of tag is used to apply style
- link tag can also be used here  [[#Link files]]

![[css selector.png]]
### Type selector 
- type selector is a selector that targets HTML elements based on their element type or tag name. It is the most basic and commonly used selector in CSS. The type selector matches all elements of a specific type on a web page and applies the specified styles to them.
- The syntax for a type selector is simply the name of the HTML element. For example, to target all `<h1>` elements on a page, you would use the type selector `h1`. Here's an example of a type selector in CSS: `h1 {   color: blue;   font-size: 24px; }` In the above CSS code, the type selector `h1` is used to target all `<h1>` elements. The styles defined within the curly braces will be applied to all `<h1>` elements on the page. In this case, the text color will be set to blue and the font size to 24 pixels.
- Type selectors can also be combined with other selectors to target elements in a more specific manner. For example, you can use a combination of a type selector and a class selector to target specific elements with a particular class. Here's an example:
- `h1.title {   color: red; }`
- In the above CSS code, the selector `h1.title` targets only `<h1>` elements that also have the class "title". The specified style (in this case, changing the text color to red) will only be applied to those elements that match both the `<h1>` type and the "title" class.
- Type selectors are very versatile and can be used to target any HTML element on a page. They are fundamental to defining the overall styling and appearance of a web page.

### ID Selector (it needs to be different for ever element)
- In web development, an ID selector is a way to target and apply styles or manipulate specific elements on a webpage using their unique identifier. It is denoted by a hash symbol (#) followed by the ID value.
- The ID attribute is used to uniquely identify elements within an HTML document. Each ID must be unique, meaning no two elements should have the same ID value within a single document.
- To create an ID selector, you assign an ID value to an HTML element using the `id` attribute. For example:html code`<div id="myElement">This is a div element.</div>`
- In the example above, the `myElement` ID is assigned to the `<div>` element.
- To apply styles or manipulate the element with a specific ID, you can use the ID selector in CSS or JavaScript. Here are examples in both languages:
	- CSS example:css code`#myElement {   color: red; }`
		- In this CSS rule, the element with the ID "myElement" will have a red text color.
	- JavaScript example:`var element = document.getElementById("myElement"); element.style.color = "red";`
		- In this JavaScript code, the `getElementById()` method is used to retrieve the element with the ID "myElement", and the `style` property is used to modify its CSS properties. In this case, the color of the element's text is set to red.
- Using ID selectors provides a way to uniquely target and style or manipulate specific elements within an HTML document.

### Class selector (multiple element can be identified using same class)
- In CSS (Cascading Style Sheets), a class selector is a way to target and apply styles to specific elements on a webpage. It is denoted by a period (.) followed by the class name.
- To create a class selector, you assign a class name to one or more HTML elements using the `class` attribute. For example:
- `<p class="highlight">This is a paragraph.</p>`
- In the example above, the `highlight` class is assigned to the `<p>` element.
- To apply styles to elements with a specific class, you define rules in your CSS using the class selector. Here's an example:
```.highlight {   color: red;   font-weight: bold; }```
- In this CSS rule, any element with the class "highlight" will have a red text color and bold font weight.
- Multiple elements on a webpage can share the same class, allowing you to apply the same styles to different elements. For example:
- ```<p class="highlight">This is a paragraph.</p> <p>This is another paragraph.</p> <p class="highlight">This is a third paragraph.</p>```
- In this case, the first and third `<p>` elements will be styled according to the rules defined for the "highlight" class in the CSS.
- Using class selectors provides a flexible way to target specific elements and apply consistent styles across multiple parts of a webpage
```
<!DOCTYPE html>
<html lang="en">
<head>
	<style>
		.center {
			text-align: center;
		}
		.large {
			font-size: large;
		}
	</style>
</head>
<body>
	<p class="center">Hello there</p>
	<p class="large">Or bhai suna they</p>
</body>
</html>
```

### Frameworks
- You can use <link herf , to link bootstrap to HTML

## Layouts

### Flex container
- Imagine you have a bunch of toys that you want to organize on a shelf. The shelf is like a container, and the toys are like the items inside the container.
- Now, let's say you want to arrange the toys in a certain way. Maybe you want them to be in a line, or maybe you want them to be stacked on top of each other. That's where the concept of a flex container comes in.
- A flex container is like a special shelf that helps you organize and arrange your toys (or any other elements) on a webpage. It's like a magical container that you can make things inside it do special tricks!
- When you turn a regular shelf into a flex container, you can tell the toys (or items) inside it how to line up, how much space they should take, and how they should behave when there's not enough room.
- For example, you can tell the toys to stand in a line horizontally, one next to the other, or you can tell them to stack vertically on top of each other. You can even tell them to grow or shrink to take up more or less space on the shelf.
- By using a flex container, you have more control over how the toys (or items) are arranged and how they behave, making it easier to create neat and organized layouts on a webpage.
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>
            hello
        </title>
        <style>
            #container {
                display: flex;  -- used to declare flex box
                flex-wrap: wrap;
            }
            #container > div {          <!-- > is used to references the children of #container -->
                background-color: green;
                font-size: 20px;
                margin: 20px;   -- add margin outside the container
                padding: 20px;   -- add margin inside a container
                width: 200px;
            }
        </style>
    </head>
    <body>
        <div id="container">
            <div>1 this is to test flex box</div>
            <div>2 this is to test flex box</div>
            <div>3 this is to test flex box</div>
            <div>4 this is to test flex box</div>
            <div>5 this is to test flex box</div>
            <div>6 this is to test flex box</div>
            <div>7 this is to test flex box</div>
            <div>8 this is to test flex box</div>
        </div>
    </body>
</html>
```
### Grid system
- CSS Grid layout is a way to organize and arrange things on a website. It's like having a grid or a table where you can place different elements, like pictures or text, in specific areas.
- Imagine you have a piece of paper divided into rows and columns, just like a grid. Each square in the grid is a place where you can put something. In CSS Grid, you can create a similar grid on a webpage.
- To start, you need to tell your webpage that you want to use a grid layout. You can do this by adding some special CSS code. It's like telling the computer that you want to use a grid.
- Once you have the grid set up, you can decide how many rows and columns you want. You can say, "I want 3 rows and 4 columns," or you can have more or less depending on what you need. Each row and column will be like a little box where you can put things.
- After setting up the rows and columns, you can place your elements in the grid. Let's say you want to put a picture in the top-left corner. You can say, "Put this picture in the first row and the first column of the grid." Then, you can put text in the second row and the third column, and so on.
- You can also control how big each element is. You can make a picture take up one box in the grid, or maybe two boxes. It's like resizing things to fit into the grid.
- The cool thing about CSS Grid is that you can easily move things around. Let's say you want to move the picture from the top-left corner to the bottom-right corner. You can simply change the numbers that say where the picture should go, and the picture will move to the new spot on the grid.
- CSS Grid gives you a lot of flexibility in arranging things on a webpage. You can create different layouts and designs by changing the rows, columns, and positions of the elements on the grid. It's like playing with a puzzle where you can place things wherever you want to make your webpage look just the way you like it!
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>My Web Page!</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
            .grid {
                background-color: green;
                display: grid;
                padding: 20px;
                column-gap: 20px;
                row-gap: 10px;
                grid-template-columns: 200px 200px auto;
            }
            .grid-item {
                background-color: white;
                font-size: 20px;
                padding: 20px;
                text-align: center;
            }
        </style>
    </head>
    <body>
        <div class="grid">
            <div class="grid-item">1</div>
            <div class="grid-item">2</div>
            <div class="grid-item">3</div>
            <div class="grid-item">4</div>
            <div class="grid-item">5</div>
            <div class="grid-item">6</div>
            <div class="grid-item">7</div>
            <div class="grid-item">8</div>
            <div class="grid-item">9</div>
            <div class="grid-item">10</div>
            <div class="grid-item">11</div>
            <div class="grid-item">12</div>
        </div>
    </body>
</html>
```


## Responsive design
```
<style>
  @media (min-width: 600px) {
     body{
      background-color: red;
      }
  }
  @media (max-width: 599px) {
     body{
      background-color: blue;
      }
  }
```
- media queries ensure how your web page going to look depending upon the size of web page being rendered

## Animation 
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>
            animate
        </title>
        <style>
            @keyframes move {
                0% {
                    left: 0%;
                }
                50% {
                    left: 50%;
                }
                100% {
                    left: 0%;
                }
            }
            h1 {
                position: relative;
                animation-name: move;
                animation-duration: 2s;
                animation-fill-mode: forwards;
                animation-iteration-count: infinite;
            }
        </style>
    </head>
    <script>
        document.addEventListener('DOMContentLoaded', function(){
            const h1 = document.querySelector('h1')
            h1.style.animationPlayState = 'paused';
            document.querySelector('button').onclick = () =>{
                if(h1.style.animationPlayState === 'paused'){
                    h1.style.animationPlayState = 'running';
                } else {
                    h1.style.animationPlayState = 'paused';
                }
            }
        });
    </script>
    <body>
        <button>Click here</button>
        <h1>Welcome!</h1>
    </body>
</html>
```


