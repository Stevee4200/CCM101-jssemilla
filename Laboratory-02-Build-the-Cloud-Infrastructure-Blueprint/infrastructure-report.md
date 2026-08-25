# Infrastructure Report

## Linux Environment Investigation

## 1. System Information

| Information              | Findings                                      |
| ------------------------ | --------------------------------------------- |
| **Operating System**     | Ubuntu 24.04.4 LTS                            |
| **Kernel Version**       | 6.8.0-136-generic                             |
| **CPU Model**            | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| **Number of CPU Cores**  | 1 CPU Core                                    |
| **Total RAM**            | Check using `free -h`                         |
| **Disk Capacity**        | Check using `df -h`                           |
| **Mounted File Systems** | Check using `df -h`                           |
| **Hostname**             | Check using `hostname`                        |
| **IP Address**           | Check using `hostname -I` or `ip addr`        |

---

## 2. Commands Used for Investigation

The following Linux commands were used to investigate the system:

```bash
lsb_release -a
```

This command displays the Linux operating system description.

```bash
uname -r
```

This command displays the current Linux kernel version.

```bash
lscpu
```

This command displays information about the processor, including the CPU model and number of CPU cores.

```bash
free -h
```


This command displays information about available storage devices and their capacity.

```bash
df -h
```

This command displays disk usage and mounted file systems.

```bash
hostname
```

This command displays the name of the current Linux machine.

```bash
hostname -I
```

This command displays the IP address assigned to the Linux environment.

---

## 3. Screenshots of Investigation

### Operating System and Kernel Version


```bash
uname -r
```

### CPU Information


```bash
lscpu
```

### Memory Information


```bash
free -h
```

### Disk and Mounted File Systems


```bash
df -h
```

### Hostname and IP Address


```bash
hostname
hostname -I
```

---

## 4. Summary

The Linux environment was investigated using several basic Linux commands through the KillerCoda terminal. The system is running **Ubuntu 24.04.4 LTS** with kernel version **6.8.0-136-generic**. The processor is identified as an **Intel Xeon E312xx**, and the environment has **1 CPU core**.

Additional commands such as `free -h`, `df -h`, `hostname`, and `hostname -I` were used to gather information about the system's memory, disk capacity, mounted file systems, hostname, and IP address.

This activity helped demonstrate how Linux commands can be used to investigate and document the infrastructure and resources of a computing environment.
