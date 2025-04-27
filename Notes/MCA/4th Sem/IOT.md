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
## Virtual Migration Techniques
Moving a virtual machine (VM) from one physical host to another, whether it is active or
not, is known as virtual machine migration. This operation is typically done to balance the
workload or carry out maintenance without interrupting services. Virtualization and cloud
computing are not complete without VM migration solutions, which give administrators
the opportunity to maximise resource utilisation and improve service availability.
### 1. Live Migration
- Moves an active virtual machine (VM) from one physical host to another **without stopping** its services.
- Requires a **shared storage infrastructure** that allows both physical hosts to access the same disk images.
- Commonly used to:
    - Optimize resource usage,
    - Balance workloads,
    - Perform maintenance tasks without downtime.
- Widely used in cloud computing to enhance availability and resource optimization.

### 2. Cold Migration
- Involves **stopping** the VM before moving it to another physical host.
- The VM's disk image is copied to the new host and then started.
- Does **not** require shared storage infrastructure.
- Simple and reliable, but causes **brief service interruption**, making it less ideal for critical services.

### 3. Storage Migration
- Transfers a VM's **storage** from one physical host to another.
- Often used along with live or cold migration to:
    - Move VMs to faster or larger storage systems,
    - Support business continuity and disaster recovery.
- Can relocate a VM’s storage to a different physical location if needed.

### 4. Cross-Platform Migration
- Moves a VM from one **virtualization platform** to another.
- Useful for:
    - Migrating from legacy to modern virtualization platforms,
    - Consolidating multiple platforms into a single one.
- Requires **conversion** of the VM’s disk image and configuration to a new format.    
- Can be complex and time-consuming.
## EC2

### Overview

- **Amazon EC2** is a web service by AWS allowing users to **rent virtual computers** to run their applications.
    
- Provides **scalable computing capacity** in the cloud for quick and easy application deployment.
    

### Key Features

- **Instance Types**:
    
    - Wide range tailored to specific needs.
        
    - Some optimized for **memory-intensive** workloads, others for **compute-intensive** tasks.
        
    - Users choose based on their application requirements and pay only for what they use.
        
- **Amazon Machine Images (AMIs)**:
    
    - Pre-configured images with OS and required applications.
        
    - Users can also create **custom AMIs** with their own configurations.
        
- **Storage Options**:
    
    - **Amazon Elastic Block Store (EBS)**: Persistent block-level storage volumes for EC2 instances.
        
    - **Amazon Elastic File System (EFS)**: Scalable file storage for EC2 instances.
        

### Key Benefits

- **Scalability**:
    
    - Easily launch or terminate instances based on demand.
        
    - Helps manage costs by paying only for needed capacity.
        
- **Flexibility**:
    
    - Freedom to choose **operating systems**, **software**, and **instance configurations**.
        
    - Wide range of **networking** and **security options** for secure connections to other resources.
        

### Conclusion
- **Amazon EC2** is a **powerful and flexible** service ideal for many applications and workloads.    
- Its instance variety, storage solutions, scalability, and security features make it a popular choice for businesses and developers.

# UNIT 3

## Features of Public Cloud Computing

- **Third-party Managed Infrastructure**:  
    Computing services like storage, processing power, and applications are provided by third-party vendors.
    
- **Internet-Based Access**:  
    Services are available online to anyone with an internet connection and payment method.
    
- **Shared Resource Pool**:  
    Multiple customers share the same pool of computing resources maintained by the provider.
    
- **Large Provider Networks**:  
    Offered by major technology firms like Amazon, Microsoft, and Google with global server and storage networks.
    
- **High Scalability and Flexibility**:  
    Resources can be easily provisioned and scaled up or down without major upfront investments.
    
- **High Availability and Reliability**:  
    Providers offer Service Level Agreements (SLAs) ensuring uptime and performance.
    
- **Pay-Per-Use Pricing Model**:  
    Users only pay for the resources they consume, reducing total cost of ownership
## Why Public Cloud 

- **Cost Effectiveness**:  
    Pay only for the resources used, avoiding the need for large upfront investments in infrastructure.
    
- **Scalability**:  
    Easily scale resources up or down based on demand, ensuring efficient resource management.
    
- **Flexibility**:  
    Wide range of resources and services available — from storage and processing to advanced services like data analytics and machine learning.
    
- **Accessibility**:  
    Services can be accessed from anywhere with an internet connection.
    
