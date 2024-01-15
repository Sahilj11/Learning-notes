## Experiment 1: Create a simple webpage using HTML


```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <a href="">Home</a>
    <a href="">Contact</a>
    <a href="">Prices</a>
    <a href="">Dashboard</a>
    <h1>This is a Heading</h1>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nemo perferendis
      doloribus assumenda error sapiente quaerat molestiae eius ex veritatis
      optio quia, magnam incidunt eveniet deleniti dicta, reiciendis cupiditate!
      Inventore, facilis.
    </p>
  </body>
</html>
```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231118080138.png)
## Experiment 2: Designing of registration form with table and use of hyperlink

This HTML structure presents a basic form layout using a table. It includes input fields for name, email, roll number, and class, followed by a submit button. The form also offers a prompt to login with a hyperlink. For functional use, the form inputs and login link require appropriate URLs or actions.


```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <table>
      <tr>
        <td>Name</td>
        <td><input type="text" /></td>
      </tr>
      <tr>
        <td>Email</td>
        <td><input type="text" /></td>
      </tr>
      <tr>
        <td>Roll No.</td>
        <td><input type="text" /></td>
      </tr>
      <tr>
        <td>Class</td>
        <td><input type="text" /></td>
      </tr>
      <tr>
        <td><input type="submit" /></td>
      </tr>
    </table>
    <p>Already have an account?<a href="">Login Here</a></p>
  </body>
</html>
```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231118080043.png)
## Experiment 3: Design a page with frames to include images and videos
Here's an example of how you can create a basic web page with framesets to include videos and images. Keep in mind that this is for educational purposes, and it's not a recommended practice for real-world web development:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Frameset Example</title>
</head>
<frameset cols="50%, 50%">
    <frame src="images_frame.html">
    <frame src="videos_frame.html">
</frameset>
</html>
```

Now, you would need to create two separate HTML files for the content of each frame:

**`images_frame.html`:**

```html
<!doctype html>
<html>
  <head>
    <title>Images Frame</title>
  </head>

  <body>
    <h1>Images Frame</h1>
    <img
      src="https://images.unsplash.com/photo-1608848461950-0fe51dfc41cb?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxleHBsb3JlLWZlZWR8MXx8fGVufDB8fHx8fA%3D%3D"
      alt="Image 1"
      height="200"
      width="200"
    />
    <img
      src="https://images.unsplash.com/photo-1615789591457-74a63395c990?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8YmFieSUyMGNhdHxlbnwwfHwwfHx8MA%3D%3D"
      alt="Image 2"
      height="200"
      width="200"
    />
  </body>
</html>
```

**`videos_frame.html`:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Videos Frame</title>
</head>
<body>
    <h1>Videos Frame</h1>
    <video width="640" height="360" controls>
        <source src="sample1.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <video width="640" height="360" controls>
        <source src="sample2.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</body>
</html>
```

**OUTPUT:**

![[exp3.png]]
In this example:

- We use the `<frameset>` element to create a two-column layout where one frame (`images_frame.html`) contains images, and the other frame (`videos_frame.html`) contains videos.
- Each frame content is in a separate HTML file.
- Images are displayed using the `<img>` element, and videos are embedded using the `<video>` element with the `controls` attribute for playback controls.

## Experiment 4: Add a Cascading style sheet for designing the webpage
Here's a simple homepage created without using an external CSS file. This example includes basic HTML markup to structure the page and style the content using inline styles:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Homepage</title>
</head>
<body>
    <header style="background-color: #333; color: #fff; text-align: center; padding: 10px;">
        <h1>Welcome to My Simple Homepage</h1>
    </header>

    <nav style="background-color: #444; color: #fff; padding: 10px;">
        <ul style="list-style: none; padding: 0; text-align: center;">
            <li style="display: inline; margin-right: 20px;"><a href="#">Home</a></li>
            <li style="display: inline; margin-right: 20px;"><a href="#">About</a></li>
            <li style="display: inline; margin-right: 20px;"><a href="#">Services</a></li>
            <li style="display: inline;"><a href="#">Contact</a></li>
        </ul>
    </nav>

    <main style="padding: 20px;">
        <h2>About Us</h2>
        <p>We are a simple homepage without any external CSS.</p>

        <h2>Our Services</h2>
        <ul>
            <li>Web Design</li>
            <li>Graphic Design</li>
            <li>Content Writing</li>
        </ul>

        <h2>Contact Us</h2>
        <p>Email: example@example.com</p>
        <p>Phone: +1 123-456-7890</p>
    </main>

    <footer style="background-color: #333; color: #fff; text-align: center; padding: 10px;">
        &copy; 2023 Simple Homepage
    </footer>
