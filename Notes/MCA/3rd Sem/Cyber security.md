# UNIT 1

## Network
### Intro
A group of computers connected to each other to communicate and to share their resources, data, and applications is called Computer Network

### Types
#### Personal area network
This network can be controlled by a single person. An individual can do communication 
between the computer devices in work space which is centered. USB, computer, mobile, Tablet, printer,
![](../../statics/Pasted%20image%2020241216101943.png)

#### LAN
A network that links computers all together via a common communication line within a local
limited area is called LAN (Local Area Network).
![](../../statics/Pasted%20image%2020241216102028.png)

#### MAN
MAN (Metropolitan Area Network) is a network bigger than LAN (Local Area Network), but
smaller than WAN (Wide Network Area). In this network type all the computers are connected in a geographical distance via shared lines for communication within anytown, a city, or any metropolitan area.

#### WAN
A network of computer that links computers in distance of a large geographical area using
sharedcommunicating lineis called WAN

#### VPN
A network of computers that widens across the internet and constitutes  a private network is called VAN (Virtual Private Network). It provides facility to send or receive data to the user like they are linked in real, while in reality they are not linked, but seems to constitute a private network via a connection that is virtual and point to point.Such type of networks helps in prevention of malicious sources as the connection make use of encrypted one so as to ensure that sensitive data is securely transmitted over VPN.
![](../../statics/Pasted%20image%2020241216102241.png)

### Network security
Network Security is known as a methods used for precautions and for protecting Computer
network structure from leaking private data, misuse, failure, alteration, destruction and unauthorized access. It is a process to secure networks from possible security threats.
#### Notes network security

**Notes on Types of Network Security**

1. **Physical Network Security**
   - **Definition**: Measures taken to prevent unauthorized physical access to network hardware, like routers, switches, and servers.
   - **Examples**: Locking server rooms, using biometric access, CCTV surveillance, and physical barriers.
   - **Importance**: Protects critical network infrastructure from theft, tampering, or physical damage.

2. **Technical Network Security**
   - **Definition**: Protection of data stored on or traveling through the network using technology and encryption.
   - **Examples**: Data encryption (e.g., TLS/SSL), intrusion detection systems (IDS), intrusion prevention systems (IPS), and network segmentation.
   - **Importance**: Ensures data integrity, confidentiality, and availability by safeguarding against cyber threats.

3. **Administrative Network Security**
   - **Definition**: Policies and procedures that govern user behavior and network access.
   - **Examples**: User training programs, incident response plans, and regular security audits.
   - **Importance**: Reduces the risk of human error and insider threats, ensuring a robust security posture.

4. **Access Control Security**
   - **Definition**: Restricts user access to network resources based on their roles and permissions.
   - **Examples**: Role-based access control (RBAC), multi-factor authentication (MFA), and network access control (NAC).
   - **Importance**: Prevents unauthorized users from accessing sensitive data and systems.

5. **Application Security**
   - **Definition**: Securing applications used within the network to protect against vulnerabilities and exploitation.
   - **Examples**: Regular application updates, penetration testing, and secure coding practices.
   - **Importance**: Shields critical applications from malware, unauthorized access, and zero-day attacks.

6. **Firewalls Security**
   - **Definition**: Hardware or software tools that filter incoming and outgoing network traffic based on predetermined security rules.
   - **Examples**: Packet-filtering firewalls, stateful inspection firewalls, and next-generation firewalls (NGFW).
   - **Importance**: Acts as the first line of defense against external threats and unauthorized traffic.

7. **Virtual Private Networks (VPN)**
   - **Definition**: Secure, encrypted connections that allow users to access the network remotely over the internet.
   - **Examples**: Site-to-site VPNs, remote access VPNs, and client-to-site VPNs.
   - **Importance**: Protects data during transmission and enables secure remote work.

8. **Wireless Security**
   - **Definition**: Safeguards wireless networks from unauthorized access and cyberattacks.
   - **Examples**: WPA3 encryption, disabling SSID broadcasting, and MAC address filtering.
   - **Importance**: Prevents eavesdropping, unauthorized use, and wireless-based attacks like war driving or rogue access points.

**Services Provided by Network Security**

1. **Message Confidentiality**
   - **Definition**: Ensures that only authorized individuals can access the content of a message.
   - **Examples**: Encryption techniques like AES or RSA.
   - **Importance**: Protects sensitive information from eavesdropping or interception.

2. **Message Integrity**
   - **Definition**: Ensures that a message has not been altered during transmission.
   - **Examples**: Hashing algorithms like SHA-256 or MD5.
   - **Importance**: Detects tampering or corruption in transmitted data.

3. **Message Authentication**
   - **Definition**: Verifies the identity of the sender and the authenticity of the message.
   - **Examples**: Digital signatures or HMAC.
   - **Importance**: Confirms that the sender is genuine and prevents impersonation.

4. **Message Non-Reproduction**
   - **Definition**: Prevents unauthorized duplication or retransmission of messages.
   - **Examples**: Use of unique session tokens or timestamps.
   - **Importance**: Ensures that data cannot be copied or reused maliciously.

5. **Entity Authentication**
   - **Definition**: Verifies the identity of users or devices attempting to access the network.
   - **Examples**: Certificates, biometrics, or two-factor authentication.
   - **Importance**: Confirms legitimate entities and prevents unauthorized access.

**Network Security Devices**

1. **Active Devices**
   - **Definition**: Devices that actively block or respond to threats.
   - **Examples**: Firewalls, intrusion prevention systems (IPS), and routers with security features.
   - **Importance**: Provides real-time protection by detecting and mitigating threats immediately.

2. **Passive Devices**
   - **Definition**: Devices that monitor and report network activities without interfering.
   - **Examples**: Intrusion detection systems (IDS), network monitors, and log analyzers.
   - **Importance**: Helps identify vulnerabilities and provides insights for preventive measures.

3. **Preventative Devices**
   - **Definition**: Devices or tools designed to prevent security incidents before they occur.
   - **Examples**: Anti-virus software, spam filters, and patch management systems.
   - **Importance**: Reduces the attack surface and prevents exploitation of known vulnerabilities.

4. **Unified Threat Management (UTM)**
   - **Definition**: Integrated security devices that combine multiple functionalities into a single system.
   - **Examples**: Devices offering firewall, VPN, anti-virus, and intrusion detection/prevention in one.
   - **Importance**: Simplifies security management while providing comprehensive protection.

## Network security techniques

### Firewall
A firewall refers to any specific device type for security of network or an application or software which detects as well as controls or cleans traffic coming to and traffic going out in network by using the predefined set of rules of security. This works like a checkpoint in between private internal networks and public external networks.

