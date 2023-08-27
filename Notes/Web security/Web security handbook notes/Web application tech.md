## HTTP Requests
- The Referer header is used to indicate the URL from which the request originated (for example, because the user clicked a link on that page). Note that this header was misspelled in the original HTTP specification, and the misspelled version has been retained ever since.
- The User-Agent header is used to provide information about the browser or other client software that generated the request. Note that most browsers include the Mozilla prefix for historical reasons. This was the User- Agent string used by the originally dominant Netscape browser, and other browsers wanted to assert to websites that they were compatible with this standard. As with many quirks from computing history, it has become so established that it is still retained, even on the current version of Internet Explorer, which made the request shown in the example.

## HTTP Methods
- The GET method is designed to retrieve resources. It can be used to send parameters to the requested resource in the URL query string. This enables users to bookmark a URL for a dynamic resource that they can reuse. Or other users can retrieve the equivalent resource on a subsequent occasion (as in a bookmarked search query). URLs are displayed on-screen and are logged in various places, such as the browser history and the web server’s access logs. They are also transmitted in the Referer header to other sites when external
- links are followed. For these reasons, the query string should not be used to transmit any sensitive information.
- The POST method is designed to perform actions. With this method, request parameters can be sent both in the URL query string and in the body of the message. Although the URL can still be bookmarked, any parameters sent in the message body will be excluded from the bookmark. These parameters will also be excluded from the various locations in which logs of URLs are maintained and from the Referer header. Because the POST method is designed for performing actions, if a user clicks the browser’s Back button to return to a page that was accessed using this method, the browser does not automatically reissue the request. Instead, it warns the user of what it is about to do, as shown in Figure 3-1. This prevents users from unwittingly performing an action more than once. For this reason, POST requests should always be used when an action is being performed.
	- ![[Pasted image 20230616151114.png]]
- The TRACE method in HTTP (Hypertext Transfer Protocol) is designed for diagnostic purposes. When a client sends a TRACE request to a server, the server should respond by returning the exact contents of the request message it received in the response body. The purpose of this feature is to allow clients to verify if any intermediary proxy servers between the client and the server are altering or modifying the request. Proxy servers are commonly used to enhance security, improve performance, or provide caching functionalities. However, in some cases, a proxy server may unintentionally modify the request, leading to unexpected behavior or errors. By including the original request in the response body, the client can compare it with the request it initially sent. If there are any differences, it indicates that one or more proxy servers have altered the request. This information can be valuable for diagnosing and troubleshooting issues related to request manipulation by proxies. It's worth noting that the TRACE method can introduce security risks if not used carefully. Since it reveals the exact contents of the request in the response, it can potentially expose sensitive information. Therefore, TRACE should be used judiciously and only in controlled environments or during diagnostic procedures. In most production scenarios, TRACE is typically disabled or not supported to mitigate security vulnerabilities.
- OPTIONS asks the server to report the HTTP methods that are available for a particular resource. The server typically returns a response containing an Allow header that lists the available methods.
- PUT attempts to upload the specifi ed resource to the server, using the content contained in the body of the request. If this method is enabled, you may be able to leverage it to attack the application, such as by uploading an arbitrary script and executing it on the server

## URL
- A uniform resource locator (URL) is a unique identifier that specifies the location of a web resource. It allows us to retrieve the resource by providing a standardized format. Most URLs follow a specific structure:
```
protocol://hostname[:port]/[path/]file[?param=value]

```
- Let's break down the components of this URL structure:
	- **Protocol:** It specifies the communication protocol to be used when accessing the resource. In the given example, the protocol is "https," which indicates the use of the HTTP protocol over a secure connection (HTTP Secure).
	- **Hostname:** It represents the domain name or IP address of the server hosting the resource. In the example URL, the hostname is "mdsec.net."
	- **Port:** This component is optional and only included if the resource is served on a non-default port for the protocol. If no port is specified, the default port for the protocol is assumed. In the example, the port is not explicitly mentioned, so the default port for HTTPS (port 443) is used.
	- **Path:** It specifies the directory or path on the server where the resource is located. In the example URL, the path is "/auth/488/".
	- **File:** It indicates the specific file or resource name that needs to be retrieved. In the given URL, the file is "YourDetails.ashx".
	- **Parameters:** This component is optional and appears after the question mark "?". It consists of key-value pairs separated by an equal sign. These parameters provide additional information or data to the server. In the example, the parameter is "uid=129"
