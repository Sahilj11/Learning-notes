
## HTTP
- HTTP can also be proxied and tunneled over other protocols
## SSL
- If the application uses SSL, this simply means that other users on the network cannot view or modify the attacker’s data in transit.

## CSRF
-   Cross-Site Request Forgery (CSRF), also known as session riding or one-click attack, is a type of security vulnerability that exploits the trust a website has in a user's browser. It occurs when an attacker tricks a victim into performing an unintended action on a web application in which the victim is authenticated.
- Here's how a CSRF attack typically works:
	1. The victim, who is authenticated on a legitimate website (e.g., a banking website), visits a malicious website controlled by the attacker.
	2. The malicious website contains crafted HTML or JavaScript code that automatically sends a request to the legitimate website in the background, without the victim's knowledge or consent.
	3. This request can be an action (e.g., transferring funds, changing account settings) that the legitimate website allows to be performed through a simple HTTP request, such as a GET or POST request.
	4. The request includes any necessary parameters or tokens required by the legitimate website, which may have been obtained by the attacker through various means (e.g., analyzing the legitimate website's source code, previous interactions with the website, or social engineering attacks).
	5. Since the victim is authenticated on the legitimate website, their browser automatically includes the necessary session cookies or authentication tokens with the malicious request, making it appear legitimate to the website.
	6. The legitimate website receives the request and processes it, unaware that it was initiated by an attacker. The action is performed on behalf of the victim, potentially leading to unauthorized actions or changes in their account.

## The Core Security Problem: Users Can Submit Arbitrary Input
- This core problem manifests itself in various ways:
	- Users can interfere with any piece of data transmitted between the client and the server, including request parameters, cookies, and HTTP headers. Any security controls implemented on the client side, such as input validation checks, can be easily circumvented.
	- Users can send requests in any sequence and can submit parameters at a different stage than the application expects, more than once, or not at all. Any assumption developers make about how users will interact with the application may be violated.
	- Users are not restricted to using only a web browser to access the application. Numerous widely available tools operate alongside, or independently of  a browser to help attack web applications. These tools can make requests that no browser would ordinarily make and can generate huge numbers of requests quickly to find and exploit problems.
- some examples of submitting crafted input to achieve this objective:
	- Changing the price of a product transmitted in a hidden HTML form field to fraudulently purchase the product for a cheaper amount
	- Modifying a session token transmitted in an HTTP cookie to hijack the session of another authenticated user 
	- Removing certain parameters that normally are submitted to exploit a logic flaw in the application’s processing 
	- Altering some input that will be processed by a back-end database to inject a malicious database query and access sensitive data

## Problem Factors
- A web application developer’s work increasingly involves weaving together tens, or even hundreds, of third-party packages, all designed to abstract the developer away from the underlying technologies.

## Mobile application interaction 
- In the context of mobile applications, there are typically two approaches to establish communication between the mobile app and the server: using a browser or a customized client that utilizes HTTP-based APIs.
- Browser-based approach: In this method, the mobile application runs within a web browser, similar to how websites are accessed on a desktop or laptop. The mobile app is essentially a web application optimized for mobile devices. It utilizes standard web technologies such as HTML, CSS, and JavaScript to create the user interface and functionality. When the mobile app needs to communicate with the server, it sends HTTP requests to the server using the browser's built-in networking capabilities. These requests can be used to retrieve data, send data, or perform other actions on the server. The server responds with HTTP responses containing the requested data or instructions for the app.
- Customized client approach: With this approach, the mobile application is developed using a programming language specific to the platform, such as Swift for iOS or Java/Kotlin for Android. The app includes a customized client component that directly communicates with the server using HTTP-based APIs. The HTTP APIs define a set of endpoints and operations that the mobile app can use to interact with the server. The app sends HTTP requests to these endpoints, specifying the desired operation and any necessary data. The server processes the request and sends back an HTTP response containing the result or any requested information.
- In both cases, HTTP (Hypertext Transfer Protocol) is used as the underlying protocol for communication between the mobile app and the server. HTTP is a widely adopted protocol for transferring data over the internet. It allows the mobile app to make requests for resources or perform actions on the server, and the server responds with the requested information or appropriate status codes.
- HTTP-based APIs provide a standardized way for the mobile app and server to communicate, regardless of the implementation details on each side. They define the structure and format of the requests and responses, including data encoding (e.g., JSON or XML) and authentication mechanisms. This standardized approach enables interoperability between different platforms and systems, allowing mobile apps to communicate with a wide range of servers and services.

## some common categories of vulnerability
### Broken authentication
- category of vulnerability encompasses various defects within the application’s login mechanism, which may enable an attacker to guess weak passwords, launch a brute-force attack, or bypass the login.

### Broken access controls
- involves cases where the application fails to properly protect access to its data and functionality, potentially enabling an attacker to view other users’ sensitive data held on the server or carry out privileged actions.

### XSS
- Cross-site scripting   This vulnerability enables an attacker to target other users of the application, potentially gaining access to their data, performing unauthorized actions on their behalf, or carrying out other attacks against them.

### Information leakage
- Information leakage This involves cases where an application divulges sensitive information that is of use to an attacker in developing an assault against the application, through defective error handling or other behavior.

