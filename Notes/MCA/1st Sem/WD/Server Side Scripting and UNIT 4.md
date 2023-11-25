# Server Side Programming
## Introduction
Server-side scripting is a web server technology in which a user's request is fulfilled by running a script directly on the web server to generate dynamic html pages
It is usually used to provide interactive web sites that interface to databases or other data stores.

## Some of the technologies designed mainly or exclusively for server-side scripting, typically by embedding instructions directly in template web pages are as follows:
- CGI (common Gateway Interface)
- ASP (Active Server Pages)
- JSP (Java Server Pages)

### Common Gateway Interface
The common gateway interface, or cgi, is a standard for external gateway programs to interface with information servers such as http servers

The Common Gateway Interface (CGI) is a set of rules that specifies how parameters are passed from programs to Web servers. When a user submits a form, a program may be executed by the Web server, and the results are returned to the browser

The Common Gateway Interface, commonly known as CGI, is a standard protocol that defines how web servers communicate with external programs or scripts. It enables dynamic content generation on web servers by allowing the execution of scripts or programs in response to a web request.

Here are some key points about the Common Gateway Interface (CGI):

1. **Purpose**: CGI is designed to facilitate the interaction between a web server and external programs, allowing for the generation of dynamic content in response to user requests. This enables the creation of interactive and dynamic web applications.

2. **Communication Process**: When a user makes a request to a web server for a CGI-enabled resource (such as a script or program), the server passes control to the specified CGI program. The program then processes the request, generates dynamic content, and returns the result to the web server.

3. **Scripting and Programming Languages**: CGI is language-agnostic, meaning that it can be used with a variety of scripting and programming languages. Common languages for CGI scripts include Perl, Python, Ruby, and shell scripts. CGI scripts are usually executable files residing on the server.

4. **Environment Variables**: CGI programs receive information from the web server through environment variables. These variables contain details about the request, such as the user agent, query parameters, and server settings. CGI scripts can use this information to customize their behavior.

5. **Output to the Server**: CGI programs generate dynamic content as their output. This output is then sent back to the web server, which, in turn, delivers it to the client's web browser. The dynamic content can include HTML, images, or any other type of data.

6. **Security Considerations**: CGI scripts need to be carefully managed to avoid security vulnerabilities. Poorly written or insecure CGI scripts can potentially lead to security issues, such as unauthorized access or execution of malicious code on the server.

7. **Evolution and Alternatives**: While CGI was one of the earliest methods for creating dynamic web content, it has been largely replaced by more efficient technologies, such as server-side scripting languages (e.g., PHP, ASP.NET) and application frameworks (e.g., Flask, Django). These alternatives often provide better performance and ease of development compared to traditional CGI.

In summary, CGI is a protocol that enables web servers to interact with external programs or scripts, allowing for the dynamic generation of content in response to user requests. While it has been largely superseded by more modern technologies, understanding CGI is valuable for historical context and legacy systems that still rely on this protocol.

#### Process 
![[Pasted image 20231124103917.png]]

### Active Server Pages
ASP uses server side scripting to dynamically produce web pages that are not affected by the type of browser the web site visitor is using.The default scripting language used for writing ASP is VBScript, although the designer can use other scripting languages like Jscript (Microsoft’s version of JavaScript).

Any web pages containing ASP cannot be run by just simply opening the page in a web browser. The page must be requested through a web server that supports ASP, this is why ASP stands for Active Server Pages, no server, no active pages

#### Code example 
The appearance of an Active Server Page depends on who or what is viewing it. To the
web browser that receives it, an ASP looks just like a normal HTML page. In addition to
text and HTML tags, there also exists server side scripts.
The code below shows what a real, live ASP page looks like:
```asp
<html>
<head>
<title> New Page </title>
</head>
<body>
<h1> My Welcome Page</h1>
<p> <% if Time>#12:00:00 AM# AND_ Time<#12:00:00 PM# Then %> </p>
<h2> Good Morning !!! </h2>
<p> <% if Time>#12:00:00 AM# AND_ Time<#6:00:00 PM# Then %> </p>
<h2> Good Afternoon !!! </h2>
</body></html>
```