#### Types
1. **Packet-Filtering Firewalls**: Filter network traffic by inspecting individual packets against predefined rules based on IP, port, and protocol.
2. **Next-Generation Firewalls (NGFW)**: Advanced firewalls that include features like deep packet inspection, intrusion prevention, and application-level control.
3. **Cloud Firewalls**: Firewalls hosted in the cloud to protect cloud-based resources and services from threats.
4. **Application-Level Gateways (Proxy Firewalls)**: Filter traffic at the application layer, acting as intermediaries between users and resources to block malicious content.
5. **Circuit-Level Gateways**: Monitor and verify session-level traffic, ensuring that connections are legitimate without inspecting packet data.
6. **Stateful Multi-Layer Inspection (SMLI) Firewalls**: Combine packet inspection and session tracking to provide comprehensive security across multiple layers of the network stack.
7. **Network Address Translation (NAT) Firewalls**: Mask internal IP addresses by translating them to a single public IP, adding a layer of privacy and security

#### Function
- Network Threat Prevention
- Access Validation
- Record and Report on Events
- Application and Control based on Identity
- Network Traffic Management and Control
- Performing Scalable
- Hybrid Cloud Support

#### **Advantages of Firewalls**

1. **Enhanced Security**: Protects networks from unauthorized access and external threats.
2. **Traffic Monitoring**: Filters incoming and outgoing traffic based on security rules.
3. **Preventing Cyberattacks**: Blocks malware, DDoS attacks, and unauthorized data access.
4. **Network Segmentation**: Creates secure zones within the network to isolate sensitive resources.
5. **Policy Enforcement**: Enforces organization-wide security policies.
6. **Logging and Auditing**: Maintains logs of traffic and alerts, aiding in compliance and threat analysis.
7. **Remote Access Security**: Secures VPN connections for remote work.

#### **Limitations of Firewalls**

1. **Cannot Prevent Insider Threats**: Does not protect against malicious actions by authorized users.
2. **Limited Against Sophisticated Attacks**: May not stop advanced threats like zero-day exploits or phishing.
3. **No Protection for Encrypted Traffic**: Encrypted data passing through the firewall remains unchecked.
4. **Dependency on Configuration**: Misconfigured rules can lead to vulnerabilities.
5. **Performance Impact**: Can slow down network performance, especially with deep packet inspection.
6. **Cost and Maintenance**: High-quality firewalls and their upkeep can be expensive.
7. **Limited Application Security**: Cannot address vulnerabilities in poorly coded applications.


### Virtualization
#### Intro
Sharing of resources from physical network devices like routers, switcheswithin various virtual networks is known as network virtualization.Network virtualization can be used in real-world at a large-scale.

#### Approaches
- Protocol-based approaches: It consists of a network protocol that enables tagging or tunneling techniques for the distinction of virtual networks.
- Machine virtualization-based approaches:It consists of groups of interconnected virtual machines to create virtual networks. To instantiate virtual routers and virtual links, Virtual Machine Monitors are used regardless of physical network topology.
- Programmable networks: Virtual networks can be created using programmable routers. We can do it in network devices by decoupling the data plane and the control plane.

#### Techniques

1. **Containerization**:
    
    - **Definition**: A lightweight method to virtualize applications and their dependencies into isolated environments, ensuring consistent performance across different systems.
    - **Advantages**: Reduces resource overhead, enhances scalability, and simplifies application deployment (e.g., Docker, Kubernetes).
2. **Sandboxing**:
    
    - **Definition**: A security technique that isolates programs or code execution in a controlled environment to prevent them from affecting the host system.
    - **Advantages**: Contains malware or harmful code, ensuring minimal impact on production systems.
3. **Server Virtualization**:
    
    - **Definition**: Dividing a physical server into multiple virtual servers using hypervisors to maximize resource utilization.
    - **Advantages**: Reduces hardware costs, increases scalability, and simplifies management.
4. **Network Virtualization**:
    
    - **Definition**: Abstracts physical network resources into logical segments for easier management and enhanced flexibility.
    - **Advantages**: Improves network efficiency, isolates traffic, and enables software-defined networking (SDN).
5. **Desktop Virtualization**:
    
    - **Definition**: Enables users to access a virtual desktop environment remotely using virtual machines (VMs).
    - **Advantages**: Centralized management, reduces hardware dependency, and enhances remote work capabilities.
6. **Hypervisor Security**:
    
    - **Definition**: Protecting the software layer that manages virtual machines from vulnerabilities and attacks.
    - **Importance**: Ensures the integrity of all hosted virtual machines.
7. **Virtual and Physical Switches**:
    
    - **Definition**: Virtual switches connect virtual machines within a virtualized environment, while physical switches handle traditional network traffic.
    - **Importance**: Facilitates communication in hybrid environments and requires secure configurations to prevent attacks.
8. **Infrastructure & Guest OS Security**:
    
    - **Definition**: Involves securing the underlying hardware (infrastructure) and guest operating systems within a virtualized setup.
    - **Importance**: Ensures both the host and the virtualized environments are protected from vulnerabilities.
9. **Server Isolation & Virtual Hard Disk (HD) Encryption**:
    - **Definition**: Server isolation prevents unauthorized access between virtual servers, while encryption protects data stored on virtual hard drives.
    - **Importance**: Enhances security by preventing lateral movement and securing sensitive data.
10. **Availability and Disaster Recovery**:
	- **Definition**: Ensures business continuity by maintaining system availability and leveraging virtualization for rapid recovery after failures.
	- **Advantages**: Minimizes downtime and supports efficient backup and restoration processes.

### DNS
The term DNS refers to"Domain Name System". A numerical connection between a host name and its network address is provided by this directory service.
DNS is necessary for the Internet to function. It can convert IP addresses into domain names
using the DNS service. Users of the network give other hosts names that are easy to remember rather than IP addresses.

#### Working
![](../../statics/Pasted%20image%2020241216112635.png)

#### Types of domains
1. **Country Code Top-Level Domains (ccTLDs):**
    
    - **Definition**: Domain extensions specific to countries or regions, consisting of two letters.
    - **Examples**:
        - `.in` (India)
        - `.us` (United States)
        - `.uk` (United Kingdom)
    - **Usage**: Often used by organizations, individuals, or businesses operating in or targeting a specific country.
2. **Inverse Domains:**
    
    - **Definition**: Used for reverse domain name lookups to map IP addresses back to domain names.
    - **Purpose**: Primarily for administrative and debugging tasks.
    - **Example**:
        - `in-addr.arpa` for IPv4 addresses.
        - `ip6.arpa` for IPv6 addresses.
3. **Generic Top-Level Domains (gTLDs):**
    
    - **Definition**: Commonly used domain extensions that are not specific to any geographic region.
    - **Examples**:
        - `.com` (commercial organizations)
        - `.org` (nonprofit organizations)
        - `.net` (network infrastructure)
        - `.edu` (educational institutions)
    - **Usage**: Open for global use, typically categorized by purpose or type of organization.

