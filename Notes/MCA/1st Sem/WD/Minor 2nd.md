## Html and media type
### Audio support in browser
- MIDI Format:- (Musical Instrument Digital Interface) is a format for sending music information between electronic music devices like synthesizers and PC sound cards.MIDI files do not contain sampled sound, but a set of digital musical instructions (musical notes) that can be interpreted by your PC's sound card.
- RealAudio Format:- format also supports video. The format allows streaming of audio (on-line music, Internet radio) with low bandwidths. Because of the low bandwidth priority, quality is often reduced. Sounds stored in the RealAudio format have the extension .rm or .ram.
- AU Format:- 
- AIFF format:- AIFF (Audio Interchange File Format) was developed by Apple. AIFF files are not cross-platform and the format is not supported by all web browsers. Sounds stored in the AIFF format have the extension .aif or .aiff.
- WAVE Format:- supported by all computers running Windows, and by all the most popular web browsers. Sounds stored in the WAVE format have the extension .wav.
- MP3 Format (MPEG):- MP3 files are actually MPEG files. But the MPEG format was originally developed for video by the Moving Pictures Experts Group. We can say that MP3 files are the sound part of the MPEG video format. MP3 is one of the most popular sound formats for music recording. The MP3 encoding system combines good compression (small files) with high quality
- Which one to choose :- b/w wave and mp3 
### Video support in browser
- AVI Format:- AVI (Audio Video Interleave) format was developed by Microsoft. The AVI format is supported by all computers running Windows, and by all the most popular web browsers. It is a very common format on the Internet, but not always possible to play on non-Windows computers
- Window Media Format:- Windows Media is a common format on the Internet, but Windows Media movies cannot be played on non-Windows computer without an extra (free) component installed.
- MPEG:- MPEG (Moving Pictures Expert Group) format is the most popular format on the Internet. It is cross-platform, and supported by all the most popular web browsers.Videos stored in the MPEG format have the extension .mpg or .mpeg.
- RealVideo Format : -
### Other binary format supported 
- PDF:- "PDF" stands for "Portable Document Format". The key word is portable, intended to combine the qualities of authenticity, reliability and ease of use together into a single packaged concept.

## Style Sheets
### What is it 
- STYLE SHEET IS A COLLECTION OF FORMATTING STYLES, WHICH CAN BE APPLIED TO A WEB PAGE.
### Separation of style and content has many benefits 
- Speed:- ‘Overall’ as the first page will probably load more slowly because the style sheet AND the content will need to be transferred. Subsequent pages will load faster because no style information will need to be downloaded – the CSS file will already be in the browser's cache.
- Maintainability:- Holding all the presentation styles in one file significantly reduces maintenance time, and reduces opportunity for human errors by reducing the maintenance tasks.
- Accessibility:- Sites that use CSS with either XHTML or HTML are easier to draw so that they appear extremely similar in different browsers
- Customization:- If a page's layout information is all stored externally, a user can decide to disable the layout information entirely, leaving the site's bare content still in a readable form. Site authors may also offer multiple stylesheets
- Consistency
- Portability
### -ves
- Lack of semantic vocabulary. HTML offers a rich, but limited vocabulary of
semantic elements (for example paragraph, quote, emphasis). The migration of HTML to
the extensible XHTML may eventually speed the proliferation of richer semantic
vocabularies to apply generalized styles to
- Complex Layouts. One of the practical problems is the lack of proper support for style
languages in major browsers.
- Most of the major web development tools still embrace a mixed presentation-content
model. So authors and designers looking for GUI based tools for their work find it difficult
to follow the semantic web method
### Style rules
A STYLE RULE IS A SET OF HTML TAGS SPECIFYING THE FORMATTING
ELEMENTS.

**A style rule can basically be split into two parts:**
- (a) Selector: A selector is a string that identifies what elements the corresponding rule
applies to and is the first part of the rule.
- (b) Declaration: This part of the rule is enclosed within curly brackets. A declaration
has two sections separated by a colon. The section before the colon tells the
property, and the section after the colon is the value of that property.

The syntax of a style rule is as follows:
Selector (property : value)
Where,
Selector = Any HTML tag
Property = Attribute like font color, font size, etc.
Value = Setting for the attribute
e.g. H1 { color : blue }

