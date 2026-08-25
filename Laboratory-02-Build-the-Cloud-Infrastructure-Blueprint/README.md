# Cloud Computing Laboratory

## Mission Overview

This laboratory activity focused on exploring a Linux environment and understanding the basic components of cloud computing infrastructure. Using the KillerCoda Playground, I investigated the system information, identified cloud infrastructure components, compared services from major cloud providers, and designed a simple cloud architecture.

The activities provided hands-on experience with Linux commands and helped me understand how compute, storage, networking, and operating systems work together in a cloud environment.

---

## Objectives

The objectives of this laboratory activity are:

* Explore and investigate a Linux environment using KillerCoda.
* Identify important system information such as the operating system, kernel, CPU, memory, storage, hostname, and IP address.
* Understand the major components of cloud infrastructure.
* Identify equivalent cloud services offered by AWS, Microsoft Azure, and Google Cloud Platform.
* Design a simple cloud infrastructure architecture.
* Practice documenting technical activities using Markdown and GitHub.

---

## Cloud Infrastructure Components

The following cloud infrastructure components were identified in the Linux environment:

### Compute Resources

Compute resources are responsible for processing instructions and running applications. In the KillerCoda environment, the CPU was identified using the `lscpu` command.

Example:

* **CPU Model:** Intel Xeon E312xx
* **CPU Cores:** 1

In cloud computing, compute resources provide the processing power needed to run applications, virtual machines, and services.

### Storage Resources

Storage resources are used to store files, applications, system data, and other information. The `df -h` commands were used to investigate disk devices and mounted file systems.

In cloud computing, storage is important because applications and users need a reliable place to save and access data.

### Networking Resources

Networking resources allow systems, users, and cloud services to communicate with each other. The IP address and network configuration can be viewed using commands such as `hostname -I`.

In cloud computing, networking connects users to cloud services and allows different cloud resources to communicate securely.

### Operating System

The Linux environment provided by KillerCoda uses:

* **Operating System:** Ubuntu 24.04.4 LTS
* **Kernel Version:** 6.8.0-136-generic

The operating system manages hardware and software resources and provides an environment where applications and services can run.

---

## Tools Used

The following tools were used during the laboratory activities:

* **KillerCoda Playground** – Used to access and explore the Linux environment.
* **GitHub** – Used to store and manage the laboratory documentation and files.
* **Markdown** – Used to create technical documentation.
* **Draw.io / Diagramming Tool** – Used to design the simple cloud infrastructure diagram.
* **Linux Terminal** – Used to execute commands and investigate the system.

---

## Linux Commands Executed

The following Linux commands were executed during the laboratory activities:

```bash
lsb_release -a
```

Displays the Linux operating system information.

```bash
uname -r
```

Displays the current Linux kernel version.

```bash
lscpu
```

Displays information about the CPU, including the processor model and number of CPU cores.

```bash
free -h
```

Displays information about storage devices and partitions.

```bash
df -h
```

Displays disk usage and mounted file systems.

```bash
hostname
```

Displays the hostname of the Linux system.

```bash
hostname -I
```
---

## Skills Learned

Through this laboratory activity, I learned the following skills:

* Basic Linux command-line navigation and system investigation.
* Identifying operating system and kernel information.
* Checking CPU, memory, and storage resources.
* Identifying the main components of cloud infrastructure.
* Comparing cloud services from AWS, Microsoft Azure, and Google Cloud Platform.
* Understanding equivalent cloud services across different providers.
* Creating a simple cloud infrastructure diagram.
* Writing technical documentation using Markdown.
* Organizing and managing laboratory files using GitHub.

---

## Challenges Encountered

One of the challenges encountered during the activity was understanding the different Linux commands and interpreting their output. Some cloud providers also use different names for similar services, which initially made comparing AWS, Microsoft Azure, and Google Cloud Platform challenging.

Another challenge was organizing the technical documentation and ensuring that the Markdown files were properly formatted. These challenges were addressed by reviewing the command outputs, comparing the purpose of cloud services, and organizing the documentation into clear sections.

---

## Conclusion

This laboratory activity provided practical experience in exploring a Linux environment and understanding the basic components of cloud computing. By using KillerCoda and Linux commands, I was able to investigate compute, storage, networking, and operating system resources.

The activity also helped me understand how AWS, Microsoft Azure, and Google Cloud Platform provide similar cloud infrastructure services under different names. Overall, this laboratory improved my Linux, cloud computing, technical documentation, and GitHub skills.