1. **ASP files are only processed when a client requests them from the server:**
   - ASP (Active Server Pages) files are not preprocessed or compiled in the same way as traditional programming languages. Instead, they are processed dynamically on the server.
   - When a client (typically a web browser) requests an ASP page, the server processes the ASP code within that page at the time of the request. The server then sends the resulting HTML or other content to the client.

2. **There are some .dll files such as ASP.dll which contains standard objects:**
   - ASP.dll is an example of a dynamic link library (DLL) file that contains standard objects and functions used in ASP programming.
   - These standard objects are part of the ASP framework and provide built-in functionality for common tasks, such as interacting with databases, handling sessions, and managing user authentication.

3. **Functions are called from these DLLs:**
   - ASP pages can call functions and use objects from DLLs like ASP.dll.
   - These functions provide a set of pre-built, reusable functionalities that developers can leverage in their ASP code. For example, if you need to perform database operations, you might use functions provided by ASP.dll to connect to a database and execute queries.

4. **Since these functions are previously defined and known, things that can be done with ASP are bounded:**
   - The use of predefined functions and standard objects provides a level of structure and consistency to ASP development.
   - The capabilities of ASP are bounded by the functions and objects available in the associated DLLs. While developers can create custom functions and components, the overall functionality is somewhat limited to what is provided by the ASP framework.

5. **ASP codes do not need to be compiled:**
   - Unlike some programming languages where code needs to be compiled into machine code or an intermediate language before execution, ASP code is interpreted on the fly.
   - The lack of a compilation step allows for rapid development and easy modification of ASP code. Changes made to ASP code are immediately reflected when the page is requested without the need for a separate compilation process.
- There exists a global.asa file which is used to specify events and global session variables which are used for all ASP files in the server.
- Before any ASP file is processed, global.asa is processed and it defines global events.
- The processing of an ASP file starts with the separation of ASP scripts and HTML codes in IIS.
- Then each script code is processed.
- The HTML corresponds of these scripts are created, and injected related places.
- Final HTML codes are sent to the client and displayed by the web browser.

#### What can ASP do?
- The most important feature of ASP is creating dynamic pages.
- You can manage data with database operations such as getting and storing people’s information in the Database.
- Interactive applications can be implemented, i.e. news type people like may be displayed.
- Script codes are not sent to the client, which brings security.
#### Advantages of ASP
- It gives dynamism to the pages created.
- Interactive pages reflecting the preferences of the user can be developed.
- ASP is a very good innovation to dynamic web programming.
- Data obtaining and displaying became more easy and efficient.
#### Disadvantages of ASP
- It is slower than most of similar technologies.
- Not very much portable.

### JSP(Java Server Pages)
#### Intro
Java server pages (jsp) is a java technology that allows software developers to dynamically generate html, xml or other types of documents in response to a web client request
#### Features
1. Platform and Server Independence. The JSP technology follows the ‘write once’ run anywhere, rule which is the basis of the java language. JSP technology can run on various web server including Apache, Netscape and IIS and is supported by a large variety of tools from different vendors.
2. Environment. JSP uses pure java and takes full advantage of its object-oriented nature. This technology lets the designer separate content generation from layout by accessing component from the page.
3. Extensible JSP Tags. JSP uses a combination of tags and scripting to create dynamic web pages. It allows the designer to extend the JSP tags available. JSP developers can create custom tag libraries, so that more functionality can be extracted using XML-like tags and this leads to less use of scripting in JSP pages.
4. Reusability Across Platform. The JSP pages uses components which are reusable. These reusable components help keep the pages simple and run faster.
5. Easier Maintenance. Application made using JSP technology are easier to maintain.

#### JSP Processing 

![[Pasted image 20231124173440.png]]


##### JSP Architecture
JSP is a part of the Java platform, Enterprise Edition (J2EE), which is the java architecture
for developing multitier enterprise applications. A JSP page is executed by a JSP engine,
which is installed in a web server or a JSP enabled application server. The JSP engine
receives the request from a client to the JSP page and generates responses from the JSP
page to the client.