#### Structure

 **Components of a Domain Name (Labels)**

- A domain name is divided into parts, called **labels**, separated by dots (`.`).
- To understand it, we read from **right to left**, where each part represents a subdivision.

**Parts of a Domain Name**

1. **Top-Level Domain (TLD)**:
    
    - The **last part** after the dot, like `.com`, `.org`, `.edu`.
    - Some TLDs represent specific **countries** or **regions**, such as:
        - `.us` for the United States.
        - `.in` for India.
        - `.ca` for Canada.
2. **Second-Level Domain (SLD)**:
    
    - The **main name** of the website, which comes **before the TLD**.
    - Example: In `techinfo.com`, "techinfo" is the SLD.
3. **Subdomain**:
    
    - The part that comes **before the SLD**, used to create sections or divisions under a main domain.
    - Example: In `www.techinfo.com`, "www" is a subdomain of `techinfo.com`.

**Example**

For the URL `www.techinfo.com`:

- **TLD**: `.com`
- **SLD**: `techinfo`
- **Subdomain**: `www`

- If you type `www.techinfo.com` in a browser, it takes you to a specific section of the website `techinfo.com`.
- If there’s a subdomain like `blog.techinfo.com`, it will take you to the blog section of the `techinfo.com` website.

### DNS Record


DNS (Domain Name System) records define how a domain behaves and how queries should be treated. Here are some commonly used DNS records explained in simple terms with examples:


1. **A Record (Address Record)**
    - **Purpose**: Maps a domain name to its IPv4 address.
    - **Key Point**: Essential for every website, and a domain can have multiple A records.
    - **Example**:
        - If `example.com` has an IP address of `192.168.1.1`, the A record will store:  
            `example.com → 192.168.1.1`.


2. **NS Record (Name Server Record)**
    - **Purpose**: Specifies the name servers for a domain. Name servers store all the DNS records related to the domain.
    - **Key Point**: Helps direct queries to the correct server for DNS resolution.
    - **Example**:
        - If the name servers for `example.com` are `ns1.dnsprovider.com` and `ns2.dnsprovider.com`, the NS records will store:  
            `example.com → ns1.dnsprovider.com`.


3. **TXT Record (Text Record)**
    - **Purpose**: Stores text information within DNS. Used for ownership verification, email security, and anti-spam purposes.
    - **Key Point**: Often includes information for SPF, DKIM, or DMARC email authentication.
    - **Example**:
        - To verify domain ownership, a TXT record might contain:  
            `example.com → "google-site-verification=abc123"`.
        - For email security, it might have:  
            `example.com → "v=spf1 include:mailserver.com ~all"`.


4. **CNAME Record (Canonical Name Record)**
    - **Purpose**: Creates an alias for a domain, pointing it to another domain name instead of an IP address.
    - **Key Point**: Used when a domain has multiple names, such as subdomains.
    - **Example**:
        - If `blog.example.com` is an alias for `example.com`, the CNAME record will store:  
            `blog.example.com → example.com`.
        - In a URL like `searchsecurity.techtarget.com`, `techtarget.com` may act as a CNAME for `searchsecurity.techtarget.com`.


#### Attacks
1. **Denial of Service (DoS)**: An attack that prevents legitimate users from accessing a service by overwhelming it with traffic.
2. **Distributed Denial of Service (DDoS)**: A DoS attack that uses multiple systems to flood a target, making it harder to mitigate.
3. **Fast Flux**: A technique used by attackers to hide the location of malicious servers by rapidly changing domain name server (DNS) records.
4. **Reflected Attacks**: Attacks where the attacker exploits a third party to send malicious traffic to the target, often used in DoS and DDoS attacks.
5. **Reflective Amplification DoS**: A form of DDoS where an attacker exploits publicly accessible servers to amplify the traffic aimed at a target.
6. **DNS Spoofing/Cache Poisoning**: The manipulation of DNS records to redirect traffic to malicious sites.
7. **DNS Tunneling**: A technique that encodes data within DNS queries and responses to bypass security filters.
8. **DNS Hijacking**: The act of altering a DNS server’s records to reroute users to malicious websites.
9. **NXDOMAIN Attack**: An attack where the attacker forces the DNS resolver to repeatedly query non-existent domains, resulting in denial of service.
10. **Phantom Domain Attack**: A type of DNS attack where fake domains are created to mislead or confuse security systems.
11. **Random Sub-Domain Attack**: An attack that targets random subdomains of a domain to exploit vulnerabilities or hide malicious activities.
12. **Domain Lock-up Attack**: A tactic where a malicious entity locks a domain to prevent the legitimate owner from changing its records.
13. **Botnet-based CPE Attack**: An attack where a botnet exploits consumer premise equipment (CPE) vulnerabilities to conduct malicious activities.
## RFID (Radio frequency identification)

### Intro
Radio waves to passively identify a tagged object that uses a technology called Radio Frequency Identification (RFID).
- It allows to track or matching of an item or individual by using passive wireless technology.
- The reader and the tag are the system's two most fundamental components. While the RFID tag uses radio waves to transmit identification and other information, the reader sends and receives signals from the tag.
![](../../statics/Pasted%20image%2020241216121804.png)

### Typesf
**1. Based on Frequency:**

1. **Ultra-High Frequency (UHF) RFID:**
    
    - **Frequency Range:** 860-960 MHz.
    - **Range:** Several meters (up to 12 meters or more).
    - **Used For:** Shipping pallets, toll collection, and vehicle tracking.
    - **Features:** Long-range communication, backscatter operation.
2. **High-Frequency (HF) RFID:**
    
    - **Frequency Range:** 13.56 MHz.
    - **Range:** Typically up to 1 meter.
    - **Used For:** Books, passports, credit cards, and contactless payment systems.
    - **Features:** Shorter range, operates using induction.
3. **Low-Frequency (LF) RFID:**
    
    - **Frequency Range:** 30 KHz to 500 KHz (commonly 125 KHz).
    - **Range:** Typically a few inches to 6 feet.
    - **Used For:** Animal tracking, access control, and industrial applications.
    - **Features:** Short range, less susceptible to interference, slower data transfer.
4. **Microwave RFID:**
    
    - **Frequency Range:** 2.45 GHz.
    - **Range:** Over 30 feet.
    - **Used For:** Long-range asset tracking and transportation systems.
    - **Features:** Higher frequency, suitable for long-range applications.

### **2. Based on Power Source:**

1. **Passive RFID:**
    
    - **Power Source:** No internal power supply; powered by the reader’s signal.
    - **Range:** Short to medium range (depends on frequency).
    - **Used For:** Inventory management, access control, and asset tracking.
    - **Features:** No battery, lower cost, and maintenance-free.