#### Ways of incorporating CSS
There are four ways of incorporating style sheets in HTML document, which are:
➢ Inline Style Sheet
➢ Internal style sheet
➢ Linking to an external style sheet
➢ Importing a style sheet
1. Inline:- applied to individual elements in the web page, Inline styles are implemented by using style attributes with the HTML tags.
```html
The syntax is :
<HTML TAG STYLE = “PROPERTY : VALUE”>
e.g.
<P STYLE = { COLOR : OLIVE }>
```
2. Internal:- More than one style rule can be grouped by using `<STYLE>..........</STYLE>` tag pair unlike of applying it individually in inline style. Each of these tags when used in the BODY of the HTML code will apply the style rules.
```html
<HTML>
<HEAD>
<STYLE>
Style Rules
</STYLE>
</HEAD>
</HTML>
<BODY>
............
............
............
</BODY>
</HTML>
```
**SELECTORS**
A SIMPLE SELECTOR DESCRIBES AN ELEMENT IRRESPECTIVE OF ITS POSITION IN THE DOCUMENT STRUCTURE. The H1 heading identifier is a typical example of simple selector.
1. HTML selector :- These selectors use the names of HTML elements without brackets. So the HTML `<P>` tag becomes P.
2. Class selector
3. ID selector 
4. Contextual selector 
Consider a situation where, some tags are under H1 that are italics. Now to change any of
their color to red following code could be used:
```
H1 { color : red }
I { color : red }
```
But in the above code, all type italicized tags turn to red. This is because of the line 2 of the
code.
To avoid such situation contextual selectors can be used. Contextual selectors can be used
to combine number of simple selector separated by a space.
The above code now can be rewritten as:
```
H1 I { COLOR : RED }
```

3. CSS:- The above methods of modifying styles of elements are within the same page. To apply similar settings for all the pages in the website, all the style rules should be put into a style sheet File and then imported or linked with the HTML document. This method of linking or importing is called CASCADING STYLE SHEETS (CSS).
- Linking to external file:- 
For constructing a CSS, first style rules must be written in a document and saves in a
separate file with extension of CSS. The syntax for linking to an external style sheet is:
```html
<HTML>
<HEAD>
<LINK REL = “STYLESHEET“ HREF = “Dictionary path where the style sheet is saved”>
</HEAD>
<BODY>
.........
.........
</BODY>
</HTML>
```
Where REL = STYLESHEET – Relation to the external document in a style sheet.

- Importing a style sheet:- Importing a style sheet, automatically pulls, the style rules into the document for use. Once imported, changes made to the style sheet will not be reflected in the web page into which it has been imported

### CSS basic interactivity
#### Statements 
In CSS, a stylesheet is composed of a list of statements, and each statement is either an at-rule or a rule set. Let's break down the components and concepts involved in this example:

1. **At-Rules**: An at-rule is an instruction or directive to the CSS parser. It begins with an at-keyword, which is denoted by the "@" character followed by an identifier (e.g., `@import`, `@media`, `@keyframes`). At-rules can serve various purposes, such as importing external stylesheets, defining media queries, or specifying keyframe animations.

   In your example, there is an `@import` at-rule, which is used to import an external CSS file named "base.css." This at-rule is terminated by a semicolon (;) at the end of the statement.

   Example:
   ```css
   @import url(base.css);
   ```

2. **Rule Sets**: A rule set is a set of CSS declarations that define how elements with a specific selector should be styled. It consists of a selector followed by a block of declarations enclosed in curly braces. The selector (`h2` in this case) defines which HTML elements should be affected by the declarations.

   In your example, there is a rule set that targets `<h2>` elements and specifies the color and font-weight of those elements. The declarations are enclosed within curly braces.

   Example:
   ```css
   h2 {
       color: #666;
       font-weight: bold;
   }
   ```

3. **Delimiters**: In CSS, different delimiters are used to specify the beginning and end of various constructs. For at-rules, the statement is typically terminated by a semicolon (;), while rule sets are enclosed within curly braces ({}). This helps the CSS parser understand the structure of the stylesheet.

   - The `@import` at-rule ends with a semicolon, indicating the completion of the directive.
   - The rule set for `h2` has its declarations enclosed in curly braces, indicating that these styles apply to `<h2>` elements.