</body>
</html>
```

In this example:

- Inline styles are used within the `style` attribute of HTML elements to set background colors, text colors, padding, text alignment, and more.
- The `<header>` element contains the website title.
- The `<nav>` element contains a navigation menu.
- The `<main>` element holds the main content of the homepage, including information about the site, services, and contact details.
- The `<footer>` element is used for the footer text.

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020230927201626.png)
## Experiment 5: Use user defined function to get array of values and sort them in ascending order

```html
<!DOCTYPE html>
<html>
<head>
    <title>Array Sorting</title>
</head>
<body>
    <h1>Array Sorting</h1>
    <p>Enter a list of numbers separated by commas:</p>
    <input type="text" id="inputArray" placeholder="e.g., 5, 2, 9, 1, 5, 6">
    <button onclick="sortArray()">Sort Ascending</button>
    <div id="result"></div>

    <script>
        // Function to sort an array in ascending order
        function sortAscending(arr) {
            return arr.sort(function(a, b) {
                return a - b;
            });
        }

        // Function to handle sorting when the button is clicked
        function sortArray() {
            const inputElement = document.getElementById('inputArray');
            const resultElement = document.getElementById('result');
            const inputValues = inputElement.value.split(',').map(Number);

            if (inputValues.length > 0) {
                const sortedArray = sortAscending(inputValues);
                resultElement.textContent = 'Sorted Array: ' + sortedArray.join(', ');
            } else {
                resultElement.textContent = 'Please enter a valid list of numbers.';
            }
        }
    </script>
</body>
</html>
```

In this example, we have a user-defined function called `sortAscending(arr)` that takes an array as an argument and sorts it in ascending order using the `sort()` method with a custom comparison function.

The `sortArray()` function is called when the "Sort Ascending" button is clicked. It retrieves the input values entered by the user, splits them into an array, and then sorts and displays the sorted array in the `result` div.

You can enter a list of numbers separated by commas in the input field, and when you click the button, it will sort them in ascending order and display the result.

**OUTPUT:**


![](../../../../statics/Pasted%20image%2020230927202318.png)
![](../../../../statics/Pasted%20image%2020230927202337.png)
## Experiment 6: Design a dynamic web page with validation of form field using javascript 


```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <style>
      body {
        font-family: Arial, sans-serif;
        margin: 20px;
        padding: 20px;
      }

      table {
        width: 100%;
        max-width: 400px;
        margin: auto;
        border-collapse: collapse;
      }

      table,
      th,
      td {
        border: 1px solid #ddd;
      }

      th,
      td {
        padding: 10px;
        text-align: left;
      }

      th {
        background-color: #333;
        color: white;
      }

      input[type="text"],
      input[type="password"] {
        width: 100%;
        padding: 8px;
        box-sizing: border-box;
        margin-top: 6px;
      }

      input[type="submit"] {
        background-color: #007bff;
        color: white;
        padding: 10px;
        border: none;
        cursor: pointer;
      }

      input[type="submit"]:hover {
        background-color: #0056b3;
      }
    </style>
    <h1>Registration Form</h1>
    <form action="" method="post">
      <table>
        <tr>
          <th colspan="2">Personal Information</th>
        </tr>
        <tr>
          <td><label for="name">Name:</label></td>
          <td><input type="text" id="name" name="name" /></td>
        </tr>
        <tr>
          <td><label for="email">Email id:</label></td>
          <td><input type="text" id="email" name="email" required /></td>
        </tr>
        <tr>
          <td><label for="password">Password:</label></td>
          <td><input type="password" id="password" name="password" /></td>
        </tr>
        <tr>
          <td><label for="confirm">Confirm Password:</label></td>
          <td><input type="password" id="confirm" name="confirm" /></td>
        </tr>
        <tr>
          <td colspan="2">
            <input type="submit" value="Register" />
          </td>
        </tr>
      </table>
    </form>

    <script>
      const form = document.querySelector("form");
      form.addEventListener("submit", (e) => {
        e.preventDefault();
        const password = document.querySelector("#password").value;
        const confirmPass = document.querySelector("#confirm").value;
        const name = document.querySelector("#name").value;
        if (name == "") {
          alert("Enter some value in name field");
        }
        if (password != confirmPass) {
          alert("password not match");
        } else {
          alert("form submitted");
        }
      });
    </script>
  </body>