#### JSP Syntax
Certainly, let's break down the notes on JSP (JavaServer Pages) based on the provided information:
##### Categories in JSP:
1. **Elements:**
   - Elements in JSP can be broadly categorized into two types: those processed on the server and everything else.
2. **Template:**
   - The template refers to data that the JSP engine ignores. This includes everything other than elements that are processed on the server.
##### Element Data Categories:
1. **Directives:**
   - Directives provide global information about an entire JSP page.
   - They are used to set page-level attributes and configurations that affect the overall behavior of the JSP.
The directives should start with `<%@` and end with `%>`. There are three types of JSP directives.
They are:
1. The page directive defines a number of attributes that affect the whole page. The
syntax is as follows:
`<%@ page attributes %>`
2. The include directive is used to insert text and code at JSP translation time. The
syntax is as follows:
`<%@ include file = “relative URL” %>`
The file that the file attribute refers to can reference a normal HTML file or another JSP
file which will be evaluated at translation time.
3. The taglib directive declares that the page uses custom tags. Uniquely names the
tag library defining them and associates a tag prefix that will distinguish the usage
of these tags. The syntax is as follows:
`<%@ taglib uri = “taglibrary URL prefix” %>`
2. **Declarations:**
   - Declarations in JSP are used to declare variables or methods that can be used later in the JSP page.
   - They are typically used to define variables or methods that have a scope limited to the current JSP page.
3. **Scriptlets:**
   - Scriptlets are sections of Java code embedded within the JSP page.
   - They are executed every time the page is requested, allowing dynamic content generation.
   - Scriptlets are enclosed within `<% %>` tags.
```jsp
<html>
<head><title> Hello </title></head>
<body>
<%
int x = 0;
for(x = 0; x < 5; x++)
{
out.println(“<h1> Hello world ! </h1>”);
}
%>
</body>
</html>
```
4. **Expressions:**
   - Expressions are used to insert dynamic data into the output stream.
   - They are evaluated, converted to a string, and inserted in the place where the expression is placed.
   - Expressions are enclosed within `<%= %>` tags.
5. **Standard Actions:**
   - Standard actions are predefined XML-like tags that provide common functionality.
   - They allow developers to use ready-made components for tasks like including another resource, controlling flow, and working with JavaBeans.
   - Standard actions are often associated with specific XML namespaces, such as JSTL (JavaServer Pages Standard Tag Library).
##### Life cycle of JSP
1. JSP Page Translation: A java servlet file is generated from the JSP source file. Generated servlet implements the interface javax.servlet.jsp.HttpJspPage. The interface HttpJspPage extends the interface JspPage. This interface JspPage extends the interface javax.servlet.Servlet.
2. JSP Page Compilation: The generated java servlet file is compiled into a java servlet class. The generated servlet class thus implements all the methods of the above said three (javax.servlet.jsp.HttpJspPage, JspPage, javax.servlet.Servlet) interfaces.
3. Class Loading: The java servlet class that was compiled from the JSP source is loaded into the container.
4. Instance Creation: An instance is created for the loaded servlet class. The interface JspPage contains jspInit() and jspDestroy(). The JSP specification has provided a special interface HttpJspPage for JSP pages serving HTTP requests and this interface contains _jspService().
5. jspInit( ) execution: This method is called when the instance is created and it is called only once during JSP life cycle. It is called for the servlet instance initialization.
6. _jspService() execution: This method is called for every request of this JSP during its life cycle. It passes the request and the response objects. _jspService() cannot be overridden.
7. jspDestroy() execution: This method is called when this JSP is destroyed and will not be available for future request
#### JSP vs Servlet 
![[Pasted image 20231124174921.png]]

