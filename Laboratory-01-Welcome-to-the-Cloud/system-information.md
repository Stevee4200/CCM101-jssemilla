# System Information

This document contains the system information gathered from the KillerCoda Ubuntu environment.

---

## Linux Distribution

**Description:** Ubuntu 24.04.4 LTS

```bash
$ lsb_release -d

Description: Ubuntu 24.04.4 LTS
```

---

## Kernel Version

**Kernel Release:** 6.8.0-136-generic

```bash
$ uname -r

6.8.0-136-generic
```

---

## CPU Information

| Property | Value |
|----------|-------|
| Architecture | x86_64 |
| CPU Model | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| CPU(s) | 1 |
| Thread(s) per Core | 1 |
| Core(s) per Socket | 1 |
| Socket(s) | 1 |
| Hypervisor | KVM |
| Virtualization Type | Full |

```bash
$ lscpu
```

---

## Memory Information

| Property | Value |
|----------|-------|
| Total Memory | 1.9 GiB |
| Used Memory | 427 MiB |
| Free Memory | 850 MiB |
| Available Memory | 1.4 GiB |
| Swap Memory | 1.0 GiB |

```bash
$ free -h
```

---

## Disk Space

| Filesystem | Size | Used | Available | Use% | Mounted On |
|------------|------|------|-----------|------|------------|
| /dev/vda1 | 19G | 5.4G | 13G | 30% | / |
| /dev/vda16 | 881M | 117M | 703M | 15% | /boot |
| /dev/vda15 | 105M | 6.2M | 99M | 6% | /boot/efi |

```bash
$ df -h
```

---

## Summary

| Category | Details |
|----------|---------|
| Linux Distribution | Ubuntu 24.04.4 LTS |
| Kernel Version | 6.8.0-136-generic |
| CPU | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| Architecture | x86_64 |
| Total Memory | 1.9 GiB |
| Available Disk Space | 13G on the root (`/`) filesystem |
| Virtualization | KVM (Full Virtualization) |