- **Security**:  
    Advanced, cutting-edge security measures are provided by public cloud vendors to protect data and applications.
    
- **Collaboration**:  
    Teams can easily collaborate and share information across different locations, boosting productivity and efficiency.
    
- **Innovation**:  
    Continuous introduction of new services and technologies, giving businesses access to the latest tools without needing heavy investment.

## Public Cloud Service Model
- IaaS
	- Uses
		- Test and Development Environment
		- Web Hosting
		- Big Data Processing
		- Disaster Recovery:- aaS can also be used for disaster recovery, as it provides a cost-effective way to replicate data and applications to an off-site location.
- PaaS
- SaaS
- Disaster Recovery as a Service (DRaaS), 
- Database as a Service (DBaaS)
- Security as a Service

## Offerings and Vendor
| Category | Offering                         | Vendor                      | Description                                                    |
| -------- | -------------------------------- | --------------------------- | -------------------------------------------------------------- |
| **IaaS** | Amazon EC2                       | Amazon Web Services (AWS)   | Virtual servers to run applications.                           |
|          | Amazon S3                        | Amazon Web Services (AWS)   | Scalable object storage service.                               |
|          | Amazon EBS                       | Amazon Web Services (AWS)   | Persistent block storage for EC2.                              |
|          | Microsoft Azure Virtual Machines | Microsoft Azure             | Virtual machines for deploying apps.                           |
|          | Google Compute Engine            | Google Cloud Platform (GCP) | Scalable virtual machine instances.                            |
|          | IBM Cloud Infrastructure         | IBM Cloud                   | Virtual servers, storage, and networking.                      |
|          | Oracle Cloud Infrastructure      | Oracle Cloud                | High-performance compute and storage.                          |
| **PaaS** | AWS Elastic Beanstalk            | Amazon Web Services (AWS)   | Platform to deploy and manage applications automatically.      |
|          | Google App Engine                | Google Cloud Platform (GCP) | Fully managed platform for app development.                    |
|          | Microsoft Azure App Service      | Microsoft Azure             | Hosting service for web apps and APIs.                         |
|          | Heroku                           | Salesforce                  | Cloud platform for easy app deployment and scaling.            |
|          | Red Hat OpenShift                | Red Hat (IBM)               | PaaS for containerized application development.                |
|          | Oracle Cloud Platform            | Oracle Cloud                | Platform services for application development and integration. |

## AWS Storage and Database Services

### Storage Services:

1. **Amazon S3 (Simple Storage Service)**:
    
    - Object-based storage service.
        
    - Highly scalable, durable, and available.
        
    - Replicates data across multiple sites.
        
    - Used for storing images, videos, logs, and backups.
        
2. **Amazon EBS (Elastic Block Store)**:
    
    - Block-based storage service for EC2 instances.
    - Offers various volume types (SSD, HDD) for different use cases.
    - Provides encryption for data both in transit and at rest.
        
3. **Amazon EFS (Elastic File System)**:
    - File-based storage for Linux workloads.
    - Scalable, highly available, and durable.
    - Can be mounted on multiple EC2 instances simultaneously.

### Database Services:
1. **Amazon RDS (Relational Database Service)**:
    - Managed relational database service (supports MySQL, PostgreSQL, Oracle, SQL Server).
    - Provides high availability, durability, and automated backups.
2. **Amazon DynamoDB**:
    - NoSQL database service.
    - Offers fast and reliable performance with automatic scaling.
    - Provides encryption in transit and replication across multiple availability zones.
3. **Amazon Aurora**:
    - Cloud-native relational database engine.
    - Compatible with MySQL and PostgreSQL.        
    - High performance, scalability, and availability with automatic multi-AZ replication.

## Private vs Public Cloud 
| Feature           | Public Cloud                                                           | Private Cloud                                                                          |
| ----------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **Cost**          | More cost-effective (pay-as-you-go, no infrastructure investment).     | High upfront investment and ongoing maintenance costs.                                 |
| **Security**      | Shared infrastructure; relatively more vulnerable to security threats. | Higher security with full control over infrastructure and data.                        |
| **Compliance**    | May face challenges meeting strict compliance requirements.            | Better suited for industries with strict compliance needs (e.g., healthcare, finance). |
| **Scalability**   | Unlimited scalability; easy to add or remove resources.                | Limited scalability; resource expansion can be difficult.                              |
| **Customization** | Less customization; managed by cloud service provider.                 | High customization; tailor infrastructure and applications to specific needs.          |
