- need app.py(where all the python code go) and templates/ (folder)
- other convention like requirements.txt (enumerate all 3rd party library that app wants to use, it loads these into the server ) and static/

## Session variable in Flask
- In the context of web development, Flask is a popular Python web framework that provides a set of tools and abstractions to simplify the process of building web applications. One of the features provided by Flask is the concept of a session.
- A session is a mechanism for storing data associated with a particular user across multiple HTTP requests. It allows the server to remember information about a user as they navigate through different pages or interact with the application. Typically, a session is used to maintain user-specific data, such as login credentials, shopping cart contents, or user preferences.
- Flask simplifies the usage of sessions by providing an abstraction called `session`. It is essentially a dictionary-like object that you can access and manipulate like any other dictionary in Python. The `session` object in Flask represents the user's session and persists data across multiple requests.
- When you put data into the `session` variable, it gets stored on the server side and associated with the user's session. This means that the data will be available again when the same user makes subsequent requests to the application. Flask takes care of managing the session data behind the scenes, ensuring that the appropriate data is retrieved and made accessible to your application code whenever needed.
- For example, let's say a user logs into a Flask application. Upon successful authentication, you can store their user ID or other relevant information in the `session` dictionary. Subsequently, on subsequent requests, you can retrieve this information from the `session` variable to identify the user and provide personalized experiences or access control.
- It's important to note that Flask uses a server-side storage mechanism for session data. By default, it uses a secure signed cookie to store a session identifier on the client side. This identifier is used to retrieve the associated session data from the server. This way, the actual session data remains secure and tamper-proof on the server, while the client only holds a reference to it.
- In summary, Flask's `session` abstraction simplifies the usage of sessions in web applications. It provides a persistent storage mechanism that allows you to store and retrieve user-specific data across multiple requests, ensuring that the data remains available for that particular user as they interact with the application.
- Server can send an additional http header in response headers :- like `set-cookie: session=value` here set cookie is the http header , and the session=value represent the key value pair 
- more info on [[Important terms#Sessions]]
```
app.config['SESSION_PERMANENT'] = False
app.config['SESSION_TYPE'] = 'filesystem'
Session(app)

```
- The code snippet you provided demonstrates the configuration and initialization of the Flask session object using the `app.config` dictionary. Let's break down each line:
	1. `app.config['SESSION_PERMANENT'] = False`: This line sets the value of the `SESSION_PERMANENT` configuration option to `False`. By default, Flask's sessions are permanent, meaning they persist across browser sessions. Setting it to `False` makes the session temporary, meaning it will be deleted when the user closes the browser or the session expires.	    
	2. `app.config['SESSION_TYPE'] = 'filesystem'`: This line sets the `SESSION_TYPE` configuration option to `'filesystem'`. It specifies the method Flask will use to store session data. In this case, the session data will be stored on the file system of the server.	    
	3. `Session(app)`: This line initializes the session object using the Flask application `app`. It binds the session functionality to your Flask application, allowing you to use the `session` object to store and retrieve data associated with a user's session.
- By configuring `SESSION_PERMANENT` to `False`, you are opting for temporary sessions that will be deleted when the user closes the browser. If you want the sessions to persist beyond browser sessions, you can set `SESSION_PERMANENT` to `True`.
- Using the `'filesystem'` session type, Flask will store session data as files on the server's file system. Each session will have a unique identifier, and the corresponding data will be stored in a file associated with that identifier. Storing session data on the file system can be useful for small to medium-sized applications.
- However, it's important to note that storing session data on the file system may have scalability limitations in certain scenarios, especially when dealing with a large number of sessions or distributed server environments. In such cases, alternative session storage mechanisms like a database or a distributed caching system may be more appropriate.
- Overall, the provided code configures Flask's session behavior to use temporary sessions stored on the file system, and it initializes the session object for use within your Flask application.
- how to delete the session when they logout 
	- ![[Pasted image 20230612074642.png]]
	- 

## App.py

### 1 code
```
from flask import Flask, render_template, request
app = Flask(__name__)
@app.route("/")
def index():
    return render_template('index.html')
```
- Imagine you have a special box called Flask that helps you build a website. When you say `app = Flask(__name__)`, you're basically opening that box and creating your own website inside it. The box is called `app` because you give it a name just like you would give a name to your pet.
- Now, let's think about the web address of a website. It's like the house number where people can find your website. When you say `@app.route("/")`, you're telling Flask that when someone visits the main address of your website (the root address), they should see something special.
- Then, you have a function called `index()`. It's like having a magic spell that you can cast whenever someone comes to your website's main address. The spell doesn't need any ingredients (no input parameters).
- Finally, when you say `return render_template('index.html')`, you're saying that when someone comes to your website, you want to show them a special page called `index.html`. It's like showing them a picture or a drawing that you made. The `return` part is like giving that picture to the visitor, so they can see it on their computer screen.
- So, in simple terms, this code is like creating your own website using Flask. When someone visits the main address of your website, they will see a special picture or drawing called `index.html` that you made.

### 2
```
def index():
    if 'name' in request.args:
        name = request.args['name']
    else:
        name = 'world'
```
- here request.args read the url parameters and give a dictionary 
- here in conditional statement we are looking for name(key) ,then on next line we are storing value of that key in name variable

### 3
```
---- HTML CODE -----
 <body>
     Hello , {{ name }}
 </body>
---- Python code ----
def index():
    if 'name' in request.args:
        name = request.args['name']
    else:
        name = 'world'
   ---alternative for if and else statement---
   name = reguest.args.get('name', 'world')
    return render_template('index.html', name=name)
```
- here {{ }} is used to put a value of the mentioned variable
- In python code , render_template takes file you want to show and the placeholder you want to pass as arguments , here left side in 2nd argument is the name of placeholder and on right side the value
-   In the given code snippet, the line `name = request.args.get('name', 'world')` retrieves the value of the query parameter named 'name' from the URL. Here's an explanation of how it works:
	- `request.args` represents the query parameters present in the URL. Query parameters are key-value pairs that are appended to the URL after a question mark (?), allowing data to be passed between the client and the server.
	- The `get()` method is used to retrieve the value of a specific query parameter. In this case, it retrieves the value of the query parameter [[Basics of internet#^cc9ff3]] named 'name'.
	- The `get()` method accepts two arguments: the first one is the name of the query parameter ('name' in this case), and the second one is the default value to be returned if the query parameter is not present in the URL.
	- If the 'name' query parameter is present in the URL, its value is assigned to the variable `name`. If the 'name' query parameter is not present, the default value 'world' is assigned to the variable `name`
	- After retrieving the value of the 'name' query parameter, the line `return render_template('index.html', name=name)` renders the 'index.html' template, passing the `name` variable as a parameter. This allows the 'name' value to be accessed and displayed in the rendered template, which can be useful for dynamically generating content based on user input or other parameters passed in the URL.

### 4
```
---- HTML CODE ----
<body>
        <form action="/greet" method="get">
            <input name="name" type="text" autocomplete="off" autofocus placeholder="Name">
            <button type="submit">Greet</button>
        </form>
    </body>

----Python code ----
@app.route('\greet')
def greet():
    return render_template('greet.html', name=request.args.get('name', 'world'))

```
- In input tag , there is an attribute 'name'
- more info on how form tag is function [[HTML AND CSS#Form]]
- using app.route a new path is created read [[Basics of internet#URL queries]] for more clarification on URL parameters

### 5
- Read this to know how to use jinja and use layout of html in other files [[Jinja#extending html to multiple html files]]

### 6
- using POST to hide the URL parameter of `?name=sahil`
```
--- Python code ---
@app.route('/greet' ,methods=['POST'])

--- HTML code ---
<form action="/greet" method="post">
```
- here it changes the method used
- The `methods=['POST']` parameter is used to specify that the associated route (`/greet` in this case) should only handle HTTP POST requests. By including this parameter, the route will only execute the function (`greet()`) when a POST request is made to that specific URL.
- more detail on [[Inspect function#^772036]]

### 7
- adding multiple scenario on a single route
```
@app.route('/' ,methods=['GET','POST'])
def index():
    if request.method == 'GET':
        return render_template('index.html')
    elif request.method == 'POST':
        return render_template('greet.html', name=request.form.get('name', 'world'))
```
- here in methods multiple are added because the initail request should be GET to receive index.html and POST is used to submit the form
- request.form for POST method  and request.args for GET method 
- GET method are default in the browser [[Important terms#^573c3e]] 

### Difference b/w args and form
- 1. `request.args`:
    - `request.args` is a dictionary-like object that contains the query string parameters in the URL. These parameters are typically used for GET requests or when data is appended to the URL.
    - For example, if the URL is `http://example.com/?name=John&age=25`, `request.args` will contain `{'name': 'John', 'age': '25'}`.
    - You can access individual values using the `request.args.get()` method. For instance, `request.args.get('name')` will return `'John'`.
    - `request.args` is immutable, meaning you cannot modify the values directly. It is read-only.
2. `request.form`: 
    - `request.form` is a dictionary-like object that contains the form data submitted by the client. This data is typically sent with POST requests.
    - It allows you to access form values based on their input names.
    - For example, if a form has an input field with `name="username"`, `request.form['username']` will give you the submitted value.
    - Unlike `request.args`, `request.form` is mutable. You can modify the form data if needed.

### 8
```
--- Jinja ---
    {% for name in REGISTRANTS %}
      <li>{{ name }}</li>
    {% endfor %}
    
--- python code ---

REGISTRANTS = {}

@app.route('/register', methods=['POST'])
def register():
    name= request.form.get('name')
    sport= request.form.get('sport')
    REGISTRANTS[name] = sport
    return render_template('success.html')
 
@app.route('/registrants')
def registrants():
    return render_template('registrant.html', registrants=REGISTRANTS)
```
- Using jinja to iterate over a dictionary named REGISTRANTS using for loop, notice in the end endfor is used which needs to be mentioned every time with verb (for example :- endwhile etc)
- In the python code we first created a REGISTRANTS dic , then populated it in register function . in the end represented on web page through registrant.html
- `{{ registrants[name] }}` for accessing the value of key
- read this for drop down option [[HTML AND CSS#Select]] 

## Error occurred during development 
- **Error:- SQLite objects created in a thread can only be used in that same thread.** 
	- Sol:- Use SQL objects (cursor and query) under same method (function) to avoid the issue of multiple thread
	- `conn = sqlite3.connect("usersdata.db", check_same_thread=False)`(Warning, your user signup implementation may trip up if two users try to create the same login credentials simultaneously, and your db scheme allows duplicate users. Hashing the password isn’t secure. It needs to be encrypted with a secret key.)
	- 
- 