2. **Active RFID:**
    
    - **Power Source:** Contains an internal power supply (battery).
    - **Range:** Long-range (up to 100 meters or more).
    - **Used For:** Real-time location tracking, high-value asset management.
    - **Features:** Longer range, higher cost due to battery, can broadcast signals continuously.
3. **Semi-Passive RFID:**
    
    - **Power Source:** Contains a battery, but only powers the tag’s electronics (not the transmission).
    - **Range:** Longer than passive RFID but shorter than active RFID.
    - **Used For:** Applications where longer range is required but power efficiency is important.
    - **Features:** Battery-assisted, more durable than passive RFID.

These are the main **types of RFID** categorized by frequency and power source, each suited for different use cases and application environments.

#### **Features of RFID (Radio Frequency Identification):**

1. **Wireless Communication:** Uses radio waves to transmit information between a tag and a reader.
2. **Unique Identification:** Each RFID tag has a unique identifier.
3. **Non-line-of-sight Reading:** Tags can be read without direct line-of-sight.
4. **Types of Tags:**
    - **Passive:** No internal power source; powered by the reader.
    - **Active:** Contains a battery; has a larger range.
#### **Advantages of RFID:**
1. **Efficiency:** Faster scanning as multiple tags can be read at once.
2. **Automation:** Reduces manual work, enhancing process automation.
3. **Security:** Can be encrypted to protect data.
4. **Durability:** Tags are less likely to get damaged compared to barcodes.
5. **Scalability:** Suitable for tracking large inventories or objects.
6. **Customizable:** Tags can include additional sensors (e.g., temperature, pressure).

#### **Disadvantages of RFID:**
1. **Cost:** Higher initial cost compared to barcodes.
2. **Interference:** Susceptible to interference from metal, liquids, or other RFID devices.
3. **Range Limitations:** Passive tags have limited range.
4. **Complexity:** Requires specialized equipment and training.
5. **Privacy Concerns:** Tags can be read without consent if not secured properly.

#### **RFID vs Barcode:**

|**Feature**|**RFID**|**Barcode**|
|---|---|---|
|**Technology**|Radio waves|Optical scanning|
|**Line-of-sight**|Not required|Required|
|**Speed**|Faster; can read multiple tags at once|Slower; one at a time|
|**Durability**|More durable; can withstand harsh environments|Can be damaged (scratches, tears)|
|**Data Capacity**|High; can store more information|Limited to basic data|
|**Cost**|Higher initial investment|Low cost|
|**Range**|Up to several meters (active tags)|Few centimeters to a meter|
|**Use Cases**|Inventory management, logistics, asset tracking|Retail, simple inventory systems|
|**Privacy**|Concerns due to remote scanning possibility|No privacy concerns|
## Type of network attack
- malware ,zeroday , Ddos , man in middle sql injection ,phishing attack
## Type of cyber attacker 
- insider , outsider
## Attacker motivation 
- monetary , political , business competition , intellectual gain , cyber warfare ,Drugs
## Tunneling 
Tunneling is the process of connecting the same type of source and destination network through a different type of network, then that internetworking strategy is called Tunneling. Tunneling is often used by VPNs - Virtual private networks.

tunnels are a strategy to transport any type of data beyond a network using some protocols in networking even though in network that is not compatible. By encapsulating packets, Tunneling is used to wrap packets inside of other packets

VPN Tunnel: A network which is public, shared and secure and has encrypted connection is a VPN. VPN packets reach their intended destination by using Tunneling process, which is typically a private network. So that creates a VPN Tunnel, when we use tunneling process in VPN.

### Types

**Split Tunneling**  
Usually, all internet traffic goes through a VPN when connected. Split tunneling lets some traffic use the regular internet (public) while other traffic goes through the VPN (private). This means your device connects to two networks at the same time: public and private.

**Generic Routing Encapsulation (GRE)**  
GRE wraps one set of data packets inside another, like putting one envelope inside another. It creates a **direct connection** between two points, making it easier for different networks to connect.

**IP-in-IP Tunneling**  
This method puts one IP packet inside another. It doesn’t encrypt data or use VPNs but helps create **new network routes** that are usually not available.

**Secure Shell (SSH)**  
SSH creates a **secure and encrypted tunnel** between a client and a server. It works at the **Application Layer** of the OSI model (layer 7) to protect data.

**Point-to-Point Tunneling Protocol (PPTP)**  
PPTP is a network protocol used to create VPN tunnels over public networks. It’s **fast and mobile-friendly**, making it a common choice for simple VPN needs.

**Secure Socket Tunneling Protocol (SSTP)**  
SSTP uses **SSL/TLS encryption** to secure VPN traffic. It ensures security by encrypting data, verifying integrity, and exchanging keys.

**Layer 2 Tunneling Protocol (L2TP)**  
L2TP connects remote users to a corporate network efficiently. It reduces costs by letting the company manage the IP addresses assigned to remote users.


## Fraud techniques
- phishing , spear phishing (targeted to specific user) , malware ,ransomware, ddos (volumetric , protocol , application layer),credit card scam

## Threat infrastructure
- Threat Infrastructure refers to an event, when a cyberattack disrupts or manipulates the operation of financial, healthcare, military, water or electricity systems even for a few hours, it has a significant impact on the organization and has widespread and significant consequences.
## Exploitation
- A program or piece of code known as an exploit is one that is made to find and take advantage of a security hole or vulnerability in a program or computer system, typically for malicious purposes like installing malware.
### Types of exploit
- hardware ( firmware vulnerability), software , network , personnel , physical site
### Detection sign of exploit 
- Slow performance
- Loss of storage space
- Unexplained changed settings
- Frequent crashes or freezes
- Tons of pop-ups or ads where they shouldn‘t be
## Malicious code 

### Types 

**Viruses**

- These are malicious programs that attach themselves to other files or programs.
- They duplicate themselves and spread when you download infected files or documents.
- Example: A virus can hide in a macro-enabled document and infect your device when opened.


**Worms**

- Worms are similar to viruses but don’t need to attach to other files.
- They spread automatically across networks without any user action.
- Example: A worm can infect your device and start spreading to others without your knowledge.

**Trojans**
- A Trojan disguises itself as a normal file or program but carries harmful code.
- It requires you to run or open it to activate the malicious content.
- Example: A fake game or app that secretly installs viruses or worms on your device.

**Cross-site Scripting (XSS)**
- XSS happens when hackers add harmful commands to web pages or apps.
- These commands can steal your sensitive information, change web content, or infect your device.
- Example: You visit a webpage, and it silently runs a script to steal your login details.

**Backdoor Attacks**

- A backdoor is a hidden entry point created by attackers to access your system.
- Once inside, they can stay unnoticed and steal data or control your device.
- Example: An attacker adds a backdoor to an app, allowing them to bypass security and access your files anytime.

## Defense analysis techniques

**Moving Target Defense (MTD)**

