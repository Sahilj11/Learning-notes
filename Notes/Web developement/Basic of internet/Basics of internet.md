
### IP 

- Imagine you want to send a letter to your friend who lives in a different city. You need to know their address to make sure the letter reaches them, right? Well, in the world of computers and the internet, IP (Internet Protocol) is like an address that helps computers find each other
- Here's how IP works: 
	- Unique numbers: Every device connected to the internet, like your computer or phone, has a unique number called an IP address. It's like a special code that identifies the device, just like your friend's home address helps identify their house.
	- Sending and receiving: When you want to visit a website or send a message, your computer needs to know the IP address of the computer it wants to communicate with. It's similar to you knowing your friend's home address to send them a letter.
	- Routing: Just like there are postal systems to deliver your letter to your friend's house, the internet has a network of routers. These routers help guide your data (like a website request or a message) through the internet to reach the correct destination based on the IP address.
	- Breaking into small parts: Sometimes, if the data you're sending is big, it gets divided into smaller pieces called packets. These packets are like tiny parts of your letter, making it easier to send them across the internet.
	- Reassembling the data: When the packets arrive at the destination computer, they are put back together in the right order to make sense. It's like your friend receiving the letter and arranging the paragraphs correctly to read your message.
- So, IP is like a system that gives unique addresses to computers and helps them send and receive data over the internet. It ensures that your computer can find other computers and communicate with them, just like an address helps you find your friend's house to send them a letter.
- In simple terms, IP is like a special code that computers use to talk to each other on the internet. It's like having a unique address for each computer, allowing them to send and receive information to the right places.
- numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. It serves two main purposes: identifying the host or network interface and providing the location of the device in the network
- #.#.#.# , each using 8 bits , 
- IPv6 been introduced to overcome bits shortage , which include 128 bits
-  Reflexive IP :- 

### What a message over internet contain

- IP address of sender and receiver 
- protocols :- like 80 for HTTP and 443 HTTPS 
- receiver IP : protocol , like 1.2.3.4:80
- sender computer will also choose a port number (may be random) , so that receiver can reply to it
- divide the request(posting image on FB) to various fragment to avoid internet congestion , each packet containing number. if one of the packet dropped , instead of server asking whole photo again it can just ask the sender the packet which got dropped , maintaining efficiency.
- Packets contain somethings and before it they contain GET and POST ()
	- GET / HTTP / 1.1 , here '1.1' means the version of HTTP
	- Host: fully qualified domain name

### Layers 

- **Application layer :-** this layer has protocols,  programs directly interact with this. like HTTP , SMTP
**- Transport layer :-** where TCP and UDP (more faster , play important part in online gaming)
	- once TCP get data it chops the information into small packets , so they can choose the fastest route individually to reach the destination. **(technology of packet switching**)
	- TCP adds headers to each packets containing instructions ,including the order of these packets to joins these info and make sense of it ^384b46
- Application layer talks to transport layer through port
- ![[tcp.png]]
- Internet layer :- uses IP to attach origin and destination address to make sure the packet knows where it came from and where it is going
- Network layer :- Contain MaC address

### TCP

- Let's imagine you want to send a letter to your friend who lives far away. TCP (Transmission Control Protocol) is like a system that helps make sure your letter arrives safely and in the right order.
- Here's how TCP works:
	- Breaking the letter into parts: Before sending the letter, TCP breaks it into smaller parts called packets. Each packet contains a piece of your letter, like a paragraph or a sentence.
	- Adding numbers: TCP gives each packet a number, so they can be put back together correctly when they arrive. It's like numbering the paragraphs of your letter so your friend can easily read them in order.
	- Sending the packets: The packets are sent over the internet one by one. They might take different paths to reach your friend's house, just like different roads might lead to different places.
	- Checking for missing packets: When your friend's computer receives the packets, TCP checks if any are missing. If a packet is missing, TCP asks the sender to send it again. It's like if a paragraph of your letter got lost in the mail, TCP would ask you to write it again and send it separately.
	- Putting the packets back together: Once all the packets have arrived, TCP helps put them back together in the right order. It uses the packet numbers to arrange them correctly, just like your friend would arrange the paragraphs of your letter based on the numbers.
	- Letting you know it's done: Finally, TCP tells your friend's computer that it has received all the packets and the letter is complete. It's like sending a message to your friend saying, "I've received all the paragraphs, and your letter is ready to read!"
- TCP makes sure that your letter (data) gets to your friend's computer without any missing parts and in the correct order. It takes care of splitting the letter into manageable pieces, sending them over the internet, and putting them back together at the destination
- In simpler terms, TCP is like a system that breaks your letter into parts, sends them, and ensures they arrive in order. It's like a helpful postman who makes sure your message gets to your friend's house and that they can read it just the way you wrote it!

### Difference b/w TCP and IP

