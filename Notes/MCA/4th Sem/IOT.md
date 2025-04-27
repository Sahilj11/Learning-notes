# UNIT 1
## Intro/Defination
- Cloud computing: A procedure for enabling network-based, on-demand access to a shared pool of computer resources, such as servers, storage, applications, and services (usually the internet). With little assistance from management or service providers, these resources may be released and deployed quickly allowing users to scale their use up or down as needed.
- Infrastructure as a Service (IaaS): a cloud service delivery paradigm that gives consumers pay-per-use access to virtualized computer resources like servers, storage, and networking parts. The virtualized infrastructure that IaaS consumers normally control can be changed, but are responsible for managing and maintaining their own software applications and data
- Platform as a Service (PaaS): a cloud service paradigm that offers users a network-based environment for creating, deploying, and managing software applications. PaaS users typically have access to a pre-configured platform that includes tools, libraries, and other resources to facilitate software development and deployment, while the operating system and supporting infrastructure are taken care of by the service provide
- Software as a Service (SaaS): a cloud service paradigm that enables customers to connect to and utilise software hosted and controlled by a service provider over a network. SaaS users typically pay a subscription fee and have little control over the underlying infra or code

## Evolution
- Early Days:-In the early days of computing, businesses and organizations relied on mainframe computers to store and process their data. These mainframes were large, expensive, and required a dedicated team of IT professionals to manage them
- Birth of internet:- The birth of the internet in the 1990s revolutionized the way we store and access information. With the internet, it became possible to share data and applications across different locations and devices. This created the framework for the growth of cloud computing.
- Emergence of Cloud Computing:- he term "cloud computing" was coined in 2006 by Eric Schmidt, the CEO of Google at the time. Cloud computing was born out of the need to provide businesses with more flexibility and scalability in their IT infrastructure. Cloud computing enables organisations to access and store data and apps online, without the need for on-site servers or IT staff.
- Evolution of cloud computing:- Since its inception, cloud computing has evolved significantly. In the early days, cloud computing was primarily used for storage and data backup. Today, cloud computing has expanded to include a variety of services, such as software as a service, platform as a service, and infrastructure as a service (SaaS)
- ![](../../statics/Pasted%20image%2020250427120837.png)

## Traditional vs Cloud Computing
| **Traditional Computing**                                   | **Cloud Computing**                                                                                                      |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| On-premises hardware and software                           | Remote servers and internet-based services                                                                               |
| IT infrastructure managed by business/organization          | IT infrastructure managed by cloud provider                                                                              |
| Computing resources accessed from a specific location       | Computing resources accessed from anywhere with internet                                                                 |
| Businesses/organizations responsible for their own security | Cloud providers have robust security measures, but businesses/organizations are still responsible for their own security |
## SaaS,PaaS,IaaS
![](../../statics/Pasted%20image%2020250427121036.png)
## Cloud Deployment Models
- The four primary cloud deployment models—public, private, hybrid, and community cloud
### Public
A sort of cloud computing architecture known as the "public cloud" allows for the delivery
of cloud services via the internet by independent cloud providers. It is available to the
general public, and anyone can use it by paying a fee or on a pay-per-use basis. Public
clouds provide scalability, flexibility, and cost-effectiveness, which makes them ideal for
small and medium-sized businesses. Public cloud services include SaaS, PaaS, and IaaS
### Private Cloud
An organisation or a single entity owns and manages a private cloud, commonly referred
to as an internal or corporate cloud. It is not accessible to the public, and its services are
available only to authorized users within the organization. Private cloud services are
designed to meet the specific requirements of an organization and provide complete control
over data security and privacy. Private clouds are ideal for organizations that require a high
level of security, compliance, and customization.
### Hybrid Cloud
Public and private cloud deployment models are combined to create a hybrid cloud. It gives
businesses the freedom to select the optimum cloud deployment approach for their
particular requirements. With a hybrid cloud, businesses can use private cloud services for
sensitive data and public cloud services for less-sensitive data. For businesses that need the
advantages of both public and private cloud deployment options, hybrid clouds are the best
option.
### Community Cloud
A community cloud is a kind of cloud deployment platform that several businesses with
comparable objectives or needs share.. It is a collaborative platform where organizations
share resources, applications, and infrastructure to achieve their common objectives.
Community clouds are suitable for industries such as healthcare, government, education,
and finance, where organizations have to comply with strict regulations and share common
resources.

![](../../statics/Pasted%20image%2020250427121332.png)
## +ve and -ves


---

###  Advantages of Cloud Computing:

1. **Cost-Effective**
    
    - Avoids upfront hardware and software costs.
        
    - Pay-as-you-go model saves money by paying only for what is used.
        
2. **Scalability and Flexibility**
    
    - Easily scale resources up or down based on demand.
        
    - Manage peak loads without high additional costs.
        
