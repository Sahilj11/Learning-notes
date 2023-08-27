## Define
- All functions we used in languages are API (there is a standard way of interfacing with those functions , they have a name ) API is just how you use a function
- More generally it define how one interact with a service
- In the essence it is just a function that you are calling remotely 
- mechanism by one system can communicate with other in structured way more often it is done in JSON(data structure)
## Search
![[Pasted image 20230612080752.png]]
- important thing to not that , in this example , get method was used that is the reason why in url we can sell ?q=value. post method remove these values from url
- The `?q=value` added to the URL when creating a search page is a common convention used to pass search parameters via the URL. It is part of the URL query string.
- In a search page, when a user enters a search query and submits the form, the search parameters need to be transmitted to the server for processing. One way to achieve this is by appending the search parameters to the URL as a query string.
- Here's how the process typically works:
	1. The user enters a search query on the search page and submits the form.
	2. The form's `action` attribute specifies the URL of the server-side script or endpoint responsible for processing the search request.
	3. The search query is encoded and added to the URL as a query string using the `?` character followed by the parameter name (`q` in this case) and its corresponding value.
	4. The resulting URL is sent to the server, along with the other form data, via an HTTP request.
	5. The server-side script or endpoint can then extract the search query from the URL query string and process it to retrieve relevant search results.
- For example, if a user searches for "apple" on a search page, the resulting URL may look like this: `https://example.com/search?q=apple`. The server-side script can access the value of the `q` parameter to perform the search operation.
- Using the query string in the URL allows for bookmarking or sharing search results by simply copying and pasting the URL. Additionally, it enables the browser's back and forward buttons to work effectively, as the search parameters are part of the URL history.
- It's worth noting that the choice of the query parameter name (`q` in this case) is arbitrary and can be customized to match the requirements of your search implementation.
## AJAX 
- AJAX stands for "Asynchronous JavaScript and XML." It's a technique used in web development to send and receive data from a server without needing to refresh the entire web page.
- it essentially change the DOM by retreiving the data from a server and pluging it in
- To understand AJAX, let's imagine you're filling out a form on a website and submitting it. Traditionally, when you click the submit button, the entire page would reload, and you would see the updated information. However, with AJAX, the process is smoother.
- With AJAX, when you submit the form, JavaScript comes into play. It sends a request to the server in the background, asking for some information or performing an action. The server processes the request and sends back a response, usually in a format called JSON, which contains the requested data.
- Once the response is received, JavaScript can update just a specific part of the webpage dynamically, without reloading the entire page. This allows for a more interactive and seamless user experience.
- AJAX can be used for various purposes, such as:
	1. Form submission: Sending form data to the server and receiving a response without page refresh.
	2. Data retrieval: Fetching data from a server or API and updating the webpage dynamically.
	3. Auto-suggest: Providing suggestions as you type in a search box, without reloading the page.
	4. Real-time updates: Continuously updating the page with new information, like social media feeds or chat applications.
- In summary, AJAX is a technique that allows web developers to create more responsive and interactive web applications by asynchronously exchanging data with a server in the background, without requiring a full page reload. It enhances the user experience by providing smoother and faster interactions on the web.
- ![[Pasted image 20230612082001.png]]
- ![[Pasted image 20230612082048.png]]
- here see , there is no layout, as javascript is been used
- ![[Pasted image 20230612082237.png]]
- fetch = it sends HTTP request  to get data from server 
- ![[Pasted image 20230612082602.png]]
- this is the format we are getting from server when using the fetch method . this was created in this picture ![[Pasted image 20230612082048.png]]
- but transfer of data in such restricted way is not flexible , better would be to get the data in generic version . which is now a days in JSON
- ![[Pasted image 20230612082841.png]]
- it is a list of dictionaries
- ![[Pasted image 20230612082956.png]]
- in the let title line replace function is used to sanitise the user input by converting text into HTML entities

## JSON
- JSON stands for "JavaScript Object Notation." It's a way to store and exchange data between different programs and systems.
- Think of JSON as a language that computers can understand. It's like a special code that follows a specific set of rules. These rules make it easy for computers to read and work with the information.
- In JSON, data is organized into key-value pairs. The key is like a label or a name, and the value is the actual information associated with that label. For example, let's say we want to describe a person named John. In JSON, it might look like this:
```
{
  "name": "John",
  "age": 25,
  "city": "New York"
}
```
- Here, "name" is the key, and "John" is the value. Similarly, "age" is the key, and 25 is the value. We can also have more complex data structures in JSON, like lists or arrays:
```
{
  "name": "John",
  "age": 25,
  "hobbies": ["reading", "playing guitar", "running"]
}

```
- In this example, "hobbies" is the key, and the value is an array that contains a list of hobbies. 
- JSON is widely used because it's easy for both humans and computers to read and write. It's used in web development, APIs (Application Programming Interfaces), and data storage. Programs can take JSON data, understand it, and use it to perform different tasks or display information.
- Overall, JSON is a convenient way to represent and share data in a format that computers can easily interpret and work with

### 1
```
fetch('type url here')
.then(response => response.json())
.then(data =>{
    rate = data.rates.EUR;
    document.querySelector('body').innerHTML = rate;
});


.catch(error => {
   console.log('Error', error);
})
```
-   The code you provided demonstrates the usage of the `fetch()` function in JavaScript to make an HTTP request to a specified URL. Here's a breakdown of the code:
	1. `fetch('type url here')`: This line initiates an HTTP GET request to the URL specified inside the `fetch()` function. Replace `'type url here'` with the actual URL you want to fetch data from.
	2. `.then(response => response.json())`: The response from the server is received as a parameter in the callback function. This line converts the response data into JSON format. The `json()` method returns a promise that resolves with the parsed JSON data.
	3. `.then(data => { rate = data.rates.EUR; ... })`: This line handles the resolved promise from the previous step. The resolved data (parsed JSON) is received as a parameter in the callback function. In this case, it assumes the JSON data has a property called `rates`, which contains an object with a property `EUR`. The value of `EUR` is assigned to the `rate` variable.
	4. `document.querySelector('body').innerHTML = rate;`: Finally, this line updates the content of the `<body>` element in the HTML document. It sets the `innerHTML` property of the `<body>` element to the value of the `rate` variable, which was obtained from the fetched JSON data. 
- To summarize, the code fetches data from a specified URL, expects the data to be in JSON format, extracts the `rate` value from the JSON response, and updates the content of the `<body>` element in the HTML document with that value

## Promise in API
- In the context of API requests, promises are a feature of JavaScript that provide a way to handle asynchronous operations. When making an API request, the response is not immediately available, so the code needs to handle the asynchronous nature of the request. Promises provide a mechanism to handle the result of an asynchronous operation when it becomes available.
- Promises represent the eventual completion or failure of an asynchronous operation and allow you to attach callbacks to handle these outcomes. When making an API request using JavaScript's `fetch()` function or other similar functions, a promise is returned.
- Promises have three states:
	1. Pending: The initial state when the asynchronous operation is in progress and the final result is not yet available.
	2. Fulfilled: The state when the asynchronous operation is completed successfully, and the promise is resolved with a value.
	3. Rejected: The state when the asynchronous operation encounters an error or failure, and the promise is rejected with a reason or error message.
- To handle the result of a promise, you can chain `.then()` and `.catch()` methods to attach callback functions. The `.then()` method is used to handle the fulfilled state, and the `.catch()` method is used to handle the rejected state. These methods allow you to perform actions based on the result of the API request, such as processing the response data or handling errors