- Imagine you want to send a letter to your friend who lives far away. IP (Internet Protocol) is like the address on the envelope that helps the letter find its way to your friend's house. TCP (Transmission Control Protocol), on the other hand, is like the system that makes sure the letter is delivered safely and in the right order.
- Here's how they work together:
	- IP (Internet Protocol):
		- IP is like the address on the envelope of your letter. It consists of a unique number that identifies the device or computer you want to send the letter to. Just like you need your friend's address to send the letter, computers need IP addresses to communicate with each other over the internet.
		- IP is responsible for routing the letter through the postal system (or the internet) to reach the correct destination. It ensures that the letter goes to the right city and the right house, just like IP directs data packets to the correct computer on the internet
	- TCP (Transmission Control Protocol):
		- TCP is like the system that ensures your letter is delivered properly and in the right order. It breaks your letter into smaller parts called packets and adds numbers to each packet, just like we discussed earlier.
		- TCP helps with the reliable delivery of these packets. It makes sure that all the packets of your letter arrive at your friend's house, and if any packet is missing, TCP asks for it to be sent again. It also puts the packets back in the right order so that your friend can read the letter correctly.
- So, to summarize:
	- IP is like the address on the envelope, which helps your letter (data) find its way to the right destination.
	- TCP is like the system that manages the delivery of the letter, making sure it arrives safely and in the right order.
- In computer terms, IP helps with the addressing and routing of data, while TCP takes care of the reliability and order of data delivery. They work together to ensure that messages, files, or any other data you send over the internet reach their intended destination correctly and without any missing parts

### DNS
- Just like we store phone numbers with names , the domains IPs are stored in names to make the internet more user-friendly 
- Domain name system :- collection of servers on internet whose main job is to translate IP addresses into Domain names and vice versa.
- Even in your home router is typically a DNS server as it stores the IP of some domain which we visit frequently
- Inside of these DNS server typically are key(fully qualified domain names ) and values(IP addresses) pair 

### Domain names explained 
- fully qualified domain name https://www.example.com/ here last '/' represent the root of website
- .com means top level domain (TLD)
- www means host names 
- https means protocol , what protocol should computer or browser use to talk to the server
- Using [[Inspect function]] to understand what goes underneath the hood