3. **Disaster Recovery**
    
    - Provides offsite data backup solutions.
        
    - Reduces risk of data loss and enables quick recovery after emergencies.
        
4. **Collaboration**
    
    - Supports real-time collaboration among employees across different locations.
        
    - Improves productivity and teamwork.
        
5. **Accessibility**
    
    - Access applications and data from anywhere via internet-connected devices.
        
    - Supports remote work and easy data access.
        

---

### Challenges of Cloud Computing:

- **Security and Privacy Concerns**  
    (Sensitive data stored offsite might be vulnerable without strong safeguards.)
    
- **Downtime and Reliability**  
    (Internet outages or cloud service disruptions can affect business operations.)
    
- **Compliance and Legal Issues**  
    (Companies must ensure they meet industry regulations regarding data storage.)
    
- **Limited Control**  
    (Less control over infrastructure and services compared to on-premises systems.)
    
- **Hidden Costs**  
    (Costs can rise unexpectedly with data transfer fees, storage, or additional services.)
    
## Virtualization and Cloud Computing
### Definition
Virtualization: A virtual version of something, such as an operating system, server, storage
device, or network resource, can be created through the process of virtualization. It entails
adding an abstraction layer between the physical hardware and the software that runs on it,
allowing several operating systems or applications to effectively share resources on a single
physical computer

Server virtualization: The process of splitting a physical server into several virtual
machines (VMs), each with its own operating system and applications, is known as server
virtualization. As a result, hardware costs are decreased, resource utilisation is increased 
and flexibility and scalability are provided. It also enables the running of different
workloads on a single physical server.


Amazon Elastic Compute Cloud (EC2): A web service called Amazon EC2 offers
scalable compute capability in the cloud. By only paying for the capacity they actually use,
it enables users to rapidly and easily deploy and scale virtual servers on Amazon's
infrastructure. EC2 is a crucial part of Amazon Web Services (AWS), a cloud platform that
provides a wide range of services to assist businesses in developing and deploying cloud-
based applications.


## Hypervisor Overview

- A hypervisor, also called a Virtual Machine Monitor (VMM), allows multiple Virtual Machines (VMs) to run on a single physical machine.
    
- It creates a virtual environment where each VM operates independently from the underlying hardware.
    
- Each VM can run its own operating system.
    
- The hypervisor allocates hardware resources like CPU, memory, and storage to each VM as needed.
    

## Types of Hypervisors

1. **Type 1 Hypervisor (Bare-metal or Native Hypervisor)**
    
    - Runs directly on the physical hardware.
        
    - More efficient and secure compared to Type 2 hypervisors.
        
    - Commonly used in enterprise environments.
        
2. **Type 2 Hypervisor (Hosted Hypervisor)**
    
    - Runs on top of the host machine’s operating system.
        
    - Easier to set up for personal or small-scale use, but generally less efficient.
        

## Benefits of Virtualization

- **Server Consolidation**
    
    - Multiple VMs can run on a single physical server.
        
    - Reduces the need for additional hardware and lowers associated costs.
        
- **Rapid Provisioning**
    
    - Enables quick deployment of new systems.
        
    - Facilitates faster response to business needs.
        
- **Improved Reliability and Availability**
    
    - In case of physical server failure, VMs can be migrated to another server without downtime.
        
    - Feature known as VM migration or live migration.
        
- **Enhanced Security**
    
    - Each VM is isolated from others, minimizing the risk of breaches across VMs.
        
- **Sandbox Testing**
    
    - New applications or software can be tested in an isolated environment.
        
    - Protects the production environment from potential disruptions.
        

## Importance in Cloud Computing

- Virtualization is a foundational technology for cloud computing.
    
- It supports cost-effective and efficient computing infrastructure.
    
- Helps businesses achieve scalability, flexibility, and improved system management.


## Popular Virtualization Technologies

### VMware

- One of the leading virtualization technologies in the market.
    
- Offers comprehensive solutions for both desktop and server virtualization.
    
- **VMware ESXi** is a popular hypervisor that enables creation of multiple VMs on a single physical server.
    
- Provides high reliability, performance, and supports a wide range of operating systems.
    

### Hyper-V

- Developed by Microsoft and integrated into Windows Server.
    
- Allows the creation of multiple virtual machines on a single physical server.
    
- Offers advanced features like live migration, network virtualization, and storage virtualization.
    
- Best suited for organizations running Windows-based workloads due to seamless integration with the Windows ecosystem.
    

### KVM (Kernel-based Virtual Machine)

- Open-source virtualization technology included in the Linux kernel.
    
- Provides a portable and efficient virtualization platform.
    
- Supports a variety of guest operating systems.
    
- Popular among businesses looking for a versatile and cost-effective virtualization solution.
    

### Xen

- Open-source virtualization technology for desktops and servers.
    
- Offers high scalability and performance.
    
- Supports a wide range of guest operating systems.
    
- Suitable for organizations that need high performance and scalability for their virtualization workloads.