</html>
```

**OUTPUT:**


![](../../../../statics/Pasted%20image%2020231118081026.png)
## Experiment 7: Create a Catalogue using ASP


```asp
<%
Response.ContentType = "text/html"
%>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Catalog</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        .product {
            border: 1px solid #ccc;
            padding: 10px;
            margin-bottom: 20px;
        }

        h3 {
            margin-top: 0;
        }

        p {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>

    <h2>Product Catalog</h2>

    <% ' VBScript code starts here %>

    <% ' Function to display a product div %>
    <% Sub DisplayProduct(name, description, price) %>
        <div class="product">
            <h3><%= name %></h3>
            <p><%= description %></p>
            <p>Price: $<%= price %></p>
        </div>
    <% End Sub %>

    <% ' Display products using the function %>

    <% DisplayProduct("Product 1", "Description of Product 1.", 19.99) %>
    <% DisplayProduct("Product 2", "Description of Product 2.", 29.99) %>
    <% DisplayProduct("Product 3", "Description of Product 3.", 39.99) %>

</body>
</html>
```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231212212946.png)
## Experiment 8: Event Handling of registration form

To implement basic event validation for a registration form using HTML and JavaScript, you can use the `onsubmit` event handler to check whether the form data is valid before submitting it. Here's a simple example:



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Registration Form</title>
    <style>
        /* Add some basic styling for better presentation */
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        form {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>

<form id="registrationForm" onsubmit="return validateForm()">
    <h2>Registration Form</h2>
    <label for="firstName">First Name:</label>
    <input type="text" id="firstName" name="firstName" required>
    
    <br>

    <label for="lastName">Last Name:</label>
    <input type="text" id="lastName" name="lastName" required>

    <br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>

    <br>

    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required>

    <br>

    <label for="confirmPassword">Confirm Password:</label>
    <input type="password" id="confirmPassword" name="confirmPassword" required>

    <br>

    <button type="submit">Register</button>
</form>

<script>
    function validateForm() {
        var firstName = document.getElementById('firstName').value;
        var lastName = document.getElementById('lastName').value;
        var email = document.getElementById('email').value;
        var password = document.getElementById('password').value;
        var confirmPassword = document.getElementById('confirmPassword').value;

        // Perform your validation logic here
        if (firstName === '' || lastName === '' || email === '' || password === '' || confirmPassword === '') {
            alert('All fields must be filled out');
            return false;
        }

        if (password !== confirmPassword) {
            alert('Passwords do not match');
            return false;
        }

        // Additional validation logic can be added here

        // If all validation passes, the form will be submitted
        return true;
    }
</script>

</body>
</html>
```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231118124450.png)
## Experiment 9: Open a window from current window on Mouse over event

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Open Window on Mouse Over</title>
</head>
<body>

<button onmouseover="openNewWindow()">Hover me to open a new window</button>

<script>
    function openNewWindow() {
        // Specify the URL for the new window
        var newWindowUrl = 'https://www.google.com';

        // Open a new window with the specified URL
        window.open(newWindowUrl, '_blank');
    }
</script>

