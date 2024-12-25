## Hypervisor

#### **What is a Hypervisor?**

A hypervisor, also known as a virtual machine monitor (VMM), is software, firmware, or hardware that creates and manages virtual machines (VMs). It allows multiple operating systems to share a single hardware host by abstracting and allocating hardware resources to each VM.
### **Types of Hypervisors**

Hypervisors are broadly classified into two types: **Type 1 (Bare-Metal)** and **Type 2 (Hosted)**.

#### **Type 1 Hypervisor (Bare-Metal)**

- **Definition**: Runs directly on the physical hardware without requiring a host operating system.
- **Examples**: VMware ESXi, Microsoft Hyper-V, Xen, KVM.
#### **Type 2 Hypervisor (Hosted)**

- **Definition**: Runs on top of a host operating system, relying on it for device drivers and hardware interactions.
- **Examples**: VMware Workstation, Oracle VirtualBox, Parallels Desktop.
## Containers
![](../../statics/Pasted%20image%2020241221150137.png)
Containers are lightweight, portable units of software that bundle an application and all its dependencies (libraries, runtime, tools, and configuration files) into a single package. Containers ensure that the application runs consistently across various environments, from development to production, regardless of differences in the underlying infrastructure.

![](../../statics/Pasted%20image%2020241221150350.png)
![](../../statics/Pasted%20image%2020241221150610.png)

### **Key Differences**

|**Aspect**|**Containers**|**Virtual Machines (VMs)**|
|---|---|---|
|**Architecture**|Share the host OS kernel.|Include a full OS and run on a hypervisor.|
|**Isolation Level**|Process-level isolation using namespaces and cgroups.|Full isolation with a dedicated OS per VM.|
|**Resource Usage**|Lightweight and efficient; shares host resources.|Resource-heavy; requires dedicated OS and hardware emulation.|
|**Startup Time**|Starts in seconds or less.|Takes minutes to boot, as a full OS is loaded.|
|**Size**|Small (MBs) due to shared OS kernel.|Large (GBs) as each VM has its own OS.|
|**Performance**|Near-native performance; low overhead.|Higher overhead due to hardware emulation.|
|**Portability**|Highly portable across different environments.|Less portable; tied to hypervisor and hardware.|
|**Management**|Easier to deploy and manage with tools like Docker.|Requires more complex setup and management.|
|**Security**|Weaker isolation as containers share the host OS kernel.|Stronger isolation with dedicated OS for each VM.|
|**Use Cases**|Microservices, CI/CD pipelines, modern apps.|Running legacy apps, OS-specific workloads, and complex environments.|

## Tech docker use of linux
### Namespaces 
A **namespace** in Linux is a feature that isolates resources for processes, creating a separate environment for them. It allows multiple processes to think they have their own dedicated resources (e.g., files, network, or processes), even though they share the same underlying system.

Think of namespaces as "bubbles" where each bubble has its own view of certain system resources. Processes inside a namespace can only see and interact with the resources assigned to that namespace.
![](../../statics/Pasted%20image%2020241221151117.png)
### Cgroups 
![](../../statics/Pasted%20image%2020241221151207.png)
### Union Mount
![](../../statics/Pasted%20image%2020241221151319.png)


The **union mount system** in Linux is a feature that allows the combination of multiple file systems into a single, unified file system. It enables files and directories from different layers to appear as if they exist in one cohesive directory structure.

### **What is a Union File System?**

A **union file system**:

- Merges multiple file system layers.
- Allows each layer to be read-only or writable.
- Supports **copy-on-write (CoW)**: Changes made to a file in a read-only layer are stored in a writable layer instead of modifying the original file.

Examples of union file systems in Linux:

- **OverlayFS** (most commonly used by Docker)

### **How Docker Uses Union Mounts**

Docker uses the union mount system to manage container layers efficiently. Each container image and its changes are represented as layers in a union file system.

#### **Key Concepts**

