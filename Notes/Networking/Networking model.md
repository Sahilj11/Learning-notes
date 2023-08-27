
## Define 
- networking models categorize and provide a structure for networking protocols and standards
- ![[sf.png]]
- Although OSI model is not used today but it impacted the understanding of network
## OSI Model 
- Open system interconnection model
- conceptual model that categorise and standardize the different function of network
- In the context of the OSI model, the word "function" refers to the specific tasks, operations, or responsibilities performed by each layer of the model. Each layer of the OSI model has a distinct function or set of functions that contribute to the overall process of network communication.
- function divided into 7 layers
- these layers work together to make network work
- the OSI (Open Systems Interconnection) model is still used as a conceptual framework for understanding and discussing network protocols and functions. While it may not be strictly implemented in its entirety in practical network implementations, the OSI model remains relevant as a reference model for network architecture and communication.

### Application layer
- ![[app.png]]
- the Application layer identifies communication partners through the use of port numbers(for http it is 80), application layer protocols, URLs, and IP addresses. By leveraging these identifiers, applications can establish connections and exchange data with the intended communication partners in a network
- The Application layer of the OSI model does not directly handle the synchronization of communication between applications. Synchronization is typically managed at higher layers of the protocol stack or within the application itself. However, the Application layer may provide certain mechanisms or protocols that facilitate synchronization. 
- ![[encap.png]]
- in encapsulation data added to the information as it moves from 7th layer to 1st layer where converted into electric signals
- ![[fg.png]]
- ![[hg.png]]
- Same-layer interaction refers to the communication and exchange of data that occurs between entities at the same layer of the OSI model, specifically within the Application layer. Within the Application layer, applications running on different network devices can interact and communicate with each other using protocols and standards specific to the application.
- In same-layer interaction at the Application layer, the communication partners are typically applications or processes running on different devices. These applications can exchange data, commands, or requests to fulfill specific functionalities or tasks. or example, a web browser application running on one device can send an HTTP request to a web server application running on another device to fetch a webpage. The web server then responds with the requested data, and the browser application processes and displays it

### Presentation layer
![[re.png]]

### Session layer
-   The Session layer is like a supervisor that helps two or more computer programs or applications talk to each other and work together smoothly. It's a layer in the computer networking system that ensures these programs can establish a connection, communicate properly, and end their conversation in a good way.
- Imagine you and your friend want to play a game online. Before you start playing, you need to establish a session or connection between your devices. The Session layer helps with that. It makes sure your devices agree on things like who will start the game, what rules you'll follow, and how you'll communicate during the game.
- Once the game starts, the Session layer keeps an eye on things to make sure everything goes well. It helps with things like keeping the game synchronized between your devices, so you both see the same thing at the same time. It also makes sure that if something goes wrong, like if your internet connection drops, you can resume the game from where you left off without losing all your progress.
- When you finish playing the game, the Session layer helps you end the session in a polite manner. It helps close the connection between your devices and lets both programs know that the game is over
- ![[Screenshot 2023-06-07 060656.png]]
### Upper layers
- ![[dcg.png]]
- ![[Screenshot 2023-06-07 061109.png]]

### Transport layer
- ![[Screenshot 2023-06-07 063119.png]]
- data is broken into small pecies , for example while watching youtube if any interuption happens in network , the whole video do not stops instead it skips a part
- Host-to-host communication refers to the process of data exchange and interaction between two end devices or hosts in a computer network. It involves the transmission of data from one host to another over a network infrastructure
- In the context of computer networking, the terms "host" and "end device" are often used interchangeably to refer to the same concept![[Screenshot 2023-06-07 063227.png]]
- this combination of data and layer 4 header called segment
- remember [[Basics of internet#^384b46]]
- TCP adds headers to each packets containing instructions ,including the order of these packets to joins these info and make sense of it

### Network layer
- ![[Screenshot 2023-06-07 063518.png]]
- it adds information like source and destination IP address
- this combination of data called packet

### Data link
- provides node to node connectivity and data transfer (for eg , pc to switch , switch to router , router to router)
- defines how data is formatted for transmission over physical medium
- ![[df.png]]
- ![[Screenshot 2023-06-07 064211.png]]
- data combination in this layer is called a frame
- after this no encapsulation happens
- MAC address are added here

### Physical layer
- ![[Screenshot 2023-06-07 064720.png]]

### Protocol Data units
- ![[Screenshot 2023-06-07 064829.png]]

## TCP/IP Suite
- ![[Screenshot 2023-06-07 065111.png]]
- ![[Screenshot 2023-06-07 065258.png]]

## Data Flow
- ![[Screenshot 2023-06-07 065415.png]]
- 