### HTTP
- application layer protocol used for communication between web browsers and web servers. HTTP defines how messages are formatted and transmitted, and it specifies the actions that web browsers and servers should take in response to various commands.
- Here are some key features and aspects of the HTTP protocol:
	- **Client-Server Model:** HTTP follows a client-server model, where the client (typically a web browser) sends requests to the server, and the server responds with the requested information.
	- **Stateless Protocol:** [[Important terms#Stateless protocol]]
	- **Request-Response Cycle:** The client sends an HTTP request to the server, specifying the desired action, such as retrieving a web page or submitting form data. The server processes the request and sends back an HTTP response, which contains the requested data, along with status codes and optional headers.
	- **URL Structure:** HTTP requests include Uniform Resource Locators (URLs) to identify the specific resource being requested. URLs consist of a scheme (typically "http://" or "https://"), the domain name or IP address of the server, and the path to the resource on the server.
	- **Methods:**  [[Important terms#Methods]]
	- **Headers:** HTTP messages contain headers that provide additional information about the request or response. Headers can include details such as content type, cache control, cookies, authentication credentials, and more.
	- **Status Codes:** HTTP responses include status codes that indicate the outcome of the request. Status codes are three-digit numbers that categorize responses into informational, success, redirection, client error, or server error categories. Examples include 200 (OK), 404 (Not Found), 500 (Internal Server Error), etc
	- HTTP (Hypertext Transfer Protocol) is considered a **connectionless protocol** because it does not maintain a persistent connection between the client (e.g., a web browser or a mobile app) and the server. In other words, after a client sends a request to the server and receives a response, the connection is closed.
		- When a client initiates an HTTP request, it establishes a connection with the server, typically over TCP/IP (Transmission Control Protocol/Internet Protocol). The client sends the request to the server, which processes the request and generates a response. The server then sends the response back to the client, and once the response is received, the connection is closed.
- HTTPS port is 443

### HTTP Headers
- An HTTP header, short for Hypertext Transfer Protocol header, is a component of an HTTP request or response that carries additional information about the message being transmitted. It consists of a set of key-value pairs, where each pair provides specific details or instructions related to the HTTP communication.
- HTTP headers are included in the beginning of an HTTP message, either in the request sent by the client to the server or in the response sent by the server back to the client. These headers provide metadata, control parameters, or instructions to the recipient about how to handle the message.
- HTTP headers can serve various purposes, such as:
	1. **Content negotiation**: Headers like "Accept" and "Accept-Language" indicate the type of content and language preferences of the client, helping the server to send an appropriate response.
	2. **Caching and expiration**: Headers like "Cache-Control" and "Expires" define how long a response should be cached by the client or intermediary caching servers.
	3. **Authentication and authorization**: Headers like "Authorization" and "WWW-Authenticate" are used to handle authentication and authorization mechanisms.
	4. **Compression**: Headers like "Content-Encoding" indicate the compression algorithm used for the response body, enabling the client to decompress it.
	5. **Security**: Headers like "Content-Security-Policy" and "Strict-Transport-Security" provide security-related instructions to the client or server.
	6. **Cookies**: Headers like "Set-Cookie" are used for managing cookies and session information.
- These are just a few examples of the numerous HTTP headers available. The headers utilized in a particular HTTP request or response depend on the specific requirements and functionalities of the application or the server handling the communication

### Error Codes
- ![[error codes.png]]
### URL queries 
- https://www.google.com/search?q=cats here the '?' is been used to pass 
- In a URL, the question mark ("?") is used to separate the base URL from the query parameters. When performing a search on Google, the query parameters are added after the question mark in the URL. ^cc9ff3
- these `?q=cats` are known as HTTP parameters
- For example, when you search for "chatbot" on Google, the URL might look like this:`https://www.google.com/search?q=chatbot`
- In this case, the base URL is "[https://www.google.com/search](https://www.google.com/search)", and the query parameter is "q=chatbot". The "q" stands for "query" and it specifies the search term.
- Additional query parameters can be added to provide more information for the search. For example, you might see parameters like **"hl" for language,** **"tbm" for search type (web, images, videos),** or **"num" for the number of search results to display per page.**
- So, the question mark in a Google search URL separates the base URL from the query parameters, allowing you to pass specific search terms and additional information to the Google search engine.
- Multiple keys and values 
	- https://www.example.com/path?key=value&key=value
	- here key value separated by '&'
-  <font style="color:red">Does every request a user make to the server automatically gets converted to key and values in URL using attributes like action. Are there other attributes which perform the same task</font>`
	- No, not every request a user makes to the server automatically gets converted to key-value pairs in the URL. The inclusion of query parameters in the URL depends on how the HTML form or the client-side code is implemented.
	- In HTML, when you use the `<form>` element, the default method for submitting the form is `GET`, which appends the form data as query parameters to the URL. The `action` attribute of the `<form>` element specifies the URL where the form data should be submitted.
	```
	<form action="/submit" method="GET">
	    <input type="text" name="username">
	    <input type="password" name="password">
	    <input type="submit" value="Submit">
	</form>
	```
	- In this case, when the user submits the form, the form data will be appended to the URL as query parameters. If the user enters "john" for the username field and "secret" for the password field, the URL will look something like this: `/submit?username=john&password=secret`. The server can then retrieve these values using the `request.args.get` method, as explained in the previous response.
	- However, it's important to note that you can also use the `POST` method to submit form data without including it in the URL. When the form's `method` attribute is set to `POST`, the form data is sent as part of the HTTP request body, rather than appending it to the URL. This is useful when dealing with sensitive data, such as passwords, where you don't want the data to be visible in the URL.
	- To summarize, the inclusion of query parameters in the URL depends on the form's `method` attribute. If it is set to `GET`, the form data will be appended as query parameters. If it is set to `POST`, the form data will be sent in the request body. Other attributes of the `<form>` element, such as `action`, determine the URL to which the form data will be submitted, but they don't directly control the conversion of the data into key-value pairs in the URL

## Server
- it responds to request from client side , it is essentially a software although popularly people think it been an physical device

## Ports 
- Imagine you have a big building with lots of rooms, and each room has a door. Now, think of a network as a way for computers to talk to each other, just like people talking to each other in different rooms.
- In networking, a port is like a door in a room. It helps computers send and receive information to and from other computers. Just like each room in a building has a unique number, each port has a unique number too.
- When computers want to talk to each other, they use these port numbers to know which door to knock on. For example, if you want to visit a friend in room number 10, you would go to the door labeled "Room 10" and knock on it. In the same way, computers use port numbers to find the right "door" to send their information to.
- So, ports help computers talk to each other by providing a specific way to send and receive information. They are like doors with numbers on them, and computers use these numbers to know where to send their messages
- Port numbers range from 0 to 65535 and are divided into three categories:
	- Well-known ports: Port numbers from 0 to 1023 are reserved for well-known services. For example, port 80 is commonly used for HTTP (Hypertext Transfer Protocol) web traffic, port 25 for SMTP (Simple Mail Transfer Protocol) email traffic, and port 22 for SSH (Secure Shell) remote access.
	- Registered ports: Port numbers from 1024 to 49151 are used for registered services or applications. They are assigned by the Internet Assigned Numbers Authority (IANA) to ensure uniqueness and avoid conflicts. These ports are often associated with specific services but can be used by other applications as well.
	- Dynamic or private ports: Port numbers from 49152 to 65535 are considered dynamic or private ports. They are available for temporary use by client applications when initiating connections to servers. These ports are dynamically allocated by the operating system and are typically not associated with specific services.
- When a network communication occurs, both the source and destination devices use port numbers to establish a connection. The **combination of an IP address and port number is referred to as a socket**. **This allows multiple applications to run simultaneously on a single device, each using a different port number.**
- By using specific port numbers, network administrators and firewall configurations can control and manage which services or applications are allowed to communicate over a network, providing a level of security and access control.