</body>
</html>
```

In this example, the `openNewWindow` function is called when the mouse hovers over the button. The `window.open` method is then used to open a new window with the specified URL (`https://www.example.com` in this case). The second parameter (`'_blank'`) indicates that the new window should be opened in a new tab or window.

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231118084333.png)

![](../../../../statics/Pasted%20image%2020231118084409.png)
## Experiment 10: Create a simple application to demonstrate servlets response and request object



Web.xml File Code
```
<?xml version="1.0" encoding="UTF-8"?>

<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
                      http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
  version="4.0"
  metadata-complete="true">

  <display-name>Welcome to Tomcat</display-name>
  <description>
     Welcome to Tomcat
  </description>
   <servlet>
        <servlet-name>SimpleServlet</servlet-name>
        <servlet-class>SimpleServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>SimpleServlet</servlet-name>
        <url-pattern>/SimpleServlet</url-pattern>
    </servlet-mapping>
</web-app>
```

```java
import java.io.*;
import javax.servlet.*;

@WebServlet("/SimpleServlet")
public class SimpleServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws IOException {
        // Set the response content type
        response.setContentType("text/html;charset=UTF-8");

        // Get information from the request object
        String clientIP = request.getRemoteAddr();
        String userAgent = request.getHeader("User-Agent");

        // Get PrintWriter object to write the HTML page
        PrintWriter out = response.getWriter();

        // Write the HTML response
        out.println("<html><head><title>Simple Servlet Example</title></head><body>");
        out.println("<h2>Request and Response Example</h2>");
        out.println("<p>Client IP Address: " + clientIP + "</p>");
        out.println("<p>User Agent: " + userAgent + "</p>");
        out.println("</body></html>");

        // Close the PrintWriter
        out.close();
    }
}
```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231212193410.png)
## Experiment 11: Demonstrate Array Objects and Date Objects predefined methods

### Array Object:

```javascript
// Creating an array
var fruits = ["Apple", "Banana", "Orange", "Mango"];

// Displaying the original array
console.log("Original Array:", fruits);

// 1. length: Returns the number of elements in the array
console.log("Number of elements:", fruits.length);

// 2. push(): Adds an element to the end of the array
fruits.push("Grapes");
console.log("After pushing 'Grapes':", fruits);

// 3. pop(): Removes the last element from the array
fruits.pop();
console.log("After popping the last element:", fruits);

// 4. join(): Joins all elements of an array into a string
var fruitsString = fruits.join(", ");
console.log("Joined String:", fruitsString);

// 5. indexOf(): Returns the index of the first occurrence of a specified element in the array
var indexOfBanana = fruits.indexOf("Banana");
console.log("Index of 'Banana':", indexOfBanana);

// 6. slice(): Returns a portion of the array
var slicedArray = fruits.slice(1, 3);
console.log("Sliced Array (from index 1 to 3):", slicedArray);
```

### Date Object:

```javascript
// Creating a Date object
var currentDate = new Date();

// Displaying the current date and time
console.log("Current Date and Time:", currentDate);

// 1. getFullYear(): Returns the year of the date
var year = currentDate.getFullYear();
console.log("Year:", year);

// 2. getMonth(): Returns the month (0-11)
var month = currentDate.getMonth();
console.log("Month:", month + 1); // Adding 1 because months are zero-based

// 3. getDate(): Returns the day of the month (1-31)
var day = currentDate.getDate();
console.log("Day of the Month:", day);

// 4. getDay(): Returns the day of the week (0-6)
var dayOfWeek = currentDate.getDay();
console.log("Day of the Week:", dayOfWeek);

// 5. toLocaleDateString(): Returns a string with a language-sensitive representation of the date
var formattedDate = currentDate.toLocaleDateString("en-US");
console.log("Formatted Date:", formattedDate);

// 6. setTime(): Sets the time value for a Date object
currentDate.setTime(currentDate.getTime() + 24 * 60 * 60 * 1000); // Adding one day
console.log("Date after adding one day:", currentDate);
```

These are just a few examples, and there are many more methods and properties available for both Array and Date objects in JavaScript.

## Experiment 12: Display calendar for the month and year selected from combo box