- Relative URLs are URLs that are specified in relation to the current page or location within a website or application. They provide a concise way to reference resources within the same domain or path without explicitly stating the full URL.
- Relative URLs can be categorized into three types:
	- 1. **Root-relative URLs**: These URLs begin with a forward slash (/) and are relative to the root directory of the website. They are used to reference resources from the root, regardless of the current location. For example:
	    - `/about-us.html`: This URL references the "about-us.html" file located in the root directory of the website.
	    - `/images/logo.png`: This URL references the "logo.png" image file located in the "images" directory in the root.
	2. **Document-relative URLs**: These URLs are relative to the current document or page. They are used to reference resources within the same directory or subdirectory as the current page. For example:
	    - `styles/main.css`: This URL references the "main.css" file located in the "styles" directory within the current directory.
	    - `../images/pic.jpg`: This URL references the "pic.jpg" image file located in the "images" directory, one level up from the current directory.
	3. **Relative URLs with anchor tags**: These URLs are used for internal page linking within the same document. They reference specific sections or elements within the current page by using an anchor tag (#) followed by the target element's ID. For example:
	    - `#section1`: This URL references the element with the ID "section1" within the current page.
	    - `#top`: This URL references the element with the ID "top" to scroll the page to the top.
## REST
- Representational State Transfer (REST) is an architectural style that provides a set of guidelines for designing web services and distributed systems. It focuses on simplicity, scalability, and ease of communication between different components within a networked environment.
- REST is based on a few key principles:
	1. **Stateless Communication**: REST is stateless, meaning that each request from a client to a server contains all the necessary information for the server to understand and process that request. The server does not retain any knowledge of the client's previous requests or interactions. This simplifies the design and scalability of the system since each request can be handled independently.
	2. **Resource-Oriented**: REST treats everything as a resource, which can be thought of as any information or entity that can be accessed through a unique identifier. Resources can be things like documents, images, or data records. Each resource is identified by a unique URL (Uniform Resource Locator). Clients can interact with these resources by sending requests to the server, typically using the HTTP protocol.
	3. **Uniform Interface**: REST defines a uniform set of operations or methods that can be performed on resources. These operations are standard HTTP methods such as GET, POST, PUT, DELETE, etc. Each method has a specific purpose, such as retrieving a resource, creating a new resource, updating an existing resource, or deleting a resource.
	4. **Representation of Resources**: REST emphasizes the use of representations to convey the state of a resource. When a client requests a resource, the server responds with a representation of that resource, which can be in various formats such as XML, JSON, or HTML. The client and server communicate by exchanging these representations, allowing the client to understand and manipulate the resource's state.
- By following these principles, REST enables systems to be loosely coupled, scalable, and interoperable. It promotes separation of concerns, where different components can evolve independently as long as they adhere to the agreed-upon conventions of the REST architecture. This makes it easier to build and integrate various components within a distributed system, including web services, APIs, and other networked applications.

### REST API
- A REST API (Application Programming Interface) is a set of rules and conventions that allows different software applications to communicate with each other over the internet. It serves as a bridge that enables one application to access and interact with the functionalities and data of another application or service.
- In the context of REST, an API is designed based on the principles of the REST architecture. It exposes a collection of resources, typically in the form of URLs (Uniform Resource Locators), that represent different entities or services. These resources can be accessed and manipulated using standard HTTP methods such as GET, POST, PUT, DELETE, and others.
- A REST API works by defining a set of endpoints, each representing a specific resource or functionality. Clients, which can be web browsers, mobile applications, or other software systems, send HTTP requests to these endpoints to perform operations on the resources.
- For example, let's say we have an online store with a REST API. It might have endpoints like:
	- `/products`: to retrieve a list of products or create a new product
	- `/products/{id}`: to get, update, or delete a specific product identified by its ID
	- `/orders`: to place an order or retrieve a list of orders
	- `/customers`: to manage customer information
- To interact with this API, a client application can make requests to these endpoints using the appropriate HTTP methods. For instance, a GET request to `/products` might retrieve a list of all available products, while a POST request to `/orders` could create a new order.
- The API would respond to these requests with the corresponding HTTP status codes (such as 200 for success or 404 for resource not found) and provide data in a format like JSON or XML. Clients can then parse and process the response to extract the necessary information.
- REST APIs are widely used in modern web development and enable different applications to integrate and interact seamlessly. They provide a standardized way for systems to communicate, allowing developers to build modular and interconnected software solutions.
- In RESTful architecture, URLs are used to identify and locate resources. Typically, when we want to pass parameters in a URL, we use the query string, which is a part of the URL after the question mark (?). However, there is an alternative approach called "REST-style URL" where parameters are included in the file path itself rather than the query string.
- Let's take an example to understand this better. Consider a car search application where you can search for cars based on their make and model. In a traditional URL, you might see something like this:
```
http://wahh-app.com/search?make=ford&model=pinto

```
- In this example, the query string parameters are `make` and `model`, and their values are `ford` and `pinto`, respectively. The server would use these parameters to perform the search and return the appropriate results.
- However, in a "REST-style" URL, the parameters are embedded in the file path itself. So the same car search URL would look like this:
```
http://wahh-app.com/search/ford/pinto

```
- In this REST-style URL, the parameters `make` and `model` are directly included in the file path, separated by slashes. This alternative approach is often used in RESTful systems because it aligns with the idea of treating everything as a resource.
- Both the traditional query string approach and the REST-style approach are valid and can be used in RESTful systems. The choice between them often depends on factors like personal preference, system design, and the conventions followed in the specific application or API.
### GraphQL
- GraphQL is like a special language that helps computers talk to each other and share information. Just imagine you have a magic notebook where you can write down questions and get specific answers back.
- In normal computer communication, you send a request to a server and get a response with all the information available. It's like getting a big book with all the pages, even if you only need a few.
- But with GraphQL, it's different. You can ask the server for exactly what you want, and it will only give you that information. It's like writing a question in your magic notebook and getting a specific answer back.
- For example, let's say you want to know the names of your friends' favorite animals. With normal communication, you would ask for all the information about your friends and their animals, and you would have to go through it all to find what you want.
- But with GraphQL, you can write a question like, "What are the names of my friends' favorite animals?" And the server will give you back just the names of the animals, without any extra stuff.
- This makes communication faster and more efficient because you get only the information you need. It's like having a personalized conversation with the server, asking for exactly what you want to know.
- GraphQL is used in many websites and apps to make communication between computers more flexible and precise. It helps developers build better and faster applications by getting only the data they need, without any extra clutter.
### URL difference 
- Sure! Here are examples of a GraphQL URL and a REST URL:
1. **GraphQL URL**:
```
https://api.example.com/graphql
```
- In GraphQL, there is typically a single endpoint, often represented by `/graphql`, where all the requests are sent. Instead of using different URLs for different resources, GraphQL uses a single URL to send queries and mutations (requests for data retrieval or modification) to the server.
- **REST URL**:
```
https://api.example.com/users

```
- In REST, URLs are structured based on the resources and the actions you want to perform on them. In this example, the URL `https://api.example.com/users` represents the "users" resource. You would typically use different URLs for different resources and actions. For example, you might have `https://api.example.com/products` for products, `https://api.example.com/orders` for orders, and so on.
- It's important to note that while GraphQL uses a single endpoint for all requests, the actual data being retrieved or modified is specified within the body of the GraphQL query or mutation. In contrast, REST URLs often represent specific resources or collections of resources, and the actions are determined by the HTTP methods (GET, POST, PUT, DELETE) used along with the URL

## HTTP Headers 
#### General Headers (can be used as response or request)
- Connection tells the other end of the communication whether it should close the TCP connection after the HTTP transmission has completed or keep it open for further messages.
- Content-Encoding specifies what kind of encoding is being used for the content contained in the message body, such as gzip, which is used by some applications to compress responses for faster transmission.
- Content-Length specifies the length of the message body, in bytes (except in the case of responses to HEAD requests, when it indicates the length of the body in the response to the corresponding GET request).
- Content-Type specifies the type of content contained in the message body, such as text/html for HTML documents.
- Transfer-Encoding specifies any encoding that was performed on the message body to facilitate its transfer over HTTP. It is normally used to specify chunked encoding when this is employed.
	- The Transfer-Encoding header is an HTTP header field used to indicate the encoding scheme applied to the message body in an HTTP transaction. It specifies how the payload data is encoded or transformed before it is sent over the network. This header is typically used when the server wants to send the response in a different encoding format than the default "Content-Length" encoding.
		The Transfer-Encoding header can have multiple values, indicating a chain of encodings applied to the message body. Some common transfer encodings include:
		1. Chunked: This encoding divides the message body into a series of chunks. Each chunk is accompanied by its size, allowing the recipient to read and reconstruct the message body. Chunked encoding is useful when the server doesn't know the full size of the response in advance or wants to transmit the response progressively.
		2. Gzip: This encoding uses the gzip compression algorithm to compress the message body before transmitting it. Gzip compression reduces the size of the payload, improving network efficiency and reducing bandwidth usage.
		3. Deflate: Similar to gzip, deflate is another compression algorithm used to reduce the size of the message body. It provides a more efficient compression algorithm compared to gzip in some cases.
		When the Transfer-Encoding header is present in an HTTP response, the recipient (usually a web browser or client application) should apply the specified encoding to decode the message body and retrieve the original content. The header is not limited to responses only and can also be used in requests, although it is less common.
		It's important to note that the Transfer-Encoding header takes precedence over the Content-Length header. If both headers are present, the recipient should ignore the Content-Length header and use the transfer encoding specified in the Transfer-Encoding header to determine the message body's length.
		Overall, the Transfer-Encoding header provides flexibility for servers to apply various encoding schemes to the message body, allowing for efficient data transmission and compression in HTTP transactions.

#### Request Headers
- Accept tells the server what kinds of content the client is willing to accept, such as image types, office document formats, and so on.
- Accept-Encoding tells the server what kinds of content encoding the client is willing to accept.
- Authorization submits credentials to the server for one of the built-in HTTP authentication types.
- Cookie submits cookies to the server that the server previously issued.
- Host specifies the hostname that appeared in the full URL being requested.
- In the two ways described, these headers are used to support caching of content within the browser, and they enable the server to instruct the browser to use a cached copy of a resource, rather than responding with the full contents of the resource if this is not necessary.
- When you are attacking an application, your browser may already have cached copies of resources that you are interested in, such as JavaScript files. By removing these two headers, you can override the browser’s caching information and ensure that the server responds with a fresh copy of the resource you wish to view.
- The If-Modified-Since header is used to specify the time at which the browser last received the requested resource.
- The If-None-Match header is used to specify the entity tag that the server issued with the requested resource when it was last received.
	- When a browser requests a resource from a server, it includes the entity tag associated with the cached copy of that resource in the If-None-Match header of the request. The entity tag is a unique identifier that was issued by the server when the resource was last received by the browser.
	- Upon receiving the request, the server can compare the entity tag in the If-None-Match header with the current entity tag of the requested resource. If the two entity tags match, it means that the browser's cached copy is still up to date and can be used. In this case, the server can respond with a "304 Not Modified" status code, indicating that the resource has not changed since the last request. The server doesn't send the actual resource again, saving bandwidth and reducing latency.
	- On the other hand, if the entity tags do not match, it means that the resource has been modified on the server since the browser last received it. In this case, the server will provide the updated resource in the response, along with a new entity tag for caching purposes.
	- By utilizing the If-None-Match header and entity tags, the browser and server can efficiently determine whether the cached copy of a resource is still valid or if it needs to be updated. This helps in reducing unnecessary data transfer and improves the overall performance of web applications.
- Origin is used in cross-domain Ajax requests to indicate the domain from which the request originated (see Chapter 13).
	- The Origin header is a part of the HTTP protocol that is used in cross-domain Ajax [[Web developement/Backend/API#AJAX]](Asynchronous JavaScript and XML) requests to indicate the domain from which the request originated. It plays a crucial role in enforcing the same-origin policy, which is a security measure implemented by web browsers to restrict cross-domain interactions.
	- The same-origin policy states that web pages can only make requests to the same domain from which they were loaded. This policy prevents malicious scripts on one website from accessing sensitive information or performing actions on other websites without explicit permission.
	- When a web page initiates an Ajax request to a different domain, the browser includes the Origin header in the request. The value of the Origin header is the domain (including the scheme and port) from which the request is being sent. This indicates the source or the "origin" of the request.
	- The server that receives the request can then use the Origin header to determine if it allows the request to be processed. The server can check the Origin header against a list of allowed domains or implement more complex logic to determine whether the request should be permitted. This process is known as Cross-Origin Resource Sharing (CORS).
	- If the server determines that the request is allowed, it includes specific CORS headers in the response to inform the browser that the requested resource can be accessed from a different domain. These CORS headers typically include Access-Control-Allow-Origin, which specifies the allowed origins, and possibly other headers to control the behavior of cross-domain requests.
	- However, if the server determines that the request is not allowed based on the Origin header, it can send back a response with an appropriate error status code or specific headers indicating that the request is forbidden.
	- In summary, the Origin header in cross-domain Ajax requests provides information about the domain from which the request originated. It helps enforce the same-origin policy and enables servers to control access to their resources from different domains through the implementation of CORS.
- Refererspecifies the URL from which the current request originated.
- User-Agent provides information about the browser or other client software that generated the request.

#### Response Headers
- Access-Control-Allow-Origin indicates whether the resource can be retrieved via cross-domain Ajax requests (see Chapter 13).
- Cache-Control passes caching directives to the browser (for example, no-cache).
- ETag specifies an entity tag. Clients can submit this identifier in future requests for the same resource in the If-None-Match header to notify the server which version of the resource the browser currently holds in its cache.
- Expires tells the browser for how long the contents of the message body are valid. The browser may use the cached copy of this resource until this time.
- Location is used in redirection responses (those that have a status code starting with 3) to specify the target of the redirect.
- Pragma passes caching directives to the browser (for example, no-cache). Server provides information about the web server software being used.
- Set-Cookie issues cookies to the browser that it will submit back to the server in subsequent requests.
- WWW-Authenticate is used in responses that have a 401 status code to provide details on the type(s) of authentication that the server supports.
- X-Frame-Options indicates whether and how the current response maybe loaded within a browser frame.
	- The X-Frame-Options header is an HTTP response header that helps to protect web pages against clickjacking attacks. Clickjacking is a malicious technique where an attacker tricks a user into clicking on a disguised or invisible element on a web page, potentially leading to unintended actions or unauthorized access.
		The X-Frame-Options header allows a website to specify whether and how the current page can be loaded within a browser frame or iframe on another website. It provides three possible values:
		1. DENY: This setting indicates that the page should not be displayed in any frame, regardless of the site attempting to embed it. If a user tries to load the page within a frame, the browser will refuse to display it.
		2. SAMEORIGIN: With this setting, the page can only be displayed in a frame on the same origin. The "origin" refers to the combination of protocol, domain, and port. For example, if a page with this setting is hosted on "example.com," it can be embedded in a frame on a page also served from "example.com" but not on a page from a different origin.
		3. ALLOW-FROM uri: This setting allows the page to be displayed in a frame on the specified URI. For example, if the header is set to "ALLOW-FROM https://example.com," the page can be embedded in a frame on any page served from "https://example.com."
		By using the X-Frame-Options header, website owners can control how their pages are embedded in other sites. This helps prevent clickjacking attacks by restricting unauthorized framing and protecting the integrity and security of the content. Modern web standards recommend using the Content-Security-Policy (CSP) header with the "frame-ancestors" directive instead of X-Frame-Options, as it offers more fine-grained control over framing policies.
	The Content-Security-Policy (CSP) header is an HTTP response header that allows website owners to specify and enforce a set of security policies for their web pages. CSP is designed to mitigate various types of attacks, such as cross-site scripting (XSS), clickjacking, and data injection attacks.
	When the browser receives a web page with the CSP header, it applies the specified security policies to limit or control the types of content and interactions allowed on the page. These policies are defined using a set of directives within the header.
	Here are some commonly used directives in the Content-Security-Policy header:
	1. default-src: This directive specifies the default source for all types of content (e.g., scripts, stylesheets, images) if a specific directive is not defined for a particular content type.
	2. script-src: This directive controls which sources are allowed to execute JavaScript code on the page, including inline scripts and external script files.
	3. style-src: This directive determines which sources can be used for loading stylesheets or embedding inline styles.
	4. img-src: This directive specifies the allowed sources for loading images on the page.
	5. connect-src: This directive governs the permitted sources for making network requests, such as XMLHttpRequest or fetch API calls.
	6. frame-src: This directive controls the sources that can be used to embed the page within an iframe or frame.
	7. font-src: This directive determines the allowed sources for loading web fonts.
	8. media-src: This directive specifies the permitted sources for loading media elements, such as audio or video files.
	These are just a few examples of the directives available in CSP. The CSP header can also include other directives, such as object-src, child-src, form-action, and more, allowing fine-grained control over different aspects of the page's content and interactions	
	By implementing a Content-Security-Policy, website owners can define a strict security policy that restricts the origin of content and prevents the execution of malicious scripts or the loading of unauthorized resources. CSP is an effective security mechanism to protect web applications and mitigate the risk of various types of attacks.

### Cookies
- Cookies normally consist of a name/value pair, as shown, but they may consist of any string that does not contain a space. Multiple cookies can be issued by using multiple Set-Cookie headers in the server’s response. These are submitted back to the server in the same Cookie header, with a semicolon separating different individual cookies. In addition to the cookie’s actual value, the Set-Cookie header can include any of the following optional attributes, which can be used to control how the browser handles the cookie:
	- expires sets a date until which the cookie is valid. This causes the browser to save the cookie to persistent storage, and it is reused in subsequent browser sessions until the expiration date is reached. If this attribute is not set, the cookie is used only in the current browser session.
	- domain specifi es the domain for which the cookie is valid. This must be the same or a parent of the domain from which the cookie is received.
	- path specifi es the URL path for which the cookie is valid.
	- secure — If this attribute is set, the cookie will be submitted only in HTTPS requests.
	- HttpOnly — If this attribute is set, the cookie cannot be directly accessed via client-side JavaScript.
		- Setting an HTTP-only cookie has several advantages in terms of security, but it also has a potential disadvantage:
			- Limited accessibility: The main disadvantage of setting an HTTP-only cookie is that it cannot be accessed or modified by client-side JavaScript code. This is actually one of the key security benefits of HTTP-only cookies, as it helps mitigate the risk of cross-site scripting (XSS) attacks. However, in certain scenarios where client-side scripts need to read or modify the cookie, the HTTP-only restriction can become a limitation.
			- For example, if you have a web application that relies heavily on JavaScript for dynamic functionality and requires access to the cookie data, setting the HTTP-only flag would prevent client-side scripts from accessing or modifying the cookie. This can impact the functionality or require additional server-side workarounds.
			- It's important to strike a balance between security and functionality when deciding to set a cookie as HTTP-only. In cases where the cookie data needs to be accessed or modified by client-side scripts, alternative security measures or careful consideration of the cookie's scope may be required.
			- It's worth noting that the advantages of using HTTP-only cookies, such as mitigating XSS attacks and protecting sensitive information, often outweigh the disadvantages. Therefore, it is generally recommended to set cookies as HTTP-only unless there is a specific need for client-side script access
## HTTP Proxies
- An HTTP proxy is a server that mediates access between the client browser and the destination web server. When a browser has been configured to use a proxy
- server, it makes all its requests to that server. The proxy relays the requests to the relevant web servers and forwards their responses back to the browser. Most proxies also provide additional services, including caching, authentication, and access control.
- You should be aware of two differences in how HTTP works when a proxy server is being used:
	- When a browser issues an unencrypted HTTP request to a proxy server, it places the full URL into the request, including the protocol prefix http://, the server’s hostname, and the port number if this is nonstandard. The proxy server extracts the hostname and port and uses these to direct the request to the correct destination web server.
	- When HTTPS is being used, the browser cannot perform the SSL handshake with the proxy server, because this would break the secure tunnel and leave the communications vulnerable to interception attacks. Hence, the browser must use the proxy as a pure TCP-level relay, which passes all network data in both directions between the browser and the destination web server, with which the browser performs an SSL handshake as normal. To establish this relay, the browser makes an HTTP request to the proxy server using the CONNECT method and specifying the destination hostname and port number as the URL. If the proxy allows the request, it returns an HTTP response with a 200 status, keeps the TCP connection open, and from that point onward acts as a pure TCP-level relay to the destination web server.
		- **what does this means?**
			- From the perspective of a web proxy, it acts as an intermediary between the client and the server. When the client establishes an SSL/TLS connection, the proxy receives the encrypted data but cannot decrypt it because it doesn't possess the necessary private key.
			- While the web proxy can see the metadata (e.g., destination IP addresses, domain names) of the SSL/TLS traffic, it cannot access or inspect the actual content of the encrypted data without the private key associated with the SSL/TLS certificate. This provides a level of confidentiality and privacy for the transmitted data, even when passing through a web proxy.
			- When a browser communicates with a web server over a secure connection using SSL/TLS (Secure Sockets Layer/Transport Layer Security), it establishes a secure tunnel to encrypt the data and protect it from interception or tampering. However, when a proxy server is involved in the connection, the SSL handshake between the browser and the destination web server cannot be performed through the proxy.
			- The reason is that the SSL handshake process involves exchanging cryptographic keys and certificates between the client (browser) and the server (destination web server) to establish a secure connection. If the SSL handshake were to be performed with the proxy server instead of the destination web server, it would break the secure tunnel and make the communication vulnerable to interception attacks. The proxy server would have access to the cryptographic keys, enabling it to decrypt and potentially intercept or modify the data exchanged between the browser and the web server.
			- To maintain the security of the communication, the browser treats the proxy server as a pure TCP-level relay. This means that the browser establishes a normal, unencrypted connection with the proxy server. The browser then sends the encrypted SSL/TLS traffic to the proxy server, which acts as a middleman, relaying the network data in both directions between the browser and the destination web server.
			- The proxy server, functioning at the TCP level, does not interfere with the SSL/TLS encryption or perform any SSL-related operations. It simply forwards the encrypted data between the browser and the destination web server without decrypting or inspecting its contents. The destination web server receives the encrypted data and performs the SSL handshake with the browser as usual, establishing a secure connection.
			- By utilizing this relay approach, the browser can maintain the security of the SSL/TLS connection while still using the proxy server for intermediary routing or caching purposes.
		- Further explanation
			- When the browser interacts with a proxy server, it treats it as a "pure TCP-level relay." This means that the browser communicates with the proxy server at a basic network level without involving any higher-level protocols or security mechanisms, such as SSL/TLS.
			- In this context, "TCP-level" refers to the Transmission Control Protocol (TCP), which is a fundamental protocol used for reliable data transmission over the internet. TCP provides a reliable, ordered, and error-checked connection between two endpoints, ensuring that data sent from one side is correctly received by the other side.
			- Treating the proxy server as a TCP-level relay implies that the browser establishes a standard TCP connection with the proxy server. This connection is typically unencrypted and lacks the additional security measures provided by protocols like SSL/TLS.
			- Instead of performing SSL/TLS handshakes and encryption with the proxy server, the browser uses the proxy server solely for routing network data. It sends and receives data packets through the proxy server, which then relays them to the intended destination web server.
			- In this scenario, any encryption and security measures are applied directly between the browser and the destination web server, without involving the proxy server. The browser establishes a separate secure connection with the destination web server using SSL/TLS. This allows the browser to maintain the confidentiality and integrity of the data while bypassing the limitations of performing SSL/TLS with the proxy server.
			- By treating the proxy server as a pure TCP-level relay, the browser can leverage the proxy's capabilities for routing or caching purposes while still ensuring secure communication with the destination web server.
		- TLS Handshake
			- ![[Pasted image 20230621142516.png]]
			- ![[Pasted image 20230621142800.png]]
			- ![[Pasted image 20230621143004.png]]
			- ![[Pasted image 20230621143206.png]]
			- ![[Pasted image 20230621143350.png]]
			- both client and server have all four keys
			- 
			- The SSL handshake is a process that occurs when a client (such as a web browser) and a server establish a secure encrypted connection using the SSL/TLS protocol. It involves a series of steps and exchanges of messages between the client and the server to negotiate and establish the parameters of the secure connection. Here is a high-level overview of the SSL handshake process:
				1. Client Hello: The client initiates the handshake by sending a Client Hello message to the server. This message includes information such as the highest SSL/TLS version supported by the client, a list of cipher suites (encryption algorithms) it can use, and a random value called the client random.    
				2. Server Hello: The server responds with a Server Hello message. This message contains the chosen SSL/TLS version, the selected cipher suite from the client's list, a random server random value, and the server's digital certificate (which contains its public key).
				3. Certificate Validation: The client verifies the authenticity and validity of the server's digital certificate. It checks if the certificate is issued by a trusted Certificate Authority (CA) and whether it is still valid. The client may also verify that the domain name in the certificate matches the server it is connecting to.		    
				4. Key Exchange: If the certificate is valid, the client generates a random value called the pre-master secret. It encrypts the pre-master secret with the server's public key (from the digital certificate) and sends it to the server	    
				5. Session Key Generation: Both the client and the server independently derive the session key (symmetric encryption key) from the client random, server random, and the pre-master secret. This ensures that only the client and server have the knowledge of the session key.
				6. Handshake Completion: At this point, both the client and the server have the session key. They exchange messages to notify each other that the handshake is complete. From this point onwards, all data transmitted between the client and the server is encrypted using the shared session key.
			- Once the handshake is complete, the client and server can securely communicate by encrypting and decrypting data using symmetric encryption with the session key. The SSL/TLS protocol also provides mechanisms for data integrity and authentication to ensure the security and integrity of the communication.
## HTTP Authentication
- The HTTP protocol includes its own mechanisms for authenticating users using various authentication schemes, including the following:
	- Basic is a simple authentication mechanism that sends user credentials as a Base64-encoded string in a request header with each message.
	- NTLM is a challenge-response mechanism and uses a version of the Windows NTLM protocol.
	- Digest is a challenge-response mechanism and uses MD5 checksums of a nonce with the user’s credentials.

## Server side functionality
- HTTP requests can be used to send parameters to the application in three main ways:
	- In the URL query string
	- In the file path of REST-style URLs
	- In HTTP cookies
	- In the body of requests using the POST method
#### Java
- Enterprise java beans:- Imagine you have a big company with lots of employees. Each employee has their own tasks and responsibilities, right? Some employees work in sales, some in marketing, some in finance, and so on.
	- Enterprise Java Beans is like a set of rules and tools that help organize and manage all these employees efficiently. It provides a way to write software components that can be reused and shared across different parts of the company.
	- These software components, called EJBs, are like small programs or building blocks that perform specific tasks. They are created using the Java programming language. Just like how Lego pieces can be used to build different structures, EJBs can be combined and used to build different software applications for the company.
	- EJBs can do things like handling customer information, managing inventory, processing financial transactions, or sending emails. They are designed to work together and follow certain rules, so they can easily communicate with each other and share information.
	- The benefit of using EJBs is that it makes the company's software development process more efficient. Instead of writing everything from scratch, developers can reuse existing EJBs and focus on specific tasks. It saves time and effort.
	- EJBs also provide extra features like security, transaction management, and scalability. These features help ensure that the software runs smoothly, handles large amounts of data, and keeps everything secure.
	- So, to sum it up, Enterprise Java Beans is like a set of rules and tools that help organize and manage software components (EJBs) in a big company. It makes software development more efficient and allows different parts of the company to work together seamlessly.
- some examples of components commonly used for key application functions:
	- Authentication — JAAS, ACEGI
	- Presentation layer — SiteMesh, Tapestry
	- Database object relational mapping — Hibernate
	- Logging — Log4J
#### PHP
- Many of these provide off-the-shelf solutions for common application functions, which are often incorporated into wider custom-built applications:
	- Bulletin boards — PHPBB, PHP-Nuke
	- Administrative front ends — PHPMyAdmin
	- Web mail — SquirrelMail, IlohaMail
	- Photo galleries — Gallery
	- Shopping carts — osCommerce, ECW-Shop
	- Wikis — MediaWiki, WakkaWikki
#### Forms
- ![[Pasted image 20230618101748.png]]
- The preceding request contains a header specifying that the type of content in the message body is x-www-form-urlencoded. This means that parameters are represented in the message body as name/value pairs in the same way as they are in the URL query string. The other content type you are likely to encounter when form data is submitted is multipart/form-data. An application can request that browsers use multipart encoding by specifying this in an enctype attribute in the form tag. With this form of encoding, the Content-Type header in the request also specifies a random string that is used as a separator for the parameters contained in the request body. For example, if the form specified multipart encoding, the resulting request would look like the following:
#### Urlencoded vs multipart encoding 
- When a request contains the header specifying "content-type: application/x-www-form-urlencoded", it means that the data sent in the message body is encoded using the x-www-form-urlencoded format. In this format, the parameters (or form fields) are represented as name/value pairs, similar to how they appear in the URL query string. For example, if you have a form with fields "username" and "password" and the user enters "john" and "secret123" respectively, the encoded form data would look like this:`username=john&password=secret123`
- In this format, the parameter names and values are URL-encoded to handle special characters. On the other hand, when a form specifies "enctype: multipart/form-data", it means that the form data will be encoded using the multipart encoding scheme. In this case, the Content-Type header in the request will also contain a random string that acts as a separator for the parameters within the request body.
- Multipart encoding is typically used when the form includes file uploads. The parameters and file data are split into separate sections within the message body, and each section is identified by a unique boundary string specified in the Content-Type header.
- For example, the Content-Type header for a multipart form request might look like this:`Content-Type: multipart/form-data; boundary=---------------------------1234567890`
- The boundary string ("---------------------------1234567890" in this example) separates different parts of the form data. Each part consists of a header section followed by the actual data.
- Multipart encoding allows for more complex form submissions that include files or other binary data. It provides a way to encapsulate and distinguish different form components within the request body.
#### Multipart encoding
- Let's say you have a form with two fields: "name" and "profile picture". The user enters their name as "John Doe" and uploads a profile picture file named "profile.jpg".
- When the form is submitted, the data will be encoded using multipart/form-data. Here's an example of how the request might look:
```
POST /submit-form HTTP/1.1
Host: example.com
Content-Type: multipart/form-data; boundary=---------------------------1234567890

-----------------------------1234567890
Content-Disposition: form-data; name="name"

John Doe
-----------------------------1234567890
Content-Disposition: form-data; name="profile_picture"; filename="profile.jpg"
Content-Type: image/jpeg

...binary data of the profile picture...
-----------------------------1234567890--

```
- In this example:
	1. The Content-Type header specifies "multipart/form-data" as the encoding type, and the boundary string is "---------------------------1234567890".
	2. Each part of the form data is separated by the boundary string. The boundary string is included as a delimiter before each part and also at the end of the request body with "--" appended.
	3. The first part represents the "name" field and has the value "John Doe". It includes a Content-Disposition header with the field name.
	4. The second part represents the "profile_picture" field, which contains the uploaded file "profile.jpg". It includes a Content-Disposition header with the field name, the filename of the uploaded file, and the Content-Type of the file (in this case, "image/jpeg"). The binary data of the file would be present after the headers.
- This multipart encoding allows the server to differentiate between different parts of the form data and handle file uploads appropriately.
## Encoding schemes
### URL encoding 
- URLs are permitted to contain only the printable characters in the US-ASCII character set — that is, those whose ASCII code is in the range 0x20 to 0x7e, inclusive. Furthermore, several characters within this range are restricted because they have special meaning within the URL scheme itself or within the HTTP protocol.
- The URL-encoding scheme is used to encode any problematic characters within the extended ASCII character set so that they can be safely transported over HTTP. The URL-encoded form of any character is the % prefix followed by the character’s two-digit ASCII code expressed in hexadecimal. Here are some characters that are commonly URL-encoded:
- A further encoding to be aware of is the + character, which represents a URL-encoded space (in addition to the %20 representation of a space).
- In the case of spaces, they are not allowed in URLs as they are treated as separators between different parts of a URL. To represent a space in a URL, URL encoding replaces it with either the "%20" sequence or the plus sign "+".
- The "%20" sequence is the most common way to represent a space in URL encoding. Each percent sign "%" is followed by two hexadecimal digits that represent the ASCII code of the character being encoded. In this case, "%20" represents the ASCII code for a space character (32 in decimal).
- When it comes to attacking web applications, it's important to be mindful of how certain characters are interpreted and processed by the server. By URL encoding specific characters, you can potentially manipulate or bypass security measures, inject malicious code, or disrupt the intended functionality of the application.
	- Space: URL encoding a space character is necessary because unencoded spaces are typically treated as separators between different parts of a request, such as the path or query parameters. URL encoding a space converts it to "%20" or "+" (as mentioned earlier) to ensure it is correctly interpreted as data rather than a delimiter.
	- . %, ?, &, =, ;, +, and #: These characters have special meanings in URL syntax. For example, the percent sign "%" is used to encode reserved or unsafe characters. The question mark "?" is used to separate the path from the query parameters. The ampersand "&" and equal sign "=" are used to separate and assign values to query parameters. The semicolon ";" is sometimes used as a separator in specific contexts. The plus sign "+" has the special meaning of representing a space in certain parts of a URL. The hash or pound sign "#" is typically used for fragment identifiers
### Unicode Encoding
- the %u prefix followed by the character’s Unicode code point expressed in hexadecimal:
	- %u2215 — /
	- %u00e9 — é
- For the purpose of attacking web applications, Unicode encoding is primarily of interest because it can sometimes be used to defeat input validation mechanisms. If an input fi lter blocks certain malicious expressions, but the component that subsequently processes the input understands Unicode encoding, it may be possible to bypass the fi lter using various standard and malformed Unicode encodings.
### HTML Encoding
- HTML encoding is used to represent problematic characters so that they can be safely incorporated into an HTML document. Various characters have special meaning as metacharacters within HTML and are used to defi ne a document’s structure rather than its content. To use these characters safely as part of the document’s content, it is necessary to HTML-encode them. HTML encoding defi nes numerous HTML entities to represent specifi c literal characters:
	- &quot; — "
	- &apos; — '
	- &amp; — &
	- &lt; — <
	- &gt; — >
- In addition, any character can be HTML-encoded using its ASCII code in decimal form:
	- &#34; — "
	- &#39; — '
- or by using its ASCII code in hexadecimal form (prefi xed by an x):
	- &#x22; — "
	- &#x27; — '
- When you are attacking a web application, your main interest in HTML encoding is likely to be when probing for cross-site scripting vulnerabilities. If an application returns user input unmodifi ed within its responses, it is probably vulnerable, whereas if dangerous characters are HTML-encoded, it may be safe.
	- If a web application returns user input without any modification or HTML encoding within its responses, it indicates a potential vulnerability. This means that any malicious script or HTML code injected by an attacker as part of the user input would be reflected directly in the response, allowing it to be executed by the client-side browser. This scenario is commonly known as a **"reflected XSS" vulnerability.**
	- On the other hand, if a web application applies HTML encoding to user input before including it in its responses, it suggests that the application is taking precautions to mitigate XSS vulnerabilities. By HTML encoding dangerous characters, such as angle brackets (< and >), ampersands (&), quotes (" and '), and others, the web application ensures that these characters are treated as literal content rather than being interpreted as HTML or script code.
### Base64 Encoding
- Base64 encoding is a process that converts binary data into a text format using a set of 64 ASCII characters. This encoding scheme is called Base64 because it operates on groups of 3 bytes (24 bits) from the input data and represents them as 4 ASCII characters.
- Base64 encoding is necessary for various purposes, including data transmission, data storage, and data representation in different systems. Here are some reasons why Base64 encoding is important:
	1. Binary-to-Text Conversion: Base64 encoding allows the conversion of binary data into a text format. Computers typically store and process data in binary format, consisting of 0s and 1s. However, some systems or protocols (such as email or XML) only support text data. Base64 encoding provides a mechanism to represent binary data, such as images or files, as a sequence of printable ASCII characters.	    
	2. Data Transmission: Base64 encoding is commonly used for transmitting binary data over text-based protocols or mediums that only support ASCII characters. For example, when sending binary attachments in email messages, the binary data is encoded using Base64 to ensure it remains intact during transmission without being corrupted or misinterpreted.	    
	3. Data Storage: In certain scenarios, such as when storing binary data in databases or text-based files, using Base64 encoding helps overcome limitations related to binary data handling. Base64-encoded data can be safely stored as text, preserving its integrity and ensuring compatibility across different systems.	    
	4. URL Compatibility: Base64 encoding is often used to represent binary data in URLs. URLs have specific requirements for characters that can be used, and Base64 encoding provides a way to represent binary data using a subset of URL-safe characters, making it suitable for inclusion in URLs without conflicts or parsing issues.	    
	5. Data Encryption: Base64 encoding is sometimes used as part of data encryption algorithms or cryptographic operations. While Base64 encoding itself does not provide encryption, it is used to encode encrypted data so that it can be safely transmitted or stored.	    
	6. Data Representation: Base64 encoding is useful for representing data in a readable format when human interpretation is required. For example, when working with API responses or debugging network traffic, Base64 encoding allows the representation of binary data in a format that can be easily inspected and understood.
- It's important to note that Base64 encoding is not a form of encryption, and it does not provide security or confidentiality. Base64-encoded data can be easily decoded back to its original binary form. If data security is a concern, encryption algorithms specifically designed for secure data protection should be used in conjunction with Base64 encoding.
- Overall, Base64 encoding serves as a valuable tool for various applications, allowing the representation, transmission, and storage of binary data in text-based systems and formats.