- This technique changes the target system constantly to confuse attackers.
- By frequently changing things like IP addresses or system configurations, it makes it harder and more expensive for attackers to succeed.
- **Purpose**: To increase the difficulty and cost of attacking a system, reducing the time the system is vulnerable.

**Mimic Defense (MD)**
- Mimic Defense creates multiple copies of the same functionality to handle external requests.
- By using redundancy and changing how requests are handled, it makes it harder for attackers to find weaknesses in the system.
- **Purpose**: To protect the system by balancing security flaws through changes in how the system operates.


**Defense in Cyber Security**

- Cyber security defense strategies are constantly being researched and improved.
- These strategies help protect organizations from attacks and keep systems secure.
- **Purpose**: To secure systems and networks from unwanted threats and issues.

---

**User and Entity Behavior Analytics (UEBA)**

- UEBA analyzes the behavior of users and systems on a network to identify unusual or suspicious activity.
- It helps detect things like compromised accounts or malicious movements within the network.
- **Purpose**: To catch harmful behavior and detect attacks by monitoring how users interact with the system.
### Defend against cyber attacks 
- two factor auth, encryption , staff guidelines , keep software updated , create risk profile (identifying which resource can be attacked)

# UNIT 2
## Ethics
Ethics can be defined as a person's moral code of conduct. In computer security, cyber-ethics is what differentiates security personnel from attackers; It defines the capacity to adhere to ethical principles at work and shares knowledge of right and wrong.

Cyber ethics, which examines ethical, legal, and social issues at a common point between
computer/information and communication technologies, is a branch of applied ethics. Cyber ethics is sometimes referred to as information ethics, computer ethics, and Internet ethics

## Ethical issues (PAPA)

**Privacy**

- This refers to how much personal information a person must share and under what conditions.
- People should have the right to keep their information private and not be forced to share it.

**Accuracy**
- Who is responsible for ensuring information is correct?
- It asks who should be accountable for mistakes in information and how to fix the harm caused by incorrect details.

**Property**
- This addresses who owns the information and how it should be fairly exchanged.
- It also considers who controls the channels (like the airwaves) through which information is transmitted and how this resource should be managed.

**Accessibility**
- This looks at who has the right to access certain information and under what conditions.
- It includes the safeguards needed to protect information and prevent misuse.

## Data protecting principle (under privacy)

**1. Data Collection and Purpose Principle**

- Personal data should only be collected for a specific, legal, and fair purpose.
- People (data subjects) must be informed about why their data is collected and who it will be shared with.
- Only necessary data should be collected, no more than needed.

**2. Accuracy and Retention Principle**
- Personal data should be kept only as long as necessary.
- The data must be accurate to fulfill the purpose for which it is used.

**3. Data Security Principle**
- Steps must be taken to protect personal data from unauthorized access, accidental loss, or misuse.

**4. Data Use Principle**
- Personal data must only be used for the specific purpose it was collected for.
- If the data is to be used for a new purpose, consent must be obtained from the individual.
**5. Data Access and Correction Principle**

- Individuals have the right to access their personal data and correct any inaccuracies.

**6. Openness Principle**

- Organizations must make their data policies clear to the public, explaining what personal data they hold and how it is used.

## Method to prevent privacy violation
Here are **9 points to avoid privacy violations**:

1. **Limit Data Collection**  
    Only collect the minimum amount of personal data necessary for your purposes.
    
2. **Obtain Clear Consent**  
    Always ask for explicit, informed consent from individuals before collecting or sharing their data.
    
3. **Encrypt Sensitive Data**  
    Encrypt data both when it's stored and during transmission to prevent unauthorized access.
    
4. **Implement Strong Access Controls**  
    Restrict access to personal data to only those who need it for legitimate purposes.
    
5. **Use Secure Communication Channels**  
    Ensure that all communication channels used for transmitting personal data are secure, such as using HTTPS for websites.
    
6. **Regularly Update and Patch Systems**  
    Keep all software, applications, and systems up-to-date with the latest security patches to protect against vulnerabilities.
    
7. **Minimize Data Retention**  
    Do not keep personal data longer than necessary. Regularly delete or anonymize data that is no longer needed.
    
8. **Educate Employees and Users**  
    Provide training on privacy policies, security practices, and how to recognize privacy risks to employees and users.
    
9. **Allow Access and Correction**  
    Give individuals the right to access their personal data and correct any inaccuracies.
## Intellectual property
Simply, the creation of the mind refers to as Intellectual Property (IP)when someone comes up with the possession of thought or design. Intellectual property means without the owner‘s permission some exclusive rights provided by any creative design owner or any distinct work type, others cannot copy or reuse that work.

### Types of IP
1. **Patent**  
    A patent grants exclusive rights to an inventor for a specific period, typically 20 years, to prevent others from making, using, or selling the invention without permission. It protects new inventions or technological advancements.
    
2. **Copyrights** 
    Copyrights protect original works of authorship, such as literature, music, and art, giving the creator exclusive rights to reproduce, distribute, and perform the work. It lasts for the creator’s lifetime plus a set number of years.
    
3. **Trademark**  
    A trademark is a symbol, word, or other identifiers used by businesses to distinguish their goods or services from others. It helps protect brand identity and reputation in the marketplace.
    
4. **Geographical Locations**  
    Geographical locations refer to areas that are recognized for producing specific products with a certain quality, reputation, or characteristics. These are protected under Geographical Indications (GI) to prevent misuse of regional names.
    
5. **Designs of Industries**  
    Industrial designs protect the visual and aesthetic appearance of products, such as shapes, patterns, or colors, that are new and original. This protection prevents unauthorized reproduction or imitation of the design.
    
6. **Secrets of Trade**  
    Trade secrets refer to valuable, confidential business information like formulas, practices, or processes that give a company a competitive advantage. They are protected as long as they remain secret and provide economic benefit.
    
7. **Layout Designs of Integrated Circuits**  
    Layout designs refer to the unique configuration of elements in integrated circuits, such as microchips. Protection prevents unauthorized copying or use of the layout design by others in the electronics industry.

## Professional and personal ethics
Kindness
Transparency
Accountability
Commitment
Punctuality
Sustainability
Fairness
Least Harm

## Hacking
![](../../statics/Pasted%20image%2020241227112716.png)
## Evidence
Any part of evidence which is generated by some mechanical or electronic type process can be referred to the term 'electronic evidence' used for proving or disproving any kind of fact or the evidence as information to be represent in court.
### Digital evidence
Electronic evidence, also commonly known as digital evidence, is data stored within electronic devices or systems that can be retrieved by forensic experts and used as admissible evidence in court.
### Digital evidence principle
Here’s a simplified version of the principles:

1. **Preserve Data Integrity**  
    Law enforcement must not change any data on computers or storage devices that might be used as evidence in court.
    
