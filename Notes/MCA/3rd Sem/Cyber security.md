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