To display a calendar for the selected month and year using JavaScript, HTML, and CSS, you can create a simple web page with dropdowns for month and year. Here's an example using vanilla JavaScript:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calendar Display</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
        }

        th, td {
            border: 1px solid #dddddd;
            text-align: center;
            padding: 8px;
        }

        th {
            background-color: #f2f2f2;
        }

        select {
            padding: 5px;
            font-size: 16px;
        }
    </style>
</head>
<body>

<h2>Calendar Display</h2>

<label for="month">Select Month:</label>
<select id="month" onchange="displayCalendar()">
    <option value="0">January</option>
    <option value="1">February</option>
    <option value="2">March</option>
    <option value="3">April</option>
    <option value="4">May</option>
    <option value="5">June</option>
    <option value="6">July</option>
    <option value="7">August</option>
    <option value="8">September</option>
    <option value="9">October</option>
    <option value="10">November</option>
    <option value="11">December</option>
</select>

<label for="year">Select Year:</label>
<select id="year" onchange="displayCalendar()"></select>

<div id="calendarContainer"></div>

<script>
    // Function to display the calendar
    function displayCalendar() {
        var month = document.getElementById("month").value;
        var year = document.getElementById("year").value;

        var date = new Date(year, month, 1);
        var daysInMonth = new Date(year, month + 1, 0).getDate();

        var calendarContainer = document.getElementById("calendarContainer");
        calendarContainer.innerHTML = ""; // Clear previous content

        // Create a table for the calendar
        var table = document.createElement("table");

        // Create the header row with day names
        var headerRow = table.insertRow();
        var daysOfWeek = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
        for (var i = 0; i < daysOfWeek.length; i++) {
            var cell = headerRow.insertCell();
            cell.textContent = daysOfWeek[i];
        }

        // Calculate the starting day of the week
        var startingDay = date.getDay();

        // Create the calendar rows and cells
        var currentDay = 1;
        for (var i = 0; i < 6; i++) {
            var row = table.insertRow();

            for (var j = 0; j < 7; j++) {
                var cell = row.insertCell();

                if (i === 0 && j < startingDay) {
                    // Empty cells before the first day of the month
                    continue;
                }

                if (currentDay > daysInMonth) {
                    // Stop when all days of the month are displayed
                    break;
                }

                cell.textContent = currentDay;
                currentDay++;
            }
        }

        // Append the table to the calendar container
        calendarContainer.appendChild(table);
    }

    // Populate the year dropdown with the current year and the next 10 years
    var yearDropdown = document.getElementById("year");
    var currentYear = new Date().getFullYear();
    for (var i = 0; i < 10; i++) {
        var option = document.createElement("option");
        option.value = currentYear + i;
        option.textContent = currentYear + i;
        yearDropdown.appendChild(option);
    }

    // Display the calendar for the current month and year on page load
    displayCalendar();
</script>

</body>
</html>
```

This example includes two dropdowns for selecting the month and year. The calendar is dynamically generated based on the selected month and year. The JavaScript function `displayCalendar()` is called whenever the month or year dropdown is changed. The CSS provides some basic styling for better presentation.

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231118131305.png)
## Experiment 13:  Create a welcome cookie and display different image and text content each time when user hit the page

displaying different content (image and text) each time a user visits a page involves using a combination of HTML, CSS, JavaScript, and server-side scripting (if necessary). Below is a simple example using JavaScript for client-side functionality:

1. **HTML Structure (index.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="welcome-container">
        <img id="welcome-image" src="" alt="Welcome Image">
        <p id="welcome-text"></p>
    </div>

    <script src="script.js"></script>
</body>
</html>
```

2. **CSS Styles (styles.css):**
```css
body {
    margin: 0;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: #f0f0f0;
}

#welcome-container {
    text-align: center;
}

#welcome-image {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 20px;
}

#welcome-text {
    font-size: 18px;
    color: #333;
}
```

