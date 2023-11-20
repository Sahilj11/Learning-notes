## (Experiment 1) 

![[Pasted image 20231118080138.png]]

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

This HTML code represents a simple webpage structure with navigation links, a heading, and a paragraph. Here's a brief description of each part:

1. `<!doctype html>`: Declares the document type and version of HTML being used.

2. `<html lang="en">`: Specifies that the document is written in English.

3. `<head>`: Contains meta-information about the HTML document, such as character set, viewport settings, and the document title.

    - `<meta charset="UTF-8" />`: Specifies the character encoding of the document as UTF-8, ensuring proper handling of text.
    
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`: Sets the viewport properties for responsive design on various devices.

    - `<title>Document</title>`: Sets the title of the webpage, which typically appears in the browser tab.

4. `<body>`: Contains the main content of the webpage.

    - `<a href="">`: Represents navigation links. However, the `href` attributes are currently empty, and they should be filled with the actual URLs or relative paths to the respective pages.

    - `<h1>This is a Heading</h1>`: Defines a top-level heading with the text "This is a Heading."

    - `<p>`: Represents a paragraph of text. The content inside the `<p>` tag is placeholder text (Lorem Ipsum).

The code provides a basic structure for a webpage but lacks actual link destinations. To make the navigation functional, you should replace the empty `href` attributes with the appropriate URLs or paths. Additionally, you may want to add more content, styling, and possibly JavaScript functionality to enhance the webpage.
## (Experiment 2)

This HTML structure presents a basic form layout using a table. It includes input fields for name, email, roll number, and class, followed by a submit button. The form also offers a prompt to login with a hyperlink. For functional use, the form inputs and login link require appropriate URLs or actions.

![[Pasted image 20231118080043.png]]

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
## (Experiment 3)
Here's an example of how you can create a basic web page with framesets to include videos and images. Keep in mind that this is for educational purposes, and it's not a recommended practice for real-world web development:
![[exp3.png]]


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

In this example:

- We use the `<frameset>` element to create a two-column layout where one frame (`images_frame.html`) contains images, and the other frame (`videos_frame.html`) contains videos.
- Each frame content is in a separate HTML file.
- Images are displayed using the `<img>` element, and videos are embedded using the `<video>` element with the `controls` attribute for playback controls.

## (Experiment 4)
Here's a simple homepage created without using an external CSS file. This example includes basic HTML markup to structure the page and style the content using inline styles:
![[Pasted image 20230927201626.png]]


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
## (Experiment 5)

Here's an example of how to create a user-defined function in JavaScript to get an array of values from the user and then sort them in ascending order:
![[Pasted image 20230927202318.png]]

![[Pasted image 20230927202337.png]]
After sorting

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

## (Experiment 6)
![[Pasted image 20231118081026.png]]
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

This HTML document presents a registration form with associated styling and client-side validation using JavaScript. Here's a more detailed explanation of its key features:

1. **Styling with CSS:**
   - The `<style>` section within the `<body>` contains CSS rules for styling the webpage. It sets the overall font, margin, and padding for the body, defines the appearance of the form elements within the table, and specifies the look of the submit button.

2. **Form Structure using Table:**
   - The form is structured using an HTML table (`<table>`) for a neat and organized layout. The table includes rows (`<tr>`) and cells (`<td>`) to arrange form elements.

3. **Input Fields and Labels:**
   - Input fields for name, email, password, and password confirmation are created using `<input>` elements within table cells. Corresponding `<label>` elements improve accessibility and user experience.

4. **JavaScript Validation:**
   - A `<script>` section at the end of the document contains JavaScript code. It selects the form, listens for its submission event, and prevents the default form submission behavior.
   - The script retrieves values from the password and confirm password fields, as well as the name field. It then performs basic validation:
      - If the name field is empty, an alert prompts the user to enter a value in the name field.
      - If the password and confirm password fields don't match, an alert notifies the user.
      - If all validation checks pass, a success alert indicates that the form has been submitted.
## <u>Experiment 7: Create a Catalogue using ASP</u>

## (Experiment 8)

To implement basic event validation for a registration form using HTML and JavaScript, you can use the `onsubmit` event handler to check whether the form data is valid before submitting it. Here's a simple example:

![[Pasted image 20231118124450.png]]

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

This example includes basic form fields for first name, last name, email, password, and confirm password. The `validateForm` function is called when the form is submitted, and it checks if the required fields are filled out and if the passwords match. If any validation fails, an alert is shown, and the form submission is prevented. Otherwise, the form is submitted.
## <u>(Experiment 9)</u>
Certainly! You can achieve this using JavaScript. Below is an example of a simple HTML page with a button. When the mouse hovers over the button, a new window is opened.
![[Pasted image 20231118084333.png]]
this window open after hover of mouse
![[Pasted image 20231118084409.png]]


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

You can customize the URL and other parameters based on your requirements.

## <u>(Experiment 11)</u>

Certainly! Let's demonstrate some common methods associated with Array and Date objects in JavaScript.

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

## (Experiment 12)
To display a calendar for the selected month and year using JavaScript, HTML, and CSS, you can create a simple web page with dropdowns for month and year. Here's an example using vanilla JavaScript:

![[Pasted image 20231118131305.png]]

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

