### Network tab (to see HTTP stuff going on)
- monitor network activity related to a web page or application. It provides detailed information about the HTTP requests and responses made by the browser when loading the webpage, including resources like HTML files, CSS stylesheets, JavaScript files, images, API requests, and more.
- **some of the key features and functionalities**
	1. Request and Response Monitoring: The Network tab displays a list of all the requests made by the browser, including the request method (GET, POST, etc.), the URL of the requested resource, the status code of the response, the size of the response, and other relevant details.
	2. Headers and Parameters: You can inspect the headers of each request and response, which include information such as cookies, user agents, cache directives, and request parameters.
	3. Timing and Performance Analysis: The Network tab provides timing information for each request, including the time it takes to initiate the request, receive the response, and load the resource. This helps in analyzing the performance of the webpage or application and identifying potential bottlenecks.
	4. Resource Preview and Content: You can preview the content of individual resources within the Network tab. This is especially useful for examining the response content of HTML, CSS, JavaScript, or JSON files.
	5. Filtering and Sorting: The Network tab allows you to filter requests based on various criteria such as file type, domain, status code, and more. You can also sort the requests based on different parameters like size, time, or domain.
	6. Request Blocking and Manipulation: In some developer tools, the Network tab may offer features to block specific requests, simulate different network conditions (e.g., throttling the network speed), or modify request headers and parameters for testing purposes
- Use preserve log option to keep all the requests 
- ![[Screenshot 2023-06-02 074329.png]]
- Response headers containing :- HTTP/1.1 200 OK (status code) , Content type : text/html
- can also use [[Web developement/extras/Commands#Curl]]  for focused response header info
- you can also see POST request , go in network tab->chose the request you want to inspect and then select payload(we can see what was actually sent to server) tab ^772036

## ELEMENTS TAB
- shows the underlying html of a page
- You can change the html of page from here 
- 