4. **Matching Pairs**: CSS syntax requires that certain characters appear in matching pairs. This includes parentheses, brackets, braces, and quotes. For example, if you open a curly brace or parentheses, you must close it to maintain a valid CSS syntax. Quotes, whether single or double, also need to appear in matching pairs.

   - Parentheses: `()` must be used in matching pairs when necessary (e.g., in function calls or property values).
   - Brackets: `[]` are used for attribute selectors.
   - Curly Braces: `{}` are used to define the block of declarations in rule sets and at-rules.
   - Quotes: Single (' ') or double (" ") quotes are used to enclose strings or URLs.

In summary, your example illustrates the use of at-rules and rule sets in CSS, and it highlights the importance of proper delimiters and matching pairs for characters like parentheses, brackets, braces, and quotes to maintain a valid CSS stylesheet.
#### Selector
#### Declaration blocks
Declaration blocks begin with a left curly brace, {, and end with a right curly brace, }. They
contain zero or more declarations separated by semicolons:
```css
h2 {
color: #666;
}
```
#### CSS comments
In CSS, a comment starts with /`*` and ends with `*`/. Comments can span multiple lines, but
may not be nested:

### Positioning in CSS
In CSS, positioning refers to the way you control the placement and layout of elements on a web page. There are several positioning properties you can use to control the positioning of elements. Here's an explanation of the commonly used positioning values:

1. **Static Positioning**:
   - Default positioning for all HTML elements.
   - Elements are placed in the normal flow of the document, and their position is not affected by the top, right, bottom, or left properties.
   - You typically don't need to specify `position: static` as it's the default.

   Example:
   ```css
   .element {
       position: static;
   }
   ```

2. **Relative Positioning**:
   - An element with `position: relative` is positioned relative to its normal position in the document flow.
   - You can use the `top`, `right`, `bottom`, and `left` properties to shift the element from its original position.
   - Other elements on the page will not be affected by the space created by the relatively positioned element.

   Example:
   ```css
   .element {
       position: relative;
       top: 20px;
       left: 30px;
   }
   ```

3. **Absolute Positioning**:
   - An element with `position: absolute` is positioned relative to its closest positioned ancestor, which means it's taken out of the normal document flow.
   - If no ancestor is positioned, it's positioned relative to the initial containing block (usually the viewport).
   - You can use the `top`, `right`, `bottom`, and `left` properties to specify the element's exact position.

   Example:
   ```css
   .element {
       position: absolute;
       top: 50px;
       right: 0;
   }
   ```

4. **Fixed Positioning**:
   - An element with `position: fixed` is positioned relative to the viewport (the browser window).
   - It stays in the same position even when the page is scrolled.
   - You can use the `top`, `right`, `bottom`, and `left` properties to specify the element's position.

   Example:
   ```css
   .element {
       position: fixed;
       top: 10px;
       right: 10px;
   }
   ```

5. **Floating Elements**:
   - Floating is not a `position` property but a way to control the layout of elements.
   - You can use `float: left` or `float: right` to make an element float to the left or right, allowing text and other elements to wrap around it.
   - Elements following the floated element will flow around it.

   Example:
   ```css
   .element {
       float: left;
   }
   ```

6. **Sticky Positioning**:
   - An element with `position: sticky` is positioned based on the user's scroll position.
   - It behaves like `relative` positioning until it reaches a certain scroll position, after which it becomes `fixed` and "sticks" to a specified position.
   - You can use the `top`, `right`, `bottom`, and `left` properties to determine where it becomes "sticky."

   Example:
   ```css
   .element {
       position: sticky;
       top: 10px;
   }
   ```

These positioning properties are powerful tools for creating complex layouts in CSS and controlling the placement of elements on a web page. They can be used individually or in combination to achieve various design effects.

### stylesheet properties
## XML
### What is it 
- Extensible Markup Language (XML) is a general-purpose specification for creating custom markup languages. It is classified as an extensible language because it allows its users to define their own elements. Its primary purpose is to facilitate the sharing of structured data across different information systems, particularly via the Internet.
### Syntax 
XML is a generic framework for storing any amount of text or any data whose structure
can be represented as a tree. The only requirement is that the text must be enclosed between
a start tag and a corresponding end tag. For example,
```xml
<BOOK> This is a book... </BOOK>
< ? XML VERSION = “1.0” ENCODING = “UTF – 8”? >
```

