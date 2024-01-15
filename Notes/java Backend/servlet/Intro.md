## Hierarchy 
- First come Servlet interface which has servlet life cycle methods 
- then a GenericServlet class, it is used when we want to create protocol independent servelt (no response and request object) 
- and at last HttpServlet 
![](../../statics/Pasted%20image%2020240113100910.png)
- whenever we want to create a servlet , a deployment descriptor file also need to be created like web.xml

## Life cycle of servlet
The life cycle of a servlet in Java is a series of steps that a servlet goes through from its initialization to its destruction. Servlets are Java programming language classes that dynamically process requests and responses from web clients. The servlet life cycle is managed by the servlet container, which is responsible for loading, initializing, invoking, and destroying servlets. Here are the key phases in the life cycle of a servlet:

1. **Loading and Instantiation:**
   - When a web server starts or when a request for a servlet is received for the first time, the servlet container loads the servlet class.
   - It creates an instance of the servlet using the `init` method.

2. **Initialization:**
   - The `init` method is called by the servlet container to initialize the servlet.
   - The `init` method is called only once during the servlet's lifetime.
   - This is the place where you perform one-time initialization tasks, such as loading configuration files or initializing resources.

3. **Request Handling:**
   - After initialization, the servlet is ready to handle client requests.
   - For each incoming request, the servlet container calls the `service` method.
   - The `service` method determines the type of request (GET, POST, etc.) and invokes the appropriate method (e.g., `doGet`, `doPost`) to handle the request.

4. **Request Processing:**
   - The `doGet`, `doPost`, and other specific methods handle the actual processing of the client's request.
   - These methods are where you write the logic to generate the response for the client.
   - The servlet remains in the request-handling state until it completes processing the request.

5. **Destroying:**
   - When the servlet container decides to shut down or when the servlet is no longer needed, the `destroy` method is called.
   - The `destroy` method allows the servlet to perform cleanup tasks, release resources, and save state information.
   - It is called only once during the servlet's lifetime.

6. **Unloading:**
   - After the `destroy` method is called, the servlet container unloads the servlet, freeing up resources.
   - The servlet is removed from memory, and its class is unloaded.

It's important to note that the servlet container manages the life cycle of servlets, and developers only need to implement the `init`, `service` (or specific request handling methods), and `destroy` methods. The container takes care of the loading, instantiation, and unloading processes. The `init` method is called when the servlet is first created, the `service` method is called for each client request, and the `destroy` method is called when the servlet is being taken out of service.