2. **Use Original Data Only When Necessary**  
    If it's necessary to use original data, the person must explain their actions and how they relate to the investigation.
    
3. **Create an Audit Trail**  
    A record of all actions taken on the digital evidence must be kept. This ensures others can review and confirm the process.
    
4. **Investigator's Responsibility**  
    The lead investigator is responsible for ensuring that the law and these principles are followed during the investigation.
### Forensic 
Computer forensic:- A field of technology that uses techniques to identify for investigative purpose and store evidence from computer devices is called Computer forensics. Often, it is used to present evidence in court.

![](../../statics/Pasted%20image%2020241227115045.png)
### Digital forensic tools
- Disk Analysis: Autopsy/The Sleuth Kit
- Image Creation: FTK Imager
- Memory Forensics: Volatility
- Windows Registry Analysis: Reorganizing the Registry
- Mobile Forensics: Celebrite UFED
- Network Analysis: Wireshark
- Linux Distribution: Caine

### Digital forensic technique 
1. **Reverse Steganography**  
    Cybercriminals hide information in digital files like images. Reverse steganography is the process of extracting that hidden data from the file, which may not look suspicious at first.    
2. **Stochastic Forensics**  
    This technique helps analyze digital activities that don’t leave clear evidence, like changes caused unintentionally by digital processes. It’s useful for investigating breaches caused by insider threats where no obvious traces are left.
3. **Cross-drive Analysis**  
    This method detects patterns by comparing data across different computer drives. It helps identify suspicious activities by linking similar information across multiple drive    
4. **Live Analysis**  
    Live analysis happens while a device or computer is running. It involves analyzing volatile data (like what’s in RAM) using system tools and is done in a forensic lab to ensure the evidence is preserved correctly.
5. **Deleted File Recovery**  
    Deleted file recovery, also called data carving, is the process of finding partially deleted files by searching through the computer's memory and system for traces of those files.


### Digital evidence collection
![](../../statics/Pasted%20image%2020241227121141.png)
## Cyber crime

### Classification
1. **Cyber Terrorism**  
    Cyber terrorism involves using computers and the internet to carry out harmful acts that could lead to loss of life. It encompasses using software or hardware to threaten or harm citizens.
    
2. **Cyber Extortion**  
    Cyber extortion happens when attackers threaten websites or systems with attacks like denial of service unless a ransom is paid. They demand money in exchange for stopping the attacks and ensuring security.
    
3. **Cyber Warfare**  
    Cyber warfare involves using computers and networks in war zones for offensive or defensive operations. It includes cyberattacks, espionage, and disruption of systems during conflicts.
    
4. **Internet Fraud**  
    Internet fraud uses online platforms to deceive victims by hiding or falsifying information to steal money or property. It covers various illegal activities conducted through the internet.
    
5. **Cyber Stalking**  
    Cyber stalking is the harassment of victims through messages, emails, or offensive comments online. Stalkers often know their targets and may combine online and offline harassment to intensify their actions.

### Types of attack cybercrime
- phishing, ddos, software piracy , hacking
## Password cracking 
### Techniques
1. **Crunch**  
    Crunch generates a list of all possible password combinations to hack passwords. It creates a wordlist used in password cracking attempts on Kali Linux.
    
2. **Rainbow Crack**  
    Rainbow Crack uses precomputed Rainbow Tables to crack password hashes. It compares the stored hash with precomputed hashes to find the matching password without brute force.
    
3. **Burp Suite**  
    Burp Suite is a web application security testing tool. It intercepts and modifies browser requests to find vulnerabilities like XSS or SQL injection, with both free and paid versions available.
    
4. **Maltego**  
    Maltego gathers and visualizes information about networks or organizations from the internet. It helps uncover connections and details about ownership and resources.
    
5. **John the Ripper**  
    John the Ripper is a tool for cracking passwords and hashes using dictionary attacks or customized wordlists. It works on various file types like zipped or locked files.

## Keylogger
- software based ( javascript based , form based). 
- hardware based (usb , smartphone sensor)
- prevention( anti-keylogger , anti virus , form filler automatic , one time password, voice to text )
## spyware 
### Types
- **Adware**: Spyware that tracks user activity to deliver targeted advertisements.
- **Tracking Cookies**: Spyware that collects user activity data and shares it with third parties.
- **Trojan**: Spyware that steals sensitive data like bank details for illegal activities.
- **Keyloggers**: Spyware that records keystrokes to capture sensitive information like passwords.
- **Stalkerware**: Spyware on mobile devices that tracks user movements for third parties.
- **System Monitor**: Spyware that tracks system-wide activities, including calls, chats, and sensitive data.

![](../../statics/Pasted%20image%2020241227123524.png)
## Phishing

1. **Spear Phishing**:  
    Targets specific individuals or organizations to steal financial or sensitive data, often appearing to come from trusted sources.
    
2. **Clone Phishing**:  
    Hackers copy trusted email messages, add fake links, and send them to many users to steal data or spread malware.
    
3. **Cat Phishing**:  
    Attackers manipulate victims emotionally, often through fake dating profiles, to steal money or personal information.
    
4. **Voice Phishing (Vishing)**:  
    Uses fake phone calls or caller IDs to trick victims into sharing private information like credit card numbers.
    
5. **SMS Phishing (Smishing)**:  
    Cybercriminals send fake text messages redirecting users to malicious websites that steal sensitive information.
## Trojan

### Types
1. **Backdoor Trojans:**  
    Allows hackers to remotely control a computer to upload, download, or execute files automatically.
    
2. **Exploit Trojans:**  
    Injects malicious code to exploit weaknesses in specific software.
    
3. **Rootkit Trojans:**  
    Hides existing malware to avoid detection and maximize damage.
    
4. **Banker Trojans:**  
    Targets sensitive banking and financial transaction information.
    
5. **DDoS Trojans:**  
    Executes Distributed Denial of Service (DDoS) attacks to overwhelm and disable networks or systems.
    
6. **Downloader Trojans:**  
    Downloads additional malware, often bringing more Trojans to the device.

#### Trojan
- A Trojan (or Trojan Horse) is malicious software disguised as legitimate or useful software.
- **Purpose:** It tricks users into downloading or running it, granting unauthorized access to attackers.
- **Characteristics:**
    1. Does not replicate itself like a virus.
    2. Can act as spyware, steal data, or provide remote control over the system.

## Backdoor
### Types of Backdoor Exploits

1. **Backdoor Exploits:**  
    Exploits weaknesses in system or software to gain illegal access, such as breaking into banking systems to control online transactions.
2. **Remote Access Backdoor:**  
    Grants hackers remote access via deceptive methods, like fake email security updates that install malware unknowingly.


## Stenography
Steganography is the art and science of embedding secret messages into a cover message in such a way that no one other than the sender and intended recipient suspects the existence of the message.