The basic syntax of an element is:
<NAME ATTRIBUTE = “value”> text </NAME>
Tree structure of an XML document:
```xml
<ROOT>
   <CHILD>
       <SUBCHILD> ... </SUBCHILD>
   </CHILD>
</ROOT>
```
```xml
<BOOKSTORE>
  <BOOK CATEGORY = “children”>
    <TITLE> Harry Potter </TITLE>
    <AUTHOR> J.K. Rowling </AUTHOR>
    <YEAR> 2005 </YEAR>
    <PRICE> 29.99 </PRICE>
  </BOOK>
  <BOOK CATEGORY = “web”>
    <TITLE> Learning XML </TITLE>
    <AUTHOR> Erik T. Ray </AUTHOR>
    <YEAR> 2003 </YEAR>
    <PRICE> 39.95 </PRICE>
 </BOOK>
</BOOKSTORE>
```

The following rules are used for using XML tags:
1).Tags are case sensitive. The tag `<TRAVEL>` differs from the tags `<Travel>` and
`<travel>`.
2).Starting tags always need a closing tag.
3).All tags must be nested properly.
4).Comments can be used like in HTML:
5).Between the starting tag and the end tag XML expects the content.
`<amount>135</amount>` is a valid tag for an element amount that has the content 135.
### +ves of XML
1. It is text – based.
2. It can represent common computer science data structures: records, lists, and trees.
3. Its self-documenting format describes structure and field names as well as specific
values.
4. It is platform – independent.
5. It can be updated incrementally.
### -ves
1. XML syntax is redundant or large relative to binary representations of similar data.
2. The redundancy may affect application efficiency through higher storage,
transmission, and processing costs.
3. Expressing non – hierarchical node relations requires extra effort.
### Need of XML
#### Data Exchange
1).XML is used to aid the exchange of data. It makes it possible to define data in a clear
way.
2). Both the sending and the receiving party will use XML to understand the kind of data
that's been sent. By using XML everybody knows that the same interpretation of the data
is used.
#### Replacement of EDI 
1).EDI (Electronic Data Interchange) has been for several years the way to exchange data
between businesses.
2).EDI is expensive, it uses a dedicated communication infrastructure. And the definitions
used are far from flexible.
3).XML is a good replacement for EDI. It uses the Internet for the data exchange. And it's
very flexible.

### DTD 
If you want to use a tag, you'll have to define it's meaning. This definition is stored in a
DTD (Document Type Definition). You can define your own DTD or use an existing one.
Defining a DTD actually means defining a XML language. An alternative for a DTD is
Schema.

## SGML
SGML, which stands for Standard Generalized Markup Language, is a markup language that served as the foundation for several other markup languages, including HTML (Hypertext Markup Language) and XML (eXtensible Markup Language). SGML was first standardized in the 1980s and is a metalanguage, which means it's a language used to define other markup languages.

Here are some key points about SGML:

1. **Metalanguage**: SGML is not intended for direct use in creating documents. Instead, it provides a framework for defining markup languages. It allows you to create document types and specify how elements, attributes, and their relationships should be structured.

2. **Generalized Markup**: SGML introduced the concept of generalized markup, which means that you can define your own tags and document structures. It provides a way to create structured documents, making it suitable for various types of content.

3. **Complex Document Structures**: SGML is particularly useful for creating complex document structures, including technical documentation, legal documents, and academic papers, where precise structure and semantics are critical.

4. **Hierarchy and Nesting**: SGML allows for the nesting of elements in a hierarchical structure, enabling the creation of rich, structured documents with a high degree of semantic meaning.

5. **Distinguishing Content from Structure**: SGML separates the content of a document from its structure and presentation. This separation of concerns is a fundamental principle in document markup.

6. **Standardization**: SGML itself is a standard, and there are industry-specific standards and document type definitions (DTDs) based on SGML for various applications.

7. **Legacy**: While SGML had a significant impact on document markup, it is not commonly used today for web content. Instead, HTML, XML, and related technologies have taken over for web-based documents.

SGML was a foundational technology that paved the way for the development of markup languages like HTML and XML, which are more widely used for various types of documents and data interchange on the internet and in various industries. Despite its reduced usage in modern web development, SGML's influence can still be seen in the principles and concepts that underpin document structuring and content separation.

## Difference b/w XML , HTML  and SGML
XML (eXtensible Markup Language), HTML (Hypertext Markup Language), and SGML (Standard Generalized Markup Language) are all markup languages, but they serve different purposes and have distinct characteristics. Here's a comparison of the three:

1. **Purpose**:
   - **XML**: XML is designed as a versatile, extensible language for storing and transporting data. It focuses on structuring and labeling data for exchange between different systems and applications.
   - **HTML**: HTML is primarily used for creating and structuring web documents, including web pages. It defines the presentation and layout of content on the web.
   - **SGML**: SGML serves as the foundation and ancestor of both XML and HTML. It is a metalanguage for defining markup languages and is not meant for document presentation. SGML is used for creating structured, highly specialized documents, such as technical manuals, legal documents, and academic papers.

2. **Syntax**:
   - **XML**: XML uses a strict, user-defined syntax where tags are case-sensitive and must be properly nested. You define your own elements and structure, which provides a high degree of flexibility.
   - **HTML**: HTML has predefined tags for structuring web content, such as headings, paragraphs, lists, and links. It's more lenient in terms of tag nesting, and the browser interprets how content is displayed.
   - **SGML**: SGML allows you to define your own document structure and markup language, making it the most flexible but also the most complex in terms of syntax.

3. **Presentation**:
   - **XML**: XML is presentation-agnostic. It doesn't concern itself with how the data should be displayed but focuses on data structure and semantics.
   - **HTML**: HTML is specifically designed for presenting content in web browsers. It includes tags for specifying text formatting, images, links, and more.
   - **SGML**: SGML is like XML in that it's primarily concerned with document structure, not presentation. The presentation is typically handled by other software.

4. **Extensibility**:
   - **XML**: XML is highly extensible. You can create custom elements and attribute names, allowing you to define your own data structures and document types.
   - **HTML**: HTML is less extensible compared to XML. While you can add custom attributes, it is not as versatile for creating new document types.
   - **SGML**: SGML is the most extensible of the three, as it's the basis for defining custom markup languages. You can create highly specialized document types tailored to specific needs.

5. **Usage**:
   - **XML**: XML is used for data interchange, configuration files, database storage, and many other applications where structured data is exchanged and stored.
   - **HTML**: HTML is used for creating web pages and web-based content. It focuses on how content is presented and displayed to users.
   - **SGML**: SGML is less common in modern usage but is still found in highly specialized applications such as technical documentation, legal documents, and government standards.

In summary, XML is a versatile data-centric language, HTML is focused on web content presentation, and SGML serves as the ancestor and foundation of both XML and HTML, with a primary focus on structured document creation. Each language has its own unique use cases and characteristics.

## JAVASCRIPT
### What is JS
JavaScript was designed to add interactivity to HTML pages.
It is a scripting language.
A scripting language is a lightweight programming language.
A JavaScript consists of lines of executable computer code.
It is usually embedded directly into HTML pages.
It is an interpreted language (means that scripts execute without preliminary compilation).
Everyone can use JavaScript without purchasing a license

### What can JS do
It gives HTML designers a programming tool.
It can put dynamic text into an HTML page.
It can react to events.
It can read and write HTML elements.
It can be used to validate data.
It can be used to detect the visitor’s browser.
It can be used to create cookies.
### Syntax 
```html
<HTML>
<BODY>
<SCRIPT TYPE=”text/javascript”>
Document.write(“Hello World !”)
</SCRIPT>
</BODY>
</HTML>
```

### JS object model
The JavaScript Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as a tree of objects, where each object corresponds to a part of the page.

Here are descriptions of some of the key objects within the JavaScript DOM:

1. **Window Object (5.3.1)**:
   - The `Window` object represents the browser window or tab in which the web page is displayed.
   - It serves as the global object for JavaScript code in a web page.
   - The `Window` object provides access to various properties and methods related to the browser window, including manipulating the window size, navigating to URLs, setting timeouts, and managing browser history.

   Example:
   ```javascript
   // Open a new browser window
   window.open("https://www.example.com");
   ```

2. **Frame Object (5.3.2)**:
   - Frames are used to divide a single browser window into multiple smaller windows, each with its own web page content.
   - The `Frame` object represents an individual frame or iframe within a frameset.
   - You can access and manipulate the content and properties of a specific frame using the frame object.

   Example:
   ```javascript
   // Access the content of a frame with the name "frameName"
   var frame = window.frames["frameName"];
   frame.location.href = "https://www.example.com";
   ```

3. **Navigator Object (5.3.3)**:
   - The `Navigator` object provides information about the user's browser and device.
   - It offers properties and methods to access details such as the browser name, version, user agent string, and platform information.
   - Developers can use this information to tailor web content or functionality based on the user's browser.

   Example:
   ```javascript
   // Get the user agent string
   var userAgent = window.navigator.userAgent;
   ```