3. **JavaScript Code (script.js):**
```javascript
document.addEventListener("DOMContentLoaded", function() {
    
        setWelcomeCookie();

        // Display different content
        displayRandomContent();
});

function setWelcomeCookie() {
    // Set the welcome cookie with a one-day expiration
    let expirationDate = new Date();
    expirationDate.setDate(expirationDate.getDate() + 1);
    document.cookie = "welcomeCookie=true; expires=" + expirationDate.toUTCString() + "; path=/";
}

function displayRandomContent() {
    let images = ["image1.jpg", "image2.jpg", "image3.jpg"];
    let texts = ["Welcome to our page!", "Discover something new today.", "Enjoy your visit!"];

    let randomImage = images[Math.floor(Math.random() * images.length)];
    let randomText = texts[Math.floor(Math.random() * texts.length)];

    document.getElementById("welcome-image").src = randomImage;
    document.getElementById("welcome-text").innerText = randomText;
}

```

cookie is set, and random content is displayed (different image and text). 

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231212195448.png)

![](../../../../statics/Pasted%20image%2020231212195508.png)
## Experiment 14: Demostrate request and response object using HTML Form

1. **HTML Form (index.html):**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Demo</title>
</head>
<body>
    <h2>Submit Form</h2>
    <form action="FormServlet" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <br>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

2. **Servlet (FormServlet.java):**

```java
import java.io.*;

import javax.servlet.*;

@WebServlet("/FormServlet")
public class FormServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {

        // Retrieve form data from the request object
        String name = request.getParameter("name");
        String email = request.getParameter("email");

        // Process the data (you can perform any desired operations here)
        String processedData = "Hello, " + name + "! Your email is: " + email;

        // Set the response type to HTML
        response.setContentType("text/html");

        // Get the PrintWriter object to write the response
        PrintWriter out = response.getWriter();

        // Generate the HTML response
        out.println("<html><head><title>Form Submission Result</title></head><body>");
        out.println("<h2>Form Submission Result</h2>");
        out.println("<p>" + processedData + "</p>");
        out.println("</body></html>");
    }
}
```

In this example, when the user submits the form, the data is sent to the `FormServlet` using the POST method. The servlet uses the `HttpServletRequest` object to retrieve the form parameters (`name` and `email`). Then, it processes the data (in this case, simply concatenates it), and uses the `HttpServletResponse` object to send an HTML response back to the client.

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231212201207.png)

![](../../../../statics/Pasted%20image%2020231212201221.png)
## Experiment 15: Database connection to display all the values in the table

```java
import java.io.*;
import java.sql.*;
import javax.servlet.*;
@WebServlet("/DisplayDataServlet")
public class DisplayDataServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        Connection conn = null;
        PreparedStatement stmt = null;
        ResultSet rs = null;

        try {
            // Load the JDBC driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Connect to the database
            String jdbcUrl = "jdbc:mysql://localhost:3306/dbms_pract_60";
            String username = "debian-sys-maint";
            String password = "lXZrfcxkYQ9rFos7";
            conn = DriverManager.getConnection(jdbcUrl, username, password);

            // Create and execute the SQL query
            String sql = "SELECT * FROM customers_60";
            stmt = conn.prepareStatement(sql);
            rs = stmt.executeQuery();

            // Display the results
            out.println("<html><body>");
            out.println("<h2>User Data Table</h2>");
            out.println("<table border='1'>");
            out.println("<tr><th>User ID</th><th>Username</th><th>Email</th><th>Password</th><th>Age</th></tr>");

            while (rs.next()) {
                out.println("<tr>");
                out.println("<td>" + rs.getInt("user_id") + "</td>");
                out.println("<td>" + rs.getString("username") + "</td>");
                out.println("<td>" + rs.getString("email") + "</td>");
                out.println("<td>" + rs.getString("password") + "</td>");
                out.println("<td>" + rs.getInt("age") + "</td>");
                // Add more columns as needed
                out.println("</tr>");
            }

            out.println("</table>");
            out.println("</body></html>");

        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        } finally {
            // Close resources
            try {
                if (rs != null) rs.close();
                if (stmt != null) stmt.close();
                if (conn != null) conn.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }
}

```

**OUTPUT:**

![](../../../../statics/Pasted%20image%2020231212211121.png)