![](../../statics/Pasted%20image%2020241227124750.png)
![](../../statics/Pasted%20image%2020241227124830.png)

### Types of stenography

1. **Text Steganography:**
    
    - This method involves hiding secret information in text files by manipulating spaces, formatting, or using patterns like capitalized letters or specific word placements.
    - Example: Encoding a message by selectively adding extra spaces between words or lines.
Format Based Method
Random and statistical generation
Linguistic Method
2. **Image Steganography:**
    
    - Hides data in digital images by altering the least significant bits (LSB) of pixel values. These changes are imperceptible to the human eye.
    - Example: Embedding a secret message in the RGB values of an image file.
Least significant bit insertion
Masking and Filtering
Redundant Pattern Encoding
Encrypt and scatter
1. **Video Steganography:**
    
    - Embeds hidden data within video files by modifying frames, inserting extra data in unused bits, or encoding in metadata.
    - Example: Storing information in specific frames of a video or within the compression artifacts of the file.
4. **Audio Steganography:**
    
    - Conceals information within audio files by manipulating frequencies, phase shifts, or by using echo hiding techniques.
    - Example: Embedding a secret message in low-frequency sound waves undetectable to listeners.
5. **Network Steganography:**
    
    - Uses network traffic or protocols to hide data. This can include altering headers, unused fields in packets, or timing intervals between transmissions.
    - Example: Hiding messages in the sequence of packet delivery or using covert channels in communication protocols like TCP/IP.

### Stenography tools
- **StegHide:** Open-source software that allows hiding secret files within image or audio files.
- **Geo Steganography:** Free tool for hiding data in BMP images or WAV files.
- **SSuitePicsel:** Free portable app for hiding text in image files using a unique method.
- **OpenPuff:** Professional tool for storing files as image, audio, video, or flash files with steganography.

# UNIT 3 

## IT Act 2000
punishments for each section under the **Information Technology Act, 2000**:
1. **Section 43**:  
    Punishes unauthorized access, damage, or data theft. If someone gains unauthorized access to a computer system or network, they can be fined up to **₹25 lakhs**. The punishment depends on the severity of the damage caused.
2. **Section 43A**:  
    Deals with compensation for failure to protect sensitive personal data. If an entity fails to implement reasonable security practices leading to a breach, they may be required to pay compensation for loss or damage to the affected individuals.
3. **Section 66B**:  
    Punishes the dishonestly receiving or retaining stolen computer resources or data. The punishment is **up to 3 years of imprisonment** or a fine of **up to ₹1 lakh**, or both.
4. **Section 66C**:  
    Punishes identity theft by using someone's identity without permission, such as accessing or stealing passwords. The punishment includes **up to 3 years of imprisonment** and a fine of **up to ₹1 lakh**.
5. **Section 66D**:  
    Punishes cheating by impersonating someone online. The punishment is **up to 3 years of imprisonment** or a fine of **up to ₹1 lakh**, or both.
6. **Section 66E**:  
    Deals with the violation of privacy, particularly with the sharing of private images or videos without consent. The punishment is **up to 3 years of imprisonment** and a fine of **up to ₹2 lakh**.
7. **Section 66F**:  
    Addresses cyber terrorism, including acts that cause disruption or damage to critical infrastructure. The punishment for cyber terrorism is **imprisonment for life** or **up to 10 years** with a fine, depending on the case's severity.
    
8. **Section 67**:  
    Punishes the publishing or transmitting obscene material in electronic form. The punishment for such acts is **up to 5 years** of imprisonment and a fine of **up to ₹10 lakh** for the first offense, with the possibility of a higher penalty for subsequent offenses.

## Digital signature

A **digital signature** is a cryptographic method used to authenticate the identity of a sender and ensure the integrity of a message or document in the digital world. It serves as an electronic equivalent of a handwritten signature or stamped seal but provides much higher security.

### Key Concepts of Digital Signatures:

1. **Authentication**: It verifies the identity of the sender, ensuring that the message or document actually comes from the claimed sender.
    
2. **Integrity**: It ensures that the content of the message or document has not been altered during transmission. If the content is changed, the digital signature will no longer match.
    
3. **Non-repudiation**: The sender cannot deny sending the message once it has been signed, providing legal proof of the sender’s involvement.

### How Digital Signatures Work:
Digital signatures use **Public Key Infrastructure (PKI)**, which involves two keys:

- **Private Key**: Kept secret by the sender, used to generate the signature.
- **Public Key**: Shared with others, used to verify the signature.

### Process of Creating a Digital Signature:

1. **Hashing**: The document or message is hashed using a hashing algorithm (e.g., SHA-256) to generate a unique hash value.
2. **Encrypting the Hash**: The hash value is encrypted using the sender's private key. This encrypted hash value becomes the digital signature.
3. **Sending the Document**: The sender sends the document along with the digital signature.
4. **Verification**: The recipient uses the sender’s public key to decrypt the digital signature and obtain the original hash. The recipient then hashes the received document. If the hashes match, it verifies both the authenticity and integrity of the document.

### Use Cases:

- **E-commerce**: Ensures secure online transactions.
- **Email Security**: Ensures that the email content has not been tampered with and verifies the sender's identity.
- **Legal Documents**: Used for electronic signatures on contracts, agreements, etc.

### Advantages:

- **Security**: Provides strong encryption and prevents tampering.
- **Trust**: Builds trust in digital communication and transactions.
- **Efficiency**: Fast and secure compared to physical signatures.

In India, digital signatures are legally recognized under the **Information Technology Act, 2000** and are widely used in e-commerce, online banking, and government services.

![](../../statics/Pasted%20image%2020241227163906.png)

### Digital signature attack
**Digital Signature Attacks** refer to various methods used by attackers to break or exploit the digital signature process. Here are the types you mentioned:

### 1. **Attack of Chosen-Message (CMA - Chosen Message Attack)**:

- **Definition**: In a chosen-message attack, the attacker can choose arbitrary messages and obtain their corresponding digital signatures from a legitimate signer.
- **Objective**: The goal is to gather enough signed messages to forge the signature of a new message. The attacker may try to generate a valid signature for an unsigned message using the signatures obtained from previous chosen messages.
- **Attack Process**: The attacker can analyze the relationship between the message and its signature and may attempt to manipulate or create a new message that passes signature verification.
- **Impact**: This type of attack tests the strength of the signature scheme in handling arbitrary message inputs, and if the signature system is not robust, the attacker may find a way to forge signatures.

### 2. **Attack of Known Message (KMA - Known Message Attack)**:

- **Definition**: In a known-message attack, the attacker already knows the message and the corresponding valid signature, and attempts to forge a signature for a different message.
- **Objective**: The attacker uses the known message-signature pair to analyze and potentially discover weaknesses in the signature algorithm, which can be exploited to sign other messages.
- **Attack Process**: The attacker might try to deduce the private key or generate a valid signature for a different message based on the known pair, aiming to deceive others with a forged signature.
- **Impact**: This attack exploits the system's vulnerability to known message-signature pairs and tests whether a new message can be forged using the knowledge of the old signature.