1. **Image Layers**: Docker images are made up of multiple read-only layers. Each layer contains part of the file system required by the container.
2. **Writable Container Layer**: When a container is created, a new writable layer is added on top of the image layers. This writable layer is unique to the container.
3. **Copy-on-Write**: If a file in a lower (read-only) layer is modified, Docker copies it to the writable layer and then applies changes. The original file remains unchanged in the lower layer.
![](../../statics/Pasted%20image%2020241221151803.png)

### **How It Works in Practice**

1. **Pulling an Image**:
    
    - When you pull a Docker image (e.g., `ubuntu:latest`), Docker downloads the layers of the image.
    - Each layer represents part of the file system (e.g., base OS, application files, configurations).
2. **Starting a Container**:
    
    - Docker creates a **union mount** using the image layers as read-only and adds a writable layer for the container.
    - Changes made during the container runtime (e.g., creating files, installing software) are stored in the writable layer.
3. **Stopping a Container**:
    
    - The writable layer persists until the container is deleted.
    - The original image layers remain unchanged and can be reused by other containers.
## Data in container
![](../../statics/Pasted%20image%2020241221152950.png)

### **Volume Mount vs Bind Mount in Docker**

Both **volume mounts** and **bind mounts** are used to manage how data is shared between a Docker container and the host machine. However, they differ in functionality, flexibility, and use cases.

---

### **1. Bind Mounts**

- **Definition**: Bind mounts link a directory or file on the host system directly to a container.
- **Host Directory**: The host directory must exist; Docker does not manage it.
- **Flexibility**: Useful when you want to share specific files or directories from the host with the container.

#### **Key Characteristics**

- **Location**: You specify an absolute path on the host (e.g., `/home/user/data`).
- **Management**: Docker does not manage or isolate bind mounts; you control the files directly on the host.
- **Performance**: Bind mounts are fast since they are simple file system links.

#### **Use Cases**

- Sharing source code between the host and container during development.
- Accessing logs or configuration files from the host system.

#### **Example**

```bash
docker run -v /path/on/host:/path/in/container myimage
```

This mounts `/path/on/host` to `/path/in/container`.

---

### **2. Volume Mounts**

- **Definition**: Volumes are managed by Docker and are stored in Docker's storage space on the host.
- **Docker-Managed**: Docker creates and manages the volume lifecycle and handles mounting.
- **Flexibility**: Better suited for persistent, container-independent data.

#### **Key Characteristics**

- **Location**: Volumes are stored in Docker's storage directory (e.g., `/var/lib/docker/volumes/`).
- **Isolation**: Volumes are isolated from the host, which enhances security and consistency.
- **Persistence**: Volumes persist even if the container is deleted (unless you explicitly remove them).

#### **Use Cases**

- Storing database files or application data.
- Sharing data between containers.
- Ensuring data persists across container restarts or rebuilds.

#### **Example**

```bash
docker run -v myvolume:/path/in/container myimage
```

This mounts the Docker-managed volume `myvolume` to `/path/in/container`.

---

### **Key Differences**

|**Feature**|**Bind Mount**|**Volume Mount**|
|---|---|---|
|**Location**|Host-defined directory (absolute path)|Docker-managed storage location|
|**Creation**|Must pre-exist on the host|Automatically created by Docker|
|**Management**|Host-managed|Docker-managed|
|**Isolation**|Direct access to host files|Isolated from host; managed by Docker|
|**Portability**|Not portable across hosts|Portable across hosts (via `docker volume`)|
|**Security**|Depends on host directory permissions|More secure; isolated from host directory|
|**Performance**|Fast|Optimized for Docker-managed workloads|

---

### **When to Use Which**

#### **Bind Mounts**

- Use for **development**: When you need direct access to files on the host.
- Temporary sharing of files between host and container.

#### **Volume Mounts**

- Use for **production**: For persistent data like databases or application data.
- Sharing data between multiple containers.

---

Would you like a detailed example or tutorial on setting up either?