4. **Document Object (5.3.4)**:
   - The `Document` object represents the web page itself.
   - It allows you to access and manipulate the content and structure of the HTML document.
   - You can use methods and properties of the `Document` object to add, remove, or modify elements on the page, change text content, and more.

   Example:
   ```javascript
   // Change the content of an element with the ID "example"
   var element = document.getElementById("example");
   element.textContent = "New content";
   ```

These objects, along with many others in the DOM, enable web developers to create dynamic and interactive web pages. JavaScript code can access and manipulate elements and properties of the document, as well as respond to user interactions and events within the web page.
#### DOM
The DOM, or Document Object Model, is a programming interface and representation of structured documents. It defines the logical structure of documents and the way a document is accessed and manipulated. In the context of web development, the DOM specifically refers to the representation of web pages in browsers.

Key points about the DOM:

1. **Structured Representation**: The DOM represents a document as a tree of objects. Each object corresponds to a part of the document, such as elements (HTML tags), attributes, and text. These objects form a hierarchy that reflects the structure of the document.

2. **Language-Neutral**: While the DOM is commonly associated with JavaScript in web development, it is not limited to a specific programming language. It provides a language-neutral interface for interacting with documents, and it can be used with various programming languages, although JavaScript is the most widely used.

3. **Dynamic and Interactive**: The DOM allows developers to access and modify the content and structure of a web page dynamically. This interactivity is what enables features like form validation, responsive user interfaces, and real-time updates without requiring a full page reload.

4. **Web Pages**: In the context of web development, the DOM represents the structure and content of HTML documents in a web browser. Each web page loaded in a browser has its own DOM, and JavaScript can be used to manipulate this DOM to create dynamic web applications.

5. **API for Web Development**: Web developers use the DOM API to access and modify the elements and content of web pages. Common tasks include reading and changing text, handling user input, modifying the appearance of elements, and responding to events (e.g., button clicks).

6. **Event Handling**: The DOM also provides a way to handle events such as clicks, keypresses, and mouse movements. Developers can define event listeners to trigger JavaScript code in response to these events.

7. **Cross-Browser Consistency**: While there might be some variations between different browsers in terms of how they implement the DOM, there are standardized specifications (e.g., W3C DOM) that help ensure a level of consistency, making it possible to write code that works across multiple browsers.

In summary, the DOM is a fundamental concept in web development, as it represents the structure and content of web pages and provides a standardized way to interact with and manipulate those pages using languages like JavaScript. It enables the creation of dynamic, interactive, and responsive web applications.
### Events 
Events are actions that can be detected by JavaScript. Every element on a web page has
certain events which can trigger JavaScript functions. For example, one can use the onClick
event on a button element to indicate that a function will run when a user clicks on the
button.
Examples of events:
➢ A mouse click
➢ A web page or an image loading
➢ Mouse over a hot spot on the web page.
➢ Selecting an input box in an HTML form
➢ Submitting an HTML form
➢ A keystroke

a) onLoad and onUnload
These events are triggered when the user enters or leaves the page. The onLoad event is
often used to check the visitor’s browser type and browser version, and load its proper
version of the web page based on the information. Both the events are also often sued to
deal with cookies that should be set when a user enters or leaves a page.
b) onFocus, onBlur and onChange
These events are often used in combination with validation of form fields.
c) onSubmit
The onSubmit event is used to validate ALL form fields before submitting it.
d) onMouseOver and onMouseOut
These events are often used to create “animated” buttons

### FormHandling in JS
Form handling in JavaScript is a fundamental part of web development that involves interacting with and manipulating HTML forms. Forms allow users to input data, and JavaScript can be used to validate, process, and interact with form elements. Here are the key aspects of form handling in JavaScript:

1. **Accessing Form Elements**:
   - You can access form elements (e.g., input fields, checkboxes, radio buttons) by using their `name` or `id` attributes in JavaScript.

   ```html
   <form id="myForm">
       <input type="text" name="username" id="username">
       <input type="password" name="password" id="password">
   </form>
   ```

   ```javascript
   // Access form and form elements
   const form = document.getElementById("myForm");
   const usernameInput = document.getElementById("username");
   const passwordInput = document.getElementById("password");
   ```

