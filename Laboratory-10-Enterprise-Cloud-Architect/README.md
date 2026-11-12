# Enterprise Cloud Architect

## Project Overview

**CloudNova** is a cloud computing project created for CCM101. Its main purpose is to demonstrate the process of building, deploying, managing, and securing a web application using virtualization and container technology.

The project uses Ubuntu Server as its main operating system and runs two connected services: WordPress and MariaDB. WordPress is responsible for displaying the website, while MariaDB manages and stores the website's information.

It also provides additional features such as network security, protected remote access, persistent storage, and scheduled database backups to help maintain the system.

## Project Objectives

- Set up a Linux server using Oracle VirtualBox.
- Configure network connections between the laptop and the virtual machine.
- Install Docker and Docker Compose.
- Deploy WordPress and MariaDB as connected services.
- Set up storage to keep application and database data safe.
- Protect the server using firewall rules and secure SSH access.
- Create a Bash script for automatic database backups.
- Schedule backups using Cron.
- Document the setup and maintenance procedures.

## System Architecture

The CloudNova infrastructure consists of the following components:

1. **Host Machine:** A Windows 11 laptop used to access and manage the virtual server.
2. **VirtualBox:** The virtualization software responsible for running Ubuntu Server.
3. **Ubuntu Server:** The main server environment where Docker and the application services operate.
4. **Network:** NAT provides internet connectivity, while Host-only networking allows communication between the laptop and the virtual machine.
5. **Firewall:** UFW and Docker firewall rules help manage and control incoming network traffic.
6. **Docker:** Provides the environment for running and managing application containers.
7. **WordPress:** Handles the website and its content.
8. **MariaDB:** Manages the website's database and stored information.
9. **Storage:** Docker volumes preserve application and database files even after containers are restarted.
10. **Backup Automation:** Bash scripts and Cron work together to generate scheduled database backups.

For a visual representation of the infrastructure, refer to [`architecture-diagram.png`](architecture-diagram.png).

## Technologies Used

| Component | Technology |
|---|---|
| Host Operating System | Windows 11 |
| Virtualization Software | Oracle VirtualBox |
| Server Operating System | Ubuntu Server 26.04.1 LTS |
| Container Platform | Docker Engine 29.9.2 |
| Container Management | Docker Compose 5.6.1 |
| Website | WordPress |
| Database | MariaDB 11.4 |
| Firewall | UFW and iptables |
| Automation | Bash and Cron |
| Remote Access | OpenSSH |
| SSH Authentication | ED25519 Key |

## Network Configuration

The following table presents the network settings used in the project.

| Interface | IP Address | Purpose |
|---|---|---|
| NAT (`enp0s3`) | `10.0.2.15/24` | Provides internet connectivity |
| Host-only (`enp0s8`) | `192.168.56.103/24` | Connects the laptop and virtual server |
| Windows Host-only Adapter | `192.168.56.1` | Allows the laptop to communicate with the server |
| WordPress | `192.168.56.103:8080` | Provides access to the website |

**WordPress Website Address:**

`http://192.168.56.103:8080`

## Docker Services

The project uses two Docker containers that communicate with each other to operate the website.

| Container | Image | Function |
|---|---|---|
| `cloudnova-wordpress` | `wordpress:latest` | Hosts and runs the website |
| `cloudnova-database` | `mariadb:11.4` | Handles website data and database operations |

Both services are connected through a Docker network called `cloudnova-network`, allowing them to exchange information.

**Persistent Storage:**

- `wordpress_data` – stores WordPress application files and related information.
- `mariadb_data` – maintains the MariaDB database files.

The MariaDB port is kept private and is not directly published to the host network.

## Security Features

Several security configurations were implemented to improve the protection of the CloudNova server:

- Enabled UFW with a default policy that denies incoming connections.
- Permitted outgoing network traffic.
- Limited SSH connections to the Host-only network.
- Disabled SSH password-based authentication.
- Prevented direct root login through SSH.
- Configured SSH public-key authentication for remote connections.
- Applied Docker firewall rules to limit access to the WordPress website.
- Restricted MariaDB communication to the internal Docker network.
- Stored database credentials in a protected `.env` file instead of publishing them in the GitHub repository.

## Backup Automation

To protect important website information, CloudNova includes an automated MariaDB backup solution developed using Bash.

**Script File:** `automation-script.sh`

**Backup Directory:** `/opt/cloudnova/backups/`

**Backup Schedule:** Daily at 2:00 AM UTC (10:00 AM Philippine Time).

The backup script is designed to perform the following operations:

- Generate a backup copy of the MariaDB database.
- Compress the generated backup using Gzip.
- Include the date and time in the backup filename.
- Validate the generated backup file.
- Automatically remove backup files that are more than seven days old.
- Save backup activity and results in a log file.

## GitHub Repository Structure

The project files are organized as follows:

```text
Laboratory-10-Enterprise-Cloud-Architect/
├── README.md
├── architecture-diagram.png
├── docker-compose.yml
├── automation-script.sh
├── operational-manual.md
└── final-reflection.md
```

## Basic Deployment Commands

Follow these commands to manage the CloudNova application.

**1. Open the project directory:**

```bash
cd /opt/cloudnova
```

**2. Launch the application containers:**

```bash
sudo docker compose up -d
```

**3. Verify the running containers:**

```bash
sudo docker ps
```

**4. Check the application logs:**

```bash
sudo docker compose logs
```

**5. Access the WordPress website:**

```text
http://192.168.56.103:8080
```

For more detailed information about installation, deployment, security configurations, backup procedures, and maintenance, read the [`operational-manual.md`](operational-manual.md) file.

## Project Deliverables

The repository contains the following project outputs:

- `architecture-diagram.png` – illustrates the overall infrastructure and network design.
- `docker-compose.yml` – contains the configuration for deploying WordPress and MariaDB.
- `automation-script.sh` – contains the Bash commands used for automated database backups.
- `operational-manual.md` – provides instructions for deploying, securing, and maintaining the infrastructure.
- `final-reflection.md` – presents the knowledge, experiences, and lessons gained throughout the CCM101 missions.

## Conclusion

The CloudNova project shows how virtualization, containerization, networking, storage, security, and automation can be combined to create a functional cloud-based application environment.

By integrating WordPress with MariaDB, the project provides a working website with persistent data storage, controlled network access, and scheduled database backups. It also demonstrates the practical skills developed throughout the CCM101 Cloud Computing activities.