### 3. **Attack of Key-only (KOA - Key-only Attack)**:

- **Definition**: In a key-only attack, the attacker only has access to the public key, but no information about the private key or message.
- **Objective**: The attacker’s goal is to forge a digital signature without the knowledge of the private key by exploiting the relationship between the public key and the signature algorithm.
- **Attack Process**: The attacker may attempt to find weaknesses in the signature scheme, such as exploiting poor implementations or mathematical weaknesses in the algorithm used for signing. If successful, the attacker can generate a valid signature that verifies correctly with the public key.
- **Impact**: This type of attack can lead to the compromise of the integrity of the entire digital signature system if the system has weaknesses that allow for key recovery or signature forgery from just the public key.

### Summary of Attacks:

1. **Chosen-Message Attack**: The attacker chooses arbitrary messages to be signed, then tries to forge signatures for new messages.
2. **Known-Message Attack**: The attacker knows the message and its valid signature and tries to forge a signature for a different message.
3. **Key-only Attack**: The attacker has access to the public key but attempts to forge a signature without knowing the private key or the message content.

These attacks highlight the importance of strong digital signature algorithms and careful implementation to prevent vulnerabilities and ensure the security of digital transactions and communications.


## IT act amendment

- Cyber security measures tightening
- A legal framework for digital signatures establishing
- Identifying and applying intermediaries
- Decryption of electronic records, monitoring and regulating the interception
- Cyber forensics
- Cyber terrorism
![](../../statics/Pasted%20image%2020241227164854.png)

## IPC
- **Section 292 (IPC)**: Prevents the sale or distribution of obscene content, including child exploitation material, with penalties up to 2 years in prison and a fine of Rs. 2000, and up to 5 years and Rs. 50,000 for repeat offenders.
    
- **Section 354C (IPC)**: Criminalizes receiving or publishing unauthorized images of a woman’s private parts or sexual acts, with punishments of up to 3 years for first-time offenders and 7 years for repeat offenders.
    
- **Section 354D (IPC)**: Defines and punishes cyber and physical stalking, including using electronic means to contact an unwilling woman, with up to 3 years in prison for the first offense and up to 5 years for repeat offenses.

## Thread for org
![](../../statics/Pasted%20image%2020241227165401.png)

- Physical:- The hidden basis of an incidence that cause canaffectprobably in the failure as well as the systems damage physically is called physical threat.

## Social Computing
Utilization of social software by organizations and any interested parties, such as partners,
customers, and employees refers as Social Computing. The intersection of social behavior and computational systems is the subject of social computing, a subfield of computer science.

### Social computing ways 
- Social software:- Any system computation, that allows social interaction between people‘s groups. It is also called Application Oriented Social Computing. Such systems examples are as follows. like online gaming , social media , wiki page , blog
- social intelligent computing:- crowd sourcing , dark social media

### Social computing tools 
- online gaming , online dating , blogging , socail media , forums , wiki , crowd sourcing ,RSS.


# UNIT 4
## Critical infrastructure
Critical infrastructure (CI) includes a group of systems and assets, whether it is physical or
virtual, necessary to a nation. Any interruption of its services may have a serious impact on the economic, national security, public health or interests of any large group etc.

The term Information Infrastructure usually refers to define inter-connected computers and
networks, and any information passing through them.

![](../../statics/Pasted%20image%2020241227212104.png)
## Cyber attacks example
- AIIMS attack 2022
- Ukraine power grid 
- iranian cyber attack on new york

## Cyber weapons
![](../../statics/Pasted%20image%2020241227212824.png)

## Framework for improving critical infrastructure 

### Component 
- The Framework Core
- A Framework Profile

### Framework core
The Framework Core provides a set of activities to achieve specific Cyber Security outcomes, and references examples of guidance to achieve those outcomes

The Framework Core consists of four main components that interact as follows:

1. **Functions**: High-level groupings of cybersecurity activities—Identify, Protect, Detect, Respond, and Recover.
2. **Categories**: These align cybersecurity outcomes with program needs and organize them within a function.
3. **Subcategories**: Detailed, actionable outcomes within each category, supporting the achievement of its goals.
4. **Informative References**: Standards, guidelines, or practices that provide methods to achieve subcategory outcomes; they are examples, not exhaustive.

### Framework profile
The alignment of the organization's functions, categories, and subcategories with its business requirements, risk tolerance, and resources is referred to as the Framework Profile (or Profile)

## Framework of cyber attack spectrum
The levels provided can be explained in the context of a cybersecurity framework as stages of increasing sophistication and impact of cybersecurity threats or incidents. Here's how they relate to the framework's core elements:

### **Contextual Mapping to the Framework Core**

1. **Level 1: Network Denied**
    
    - **Function**: Detect, Protect, Respond
    - **Category**: This level focuses on threats that block or deny access to the network, such as Distributed Denial of Service (DDoS) attacks.
    - **Subcategories**: Outcomes might include monitoring traffic, implementing firewalls, or activating intrusion prevention systems.
    - **Informative References**: Standards like NIST SP 800-41 (firewalls) or ISO 27001 (access control policies).
2. **Level 2: Enterprise Denial**
    
    - **Function**: Protect, Recover
    - **Category**: Expands the scope to an organization-wide denial of service or data loss, impacting all critical systems.
    - **Subcategories**: Address comprehensive backup systems, disaster recovery, and redundancy measures.
    - **Informative References**: Guidelines for business continuity (e.g., NIST SP 800-34).
3. **Level 3: Enterprise Manipulation**
    
    - **Function**: Detect, Respond
    - **Category**: Relates to threats where attackers manipulate or alter enterprise systems or data.
    - **Subcategories**: Focus on monitoring changes to system configurations, detecting unauthorized access, and responding to tampering.
    - **Informative References**: Logging and monitoring standards, such as CIS Controls and NIST guidelines.
4. **Level 4: Mission Denied**
    
    - **Function**: Recover, Identify
    - **Category**: Addresses incidents that hinder critical missions or goals of the organization, causing operational failure.
    - **Subcategories**: Include risk management processes, prioritization of recovery activities, and impact assessments.
    - **Informative References**: Incident response frameworks like NIST SP 800-61.
5. **Level 5: Mission Manipulation**
    
    - **Function**: Respond, Recover, Identify
    - **Category**: The most sophisticated level, where attackers manipulate mission-critical outcomes, leading to strategic or operational damage.
    - **Subcategories**: Include advanced threat detection, response strategies, and resilience-building activities.
    - **Informative References**: Advanced Persistent Threat (APT) handling guidelines, such as those in NIST and ISO standards.