## PERL(Practical extraction report language)
Perl is an interpreted language optimized for scanning arbitrary text files, extracting information from those text files, and printing reports based on that information
PERL is high-level, general-purpose, interpreted, dynamic programming language.
### Application
1. PERL has been used since the early days of the Web to write CGI scripts.
2. PERL is often used as a glue language, tying together systems and interfaces that were not specifically designed to interoperate, and for converting or processing large amounts of data for tasks like creating reports.
3. Graphical user interfaces (GUI's) may be developed using PERL.
4. PERL is also widely used in finance and bioinformatics, where it is valued for rapid application development and deployment, and the ability to handle large data sets.
## VBScript
Vbscript (short for visual basic scripting edition) is an active scripting language developed by microsoft.

When employed in Microsoft Internet Explorer, VBScript is similar in function to JavaScript, as a language to write functions that are embedded in or included from HTML pages and interact with the Document Object Model (DOM) of the page, to perform tasks not possible in HTML alone.

VBScript is used for server-side processing of web pages, most notably with Microsoft Active Server Pages (ASP).

## JSP Configure and troubleshooting
JSP needs any web server; this can be tomcat by apache, WebLogic by bea, or WebSphere by IBM.

After successful installation of tomcat and JSP we need IDE integrated development environment.

#### troubleshooting

Troubleshooting is a form of problem solving most often applied to repair of failed products or processes. It is a logical, systematic search for the source of a problem so that it can be solved, and so the product or process can be made operational again. Troubleshooting is needed to develop and maintain complex systems where the symptoms of a problem can have many possible causes. Troubleshooting is used in many fields such as engineering, system administration, electronics, automotive repair, and diagnostic medicine.

Troubleshooting requires identification of the malfunction(s) or symptoms within a system. Then, experience is commonly used to generate possible causes of the symptoms. Determining which cause is most likely is often a process of elimination - eliminating potential causes of a problem. Finally, troubleshooting requires confirmation that the solution restores the product or process to its working state.
# ASP 
## Configuring
### For Apache Server (with mod_aspdotnet):

1. **Install Apache:**
    
    - Ensure that Apache is installed on your server.
2. **Install mod_aspdotnet:**
    
    - Download and install mod_aspdotnet for Apache. This module allows Apache to serve ASP.NET and ASP Classic pages.
    - Configure Apache to load the mod_aspdotnet module.
3. **Configure ASP Settings:**
    
    - In your Apache configuration file (e.g., `httpd.conf`), add the following lines:
        
        bashCopy code
        
        `AddType application/x-asp-net .aspx AddType application/x-asp-net .asmx AddType application/x-asp-net .ashx AddType application/x-asp-net .asax AddType application/x-asp-net .ascx`
        
    - Adjust other settings as needed.
4. **Restart Apache:**
    
    - After making changes, restart Apache to apply the configuration.

## Basic Syntax
An ASP file normally contains HTML tags, just like an HTML file. However, an ASP file can also contain server scripts, surrounded by the delimiters <% and %>.

### Write output to browser
The response.write command is used to write output to a browser. The following example sends the text “Hello World !” to the browser:
```asp
<html>
<body>
<%
Response.write(“Hello World ! ”)
%>
</body>
</html>
```

There is also a shorthand method for the response.write command. The following example also sends the text “Hello World !” to the browser:
```asp
<html>
<body>
<%=”Hello World ! ”%>
</body>
</html>
```
### Life Time of variable
A variable declared outside a procedure can be accessed and changed by any script in the ASP file. A variable declared inside a procedure is created and destroyed every time the procedure is executed.

#### Session Variable
Session variables are used to store information about ONE single user, and are available to all pages in one application.

#### Application variable 
Application variables are also available to all pages in one application.

### Procedures
```asp
<html>
<head>
<% sub vbproc(num1,num2)
Response.write(num1*num2)
end sub
%>
</head>
<body>
<p> Result: <% call vbproc(3,4) %></p>
</body>
</html>
```

Insert the `<%@language=”language”%>` line above the `<html>` tag to write procedures or
functions in another scripting language than default:

```asp
<%@ language=”javascript” %>
<html>
<head>
<%
   function jsproc(num1,num2){
	Response.write(num1*num2)
   }
%>
</head>
<body>
<p> Result: <% jsproc(3,4) %></p>
</body>
</html>
```
### User Input
The request object may be used to retrieve user information from forms.
User input can be retrieved in two ways: With Request.QueryString or Request.form

#### Request.QueryString
This command is used to collect values in a form with method= “get”. Information sent from a form with the GET method is visible to everyone (will be displayed in the browser’s address bar) and has limits on the amount of information to send. If a user typed “pankaj” and “sharma” in the form example above, the URL sent to the server would look like this:
`http://www.abes.ac.in/simpleform.asp?fname=pankaj&lname=sharma`

Assume that the ASP file “simpleform.asp” contains the following script:
```asp
<body>
Welcome
<% response.write(request.querystring(“fname”))
Response.write(“ ” & request.querystring(“lname”))
%>
</body>
```
The browser will display the following in the body of the document:
Welcome pankaj sharma

#### Request.Form
This command is used to collect values in a form with method= “post”. Information sent from a form with the POST method is invisible to others and has no limits on the amount of information to send.

If a user typed “Bill” and “Gates” in the form example above, the URL sent to the server would look like this:
`Http://www.abes.ac.in/simpleform.asp`
Assume that the ASP file “simpleform.asp” contains the following script:

```asp
<body>
Welcome
<%
Response.write(request.form(“fname”))
Response.write(“ ” & request.form(“lname”))
%>
</body>
```
output:
Welcome Bill Gates


## ASP Object and component
ASP (Active Server Pages) is a server-side scripting technology developed by Microsoft for building dynamic web applications and websites. ASP allows you to embed server-side code within HTML pages, enabling the creation of dynamic content that can interact with databases and perform various server-side tasks. ASP objects and components are essential elements in the ASP architecture, providing a way to organize and manage server-side functionality.

### ASP Objects:

ASP objects are pre-built, reusable components that encapsulate specific functionalities, making it easier to perform common tasks in server-side scripting. Some key ASP objects include:

1. **Request Object:**
   - Handles incoming data from client requests, such as form submissions or query strings.

   Example:
   ```asp
   <% 
   Dim userInput
   userInput = Request("username")
   Response.Write("Hello, " & userInput)
   %>
   ```

2. **Response Object:**
   - Sends output to the client, such as HTML content or redirecting to another page.

   Example:
   ```asp
   <% 
   Response.Write("This is dynamic content.")
   Response.Redirect("newpage.asp")
   %>
   ```

3. **Session Object:**
   - Manages user-specific data across multiple pages during a user's session.

   Example:
   ```asp
   <% 
   Session("user_id") = "12345"
   %>
   ```

4. **Server Object:**
   - Provides server-related information and functionalities.

   Example:
   ```asp
   <% 
   Dim serverPath
   serverPath = Server.MapPath("/")
   Response.Write("The physical path of the root directory is: " & serverPath)
   %>
   ```

### ASP Components:

ASP components are more extensive pieces of software that can be reused across multiple applications. They are often created using languages like Visual Basic or C++ and are registered on the server. Components can encapsulate complex business logic or interactions with external systems.

Example of using a component (assuming you have registered it on the server):

```asp
<%
Dim myComponent
Set myComponent = Server.CreateObject("MyComponent.MyClass")
Response.Write("Result from the component: " & myComponent.DoSomething())
Set myComponent = Nothing
%>
```

In the example above, "MyComponent.MyClass" is the ProgID (Programmatic Identifier) of a registered component, and `DoSomething()` is a method provided by that component.

Understanding and effectively using ASP objects and components allow developers to build scalable, modular, and efficient server-side applications.
# JSP
## JAVA Servlet 
A Java program that extends the functionality of a Web server, generating dynamic content and interacting with Web clients using a request-response paradigm.
## JSP
A text-based document capable of returning both static and dynamic content to a client browser. Static content and dynamic content can be intermixed. Static contents are HTML, XML, Text and Dynamic contents are Java code, Displaying properties of JavaBeans, Invoking business logic defined in Custom tags.

## JSP Object and Component
In JSP (JavaServer Pages), implicit objects are predefined objects that are automatically created by the JSP container and are available for use in the JSP page without the need for explicit declaration or instantiation. These objects provide information about the request, session, application, and other aspects of the JSP environment. The JSP container makes these implicit objects available during the lifecycle of a JSP page.

Here are the commonly used implicit objects in JSP:

1. **request:**
   - Represents the client's request to the server. It is an instance of the `HttpServletRequest` class.
   - Example usage: `request.getParameter("parameterName")` to retrieve request parameters.

2. **response:**
   - Represents the server's response to the client. It is an instance of the `HttpServletResponse` class.
   - Example usage: `response.getWriter().write("Hello, World!")` to write content to the response.

3. **out:**
   - Represents the output stream used to send content to the client's browser. It is an instance of the `JspWriter` class.
   - Example usage: `<%= "Hello, World!" %>` to write content directly to the response.

4. **session:**
   - Represents the user's session. It is an instance of the `HttpSession` class.
   - Example usage: `session.getAttribute("attributeName")` to retrieve session attributes.

5. **application:**
   - Represents the servlet context or application context. It is an instance of the `ServletContext` class.
   - Example usage: `application.getRealPath("/")` to get the real path of the web application's root directory.

6. **config:**
   - Represents the configuration information of the JSP page. It is an instance of the `ServletConfig` class.
   - Example usage: `config.getInitParameter("parameterName")` to retrieve initialization parameters.

7. **page:**
   - Represents the JSP page itself. It is an instance of the generated servlet class.
   - Example usage: `pageContext.getAttribute("attributeName")` to retrieve page attributes.

8. **pageContext:**
   - Represents the page context, providing access to various objects such as request, response, session, and application.
   - Example usage: `pageContext.forward("newPage.jsp")` to forward the request to another JSP page.

These implicit objects simplify the development of dynamic web applications by providing easy access to information related to the request, response, session, and application context. Developers can use these objects directly within the JSP page to perform common tasks and access key components of the web application environment.

## Progamming language used in ASP/CGI/JSP
ASP (Active Server Pages), CGI (Common Gateway Interface), and JSP (JavaServer Pages) are technologies used for server-side scripting in web development. Each of them supports different programming languages:

1. **ASP (Active Server Pages):**
   - **Primary Language:** VBScript (Visual Basic Scripting Edition) is the default scripting language for classic ASP.
   - **Additional Languages:** JScript (Microsoft's version of JavaScript) is also supported in ASP, and you can use other languages through third-party components.

   Example (VBScript):
   ```asp
   <% 
   Dim message
   message = "Hello, ASP!"
   Response.Write(message)
   %>
   ```

2. **CGI (Common Gateway Interface):**
   - **Any Language:** CGI is language-agnostic, meaning it can work with any programming language that can read from and write to standard input/output. Common languages include Perl, Python, C, and shell scripts.

   Example (Perl):
   ```perl
   #!/usr/bin/perl
   print "Content-type: text/html\n\n";
   print "Hello, CGI!";
   ```

3. **JSP (JavaServer Pages):**
   - **Primary Language:** Java is the primary language for JSP.
   - **Additional Languages:** JSP also allows embedding JavaBeans components and custom tags. Tag libraries can be created using Java or other languages.

   Example (Java):
   ```jsp
   <%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
   <html>
   <head>
       <title>JSP Example</title>
   </head>
   <body>
       <%
           String message = "Hello, JSP!";
           out.println(message);
       %>
   </body>
   </html>
   ```

## Retreiving content from HTML Form

```html
<form action="form.jsp" method="get">
<table>
<tr><td><b>Name</b>
<td><input type="text" name="name">
<tr><td><b>Favorite color</b>
<td><input type="text" name="color">
</table>
<input type="submit" value="Send">
</form>
```
Keeps the browser request information in the request object. The request object contains
the environment variables you may be familiar with from CGI programming. For example,
it has the browser type, any HTTP headers, the server name and the browser IP address.
You can get form values using request.getParameter object.
The following JSP script will extract the form values and print them right back to the user.

form.jsp
```jsp
Name: <%= request.getParameter("name") %> <br>
Color: <%= request.getParameter("color") %>
```

### Retieriving a Query String(parameters passed in the URL)

In JavaServer Pages (JSP), you can retrieve values from the query string (parameters passed in the URL) using the implicit `request` object. The query string is the part of a URL that follows the "?" symbol and contains key-value pairs separated by "&" symbols.

Here's an example of how to retrieve a query string parameter in a JSP:

Assume you have a URL like this: `http://example.com/mypage.jsp?name=John&age=25`

To retrieve the values of the `name` and `age` parameters in your JSP, you can do the following:

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Query String Example</title>
</head>
<body>

<%
    // Retrieve values from the query string
    String name = request.getParameter("name");
    String age = request.getParameter("age");

    // Check if parameters are not null before using them
    if (name != null && age != null) {
%>
        <p>Name: <%= name %></p>
        <p>Age: <%= age %></p>
<%
    } else {
%>
        <p>No valid parameters found in the query string.</p>
<%
    }
%>

</body>
</html>
```

In this example:

- `request.getParameter("name")` retrieves the value associated with the "name" parameter in the query string.
- `request.getParameter("age")` retrieves the value associated with the "age" parameter in the query string.

It's good practice to check if the parameters are not `null` before using them to avoid potential `NullPointerExceptions`. In the example, the values are displayed only if both `name` and `age` are not `null`.

Remember that URL parameters are typically URL-encoded, so if you have special characters in the parameter values, you might need to decode them using `java.net.URLDecoder`.

# Cookies
In JSP cookie are the object of the class javax.servlet.http.Cookie. This class is used to
creates a cookie, a small amount of information sent by a servlet to a Web browser, saved
by the browser, and later sent back to the server. A cookie's value can uniquely identify a
client, so cookies are commonly used for session management. A cookie has a name, a
single value, and optional attributes such as a comment, path and domain qualifiers, a
maximum age, and a version number.
The getCookies() method of the request object returns an array of Cookie objects. Cookies
can be constructed using the following code:
Cookie(java.lang.String name, java.lang.String value)

# Form Processing using pearl / VBscript
Form processing using Perl and VBScript typically involves creating a web form in HTML, submitting the form data to a server, and then using the chosen scripting language to process the form data on the server side. Below are examples for form processing using Perl (CGI) and VBScript (ASP).

### Perl (CGI) Example:

Assume you have an HTML form like this:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Processing with Perl</title>
</head>
<body>

<form action="process_form.cgi" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br>

    <input type="submit" value="Submit">
</form>

</body>
</html>
```

And here's a simple Perl script (`process_form.cgi`) to process the form data:

```perl
#!/usr/bin/perl
use strict;
use warnings;

# Print the Content-type header
print "Content-type: text/html\n\n";

# Get form data
my $name  = $ENV{'QUERY_STRING'} =~ s/\+/ /gr;
my $email = <STDIN>;

# Print the processed data
print "<html><head><title>Form Processed</title></head><body>";
print "<p>Name: $name</p>";
print "<p>Email: $email</p>";
print "</body></html>";
```

In this Perl script:
- The `Content-type` header is printed to indicate that the output is HTML.
- The form data is obtained from the environment variable `QUERY_STRING` and standard input (`<STDIN>`).

### VBScript (ASP) Example:

Assume you have an HTML form like this:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Processing with VBScript</title>
</head>
<body>

<form action="process_form.asp" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br>

    <input type="submit" value="Submit">
</form>

</body>
</html>
```

And here's a simple VBScript script (`process_form.asp`) to process the form data:

```vbscript
<%
' Get form data
Dim name, email
name = Request.Form("name")
email = Request.Form("email")

' Display the processed data
Response.Write "<html><head><title>Form Processed</title></head><body>"
Response.Write "<p>Name: " & name & "</p>"
Response.Write "<p>Email: " & email & "</p>"
Response.Write "</body></html>"
%>
```

In this VBScript script:
- The `Request.Form` object is used to retrieve form data submitted with the `POST` method.
- The processed data is then displayed using the `Response.Write` method.

# I/O on WWW
Input and output operations on the World Wide Web (WWW) involve handling user interactions, receiving data from users, and presenting information to users. Here are common examples of input and output operations on the web:

### Input Operations:

1. **Form Submission:**
   - Users input data through HTML forms.
   - The data is sent to the server through HTTP methods (e.g., GET or POST).
   - Server-side scripts (e.g., PHP, Python, ASP) process the form data.

2. **User Interactions:**
   - JavaScript captures user interactions like clicks, keypresses, or mouse movements.
   - AJAX (Asynchronous JavaScript and XML) is used to send and receive data without refreshing the entire page.

3. **URL Parameters:**
   - Users can provide input via URL parameters (query strings).
   - Server-side scripts extract and process these parameters.

4. **Cookies:**
   - Users may provide input through cookies stored on their browsers.
   - Servers can read and process cookie data.

### Output Operations:

1. **HTML Rendering:**
   - Server-side scripts generate HTML dynamically based on user input or data retrieved from databases.
   - The generated HTML is sent to the user's browser for rendering.

2. **AJAX Responses:**
   - JavaScript, through AJAX requests, can receive data from the server asynchronously.
   - The received data is then dynamically updated on the page without a full reload.

3. **Server-Sent Events (SSE):**
   - The server can send real-time updates to the client using SSE.
   - Clients receive and process updates without initiating a new request.

4. **File Downloads:**
   - Servers can send files (e.g., documents, images, or media) in response to user requests.
   - File downloads are typically initiated by user interactions (e.g., clicking a download link).

5. **API Responses:**
   - Web applications often interact with APIs (Application Programming Interfaces).
   - Data from APIs is processed by the client-side code and displayed to the user.

6. **Server-side Script Output:**
   - The output of server-side scripts (e.g., PHP, Python, ASP) is sent to the client's browser.
   - This output may include dynamically generated HTML, JSON, or other formats.

# Configure Server for CGI
To configure a server to support CGI (Common Gateway Interface), you need to ensure that the server recognizes and executes CGI scripts correctly. Below are general steps for configuring a server to support CGI. Keep in mind that specific steps can vary depending on the web server software you are using (e.g., Apache, Nginx, or IIS).

### For Apache Server:

1. **Enable CGI Module:**
   - Ensure that the CGI module is enabled in Apache. You can use the `a2enmod` command to enable it:
     ```bash
     sudo a2enmod cgi
     ```

2. **Configure Directory Options:**
   - Edit your Apache configuration file (commonly located at `/etc/apache2/apache2.conf` or `/etc/httpd/httpd.conf`).
   - Ensure that the `<Directory>` directive for the CGI directory allows the execution of CGI scripts. Example:
     ```apache
     <Directory "/path/to/cgi-bin">
         AllowOverride None
         Options +ExecCGI
         AddHandler cgi-script .cgi .pl
         Require all granted
     </Directory>
     ```

3. **AddHandler for CGI Scripts:**
   - Make sure the `AddHandler` directive includes the appropriate file extensions for CGI scripts (e.g., `.cgi` and `.pl`).

4. **Check File Permissions:**
   - Ensure that CGI scripts have execute permissions. You can set the execute permission using the `chmod` command:
     ```bash
     chmod +x /path/to/cgi-bin/script.cgi
     ```

5. **Restart Apache:**
   - Restart Apache to apply the changes:
     ```bash
     sudo service apache2 restart
     ```

### For IIS (Internet Information Services):

1. **Enable CGI Feature:**
   - Open the "Server Manager."
   - Navigate to "Manage" -> "Add Roles and Features."
   - In the "Add Roles and Features Wizard," select "Web Server (IIS)" and then choose "CGI" under the "Application Development" feature.

2. **Configure CGI Settings:**
   - Open IIS Manager.
   - Select your site.
   - Open "Handler Mappings" and ensure that the CGI module is enabled for the desired file extensions (e.g., `.cgi`).

3. **Check File Permissions:**
   - Ensure that CGI scripts have execute permissions.

4. **Restart IIS:**
   - Restart IIS to apply the changes.

By following these steps, you can configure your server to support CGI scripts and execute them correctly when requested. Adjust the configuration based on the specifics of your server environment.