2. **Form Submission**:
   - You can use JavaScript to intercept the form submission event and perform actions before or after the form is submitted to the server.

   ```javascript
   form.addEventListener("submit", function (event) {
       // Prevent the default form submission
       event.preventDefault();

       // Your custom form validation and submission logic
   });
   ```

3. **Form Validation**:
   - JavaScript is often used to validate user input on the client side before submitting data to the server. You can check for required fields, data formats, and more.

   ```javascript
   form.addEventListener("submit", function (event) {
       if (usernameInput.value === "" || passwordInput.value === "") {
           alert("Both fields are required.");
           event.preventDefault(); // Prevent form submission
       }
   });
   ```

4. **Updating Form Elements**:
   - JavaScript can update the values of form elements, such as setting default values, changing the options in a select element, or enabling/disabling elements based on user actions.

   ```javascript
   // Set a default value for an input field
   usernameInput.value = "DefaultUser";

   // Disable an input field
   passwordInput.disabled = true;
   ```

5. **Handling Events**:
   - You can use JavaScript to respond to form-related events, such as user input events (e.g., `input`, `change`, `keyup`) and form submission events (e.g., `submit`).

   ```javascript
   // Detect when the username input changes
   usernameInput.addEventListener("input", function () {
       console.log("Username changed to: " + usernameInput.value);
   });
   ```

6. **Dynamic Form Elements**:
   - JavaScript can add or remove form elements dynamically, allowing you to create interactive forms that adapt to user actions.

   ```javascript
   // Add a new input field to the form
   const newInput = document.createElement("input");
   newInput.type = "text";
   form.appendChild(newInput);
   ```

These are some of the essential aspects of form handling in JavaScript. JavaScript empowers web developers to create dynamic, responsive forms and perform client-side validation and data processing, improving the user experience on web applications.

## Cookies
### What is it 
A COOKIE IS A SMALL FILE THAT THE SERVER EMBEDS ON THE USER’S
COMPUTER. EACH TIME THE SAME COMPUTER REQUESTS A PAGE WITH
A BROWSER, IT WILL SEND THE COOKIE TOO
### Creating cookie
The “Response.Cookies” command is used to create cookies. For example, to create a
cookies named ”firstname” and assigning the value “Ashwin” to it, following command
may be used:
```js
<%
Response . Cookies(“firstname”) = ”Ashwin”
%>
```
It is also possible to assign properties to a cookie, like setting a date when the cookie should
expire:
```
<%
Response . Cookies(“firstname”) = “Ashwin”
Response . Cookies(“firstname”) . Expires = # May 10, 2002 #
%>
```
###  Retrieving cookie
The “Request . Cookies” command is used to retrieve a cookie value. For example,
```
<%
Fname = Request . Cookies(“firstname”)
Response . write(“Firstname = ” & fname)
%>
```
### Cookie with key
if a cookie contains a collection of multiple values, this is said as the cookie has keys.
Consider the example to create a cookie collection named “user”. The “user” cookie has
keys that contains information about a user:
```
<%
Response . Cookies(“user”) (“firstname”) = “ADITYA VARDHAN”
Response . Cookies(“user”) (“lastname”) = “ANUBHAV AGARWAL”
Response . Cookies(“user”) (“country”) = “INDIA”
Response . Cookies(“user”) (“age”) = “22”
%>
```

## Frame obj and navigator obj
The `Frame Object` and `Navigator Object` in JavaScript are two different objects with distinct purposes and properties. Here's a comparison of the two:

**Frame Object:**
1. **Purpose**: The `Frame Object` represents an individual frame or iframe within a frameset. It is used for accessing and manipulating the content of a specific frame within a web page.
2. **Access**: You can access a frame object using the `window.frames` collection, specifying the frame's index or name.
3. **Properties**: The frame object provides properties related to the frame's document, location, and content. Common properties include `frame.document`, `frame.location`, and `frame.contentWindow`.
4. **Use Case**: Frame objects are typically used when dealing with framesets or iframes on a web page to control or manipulate content within a specific frame.
5. **Example**:
   ```javascript
   // Access a frame by name
   var frame = window.frames["frameName"];
   frame.location.href = "https://www.example.com";
   ```

**Navigator Object:**
1. **Purpose**: The `Navigator Object` represents the browser and provides information about the user's browser and device, including details about the browser version, user agent string, and platform information.
2. **Access**: The `Navigator Object` is accessed through the `window.navigator` object.
3. **Properties**: The navigator object includes properties such as `navigator.userAgent`, `navigator.appName`, `navigator.platform`, and others that provide information about the user's browsing environment.
4. **Use Case**: The navigator object is often used for feature detection and adapting web content or functionality based on the user's browser.
5. **Example**:
   ```javascript
   // Get the user agent string
   var userAgent = window.navigator.userAgent;
   ```

In summary, the `Frame Object` is used to work with individual frames within framesets or iframes on a web page, while the `Navigator Object` provides information about the user's browser and device, which can be used for feature detection and adapting web content to different environments. They serve different purposes and are used in different contexts in web development.
## Window Obj
The `Window` object is a fundamental component of JavaScript in the context of web development. It represents the browser window or tab where a web page is loaded and serves as the global object for JavaScript code within that page. This object is central to many aspects of web development and allows developers to interact with and control various facets of the browser and web page.

Through the `Window` object, developers can access properties and methods that enable tasks such as manipulating the Document Object Model (DOM), handling events, and managing browser navigation. For instance, you can use `window.document` to access the DOM, `window.addEventListener()` to handle events, and `window.location` to navigate to different URLs.

The `Window` object is also crucial for creating interactive user interfaces. It provides methods for creating dialog boxes, including `window.alert()`, `window.prompt()`, and `window.confirm()`, to engage with users effectively.

In addition, the `Window` object offers control over the window's dimensions, allowing you to resize or reposition the browser window as needed. Timers and asynchronous code execution are supported through functions like `window.setTimeout()` and `window.setInterval()`.

Moreover, the security of the `Window` object is paramount, as it can be used for pop-up windows and other features that may pose security risks. Modern browsers have implemented security measures to prevent unauthorized behavior, like intrusive pop-ups.

The `Window` object hierarchy includes child windows, such as iframes and pop-up windows. Developers can access these child windows using `window.frames` or by creating new windows using `window.open()`.

In summary, the `Window` object is a versatile and critical element in web development, allowing for dynamic and interactive web applications by providing control over the browser window, user interactions, and various other aspects of web pages.

## Program to create prompt box
To create a prompt dialog box in JavaScript, you can use the `window.prompt()` method. This method displays a dialog box with an input field and OK/Cancel buttons. Here's a simple example:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Prompt Dialog Example</title>
</head>
<body>
    <button onclick="showPrompt()">Click me</button>

    <script>
        function showPrompt() {
            // Display a prompt dialog
            const userInput = window.prompt("Please enter your name:", "John Doe");

            // Check if the user clicked "OK" and provided input
            if (userInput !== null) {
                alert("Hello, " + userInput + "!");
            } else {
                alert("No name provided.");
            }
        }
    </script>
</body>
</html>
```

In this example, we have an HTML button element, and when it is clicked, the `showPrompt()` JavaScript function is executed. Inside the function:

1. We use `window.prompt()` to display the prompt dialog. The first argument is the message or question to display, and the second argument is the default value for the input field.

2. The function checks if the user clicked "OK" and provided input. If the user provided input, an alert displays a greeting with the entered name. If the user clicked "Cancel" or didn't provide input, a different alert message is shown.

You can customize the prompt dialog by changing the message and default value to suit your needs.

## COOKIES
**Importance of Cookies:**
1. **User Authentication**: Cookies enable seamless and secure user authentication, allowing users to stay logged in without repeated logins.
2. **Personalization**: They enhance user experience by storing preferences and customizing content based on user choices.
3. **Shopping Carts**: Cookies simplify e-commerce by maintaining shopping cart items across sessions.
4. **Tracking User Behavior**: Web analytics and behavior tracking through cookies provide insights for website improvement and marketing strategies.
5. **Ad Targeting**: Cookies support targeted advertising, which benefits users with more relevant ads and websites with increased revenue.
**Drawbacks of Cookies:**
1. **Privacy Concerns**: Some users feel that cookies invade their privacy by tracking and collecting data without clear consent.
2. **Security Risks**: Cookies can be exploited for malicious purposes, including session hijacking and data breaches.
3. **Data Overload**: Accumulated cookies can affect website performance and increase storage requirements, potentially slowing down the site.
4. **Cross-Site Tracking**: Third-party cookies have raised concerns about cross-site tracking and user profiling without consent.
5. **Legal Compliance**: Evolving data privacy regulations require websites to comply with strict cookie usage requirements, adding complexity and potential legal risks for site owners.
6. 