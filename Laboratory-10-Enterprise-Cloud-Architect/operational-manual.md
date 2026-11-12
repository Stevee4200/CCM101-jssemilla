# CloudNova – Operational Manual

## 1. Introduction

This operational manual provides instructions for installing, deploying, protecting, and maintaining the CloudNova infrastructure.

CloudNova is a web hosting environment built using Ubuntu Server running inside Oracle VirtualBox. It uses Docker to manage WordPress and MariaDB as its main application services.

This document serves as a guide for managing the server, operating the website, configuring security, monitoring services, and performing regular database backups.

## 2. System Requirements

Before deploying CloudNova, the following hardware and software components are needed.

### 2.1 Host Machine

- Windows 11 operating system
- Oracle VirtualBox
- SSH client
- Web browser
- Working internet connection

### 2.2 Virtual Machine

- Ubuntu Server 26.04.1 LTS
- 35 GB dynamically allocated virtual disk
- Docker Engine
- Docker Compose
- UFW Firewall
- OpenSSH Server

### 2.3 Application Components

- WordPress for website hosting
- MariaDB 11.4 for database management
- Docker network for container communication
- Docker storage volumes for persistent data

## 3. Server and Network Setup

### 3.1 Virtual Machine Information

CloudNova uses an Ubuntu Server virtual machine created and managed through Oracle VirtualBox.

| Configuration | Value |
|---|---|
| Server Name | `cloudnova-server` |
| Linux User | `cloudnova` |
| Operating System | Ubuntu Server 26.04.1 LTS |
| Virtualization Software | Oracle VirtualBox |
| Virtual Disk | 35 GB |

### 3.2 Network Configuration

The virtual server uses two network interfaces to provide internet access and communication with the Windows host machine.

| Interface | IP Address | Purpose |
|---|---|---|
| `enp0s3` | `10.0.2.15` | Internet connectivity |
| `enp0s8` | `192.168.56.103` | Communication between laptop and server |

The Windows laptop uses `192.168.56.1` as its Host-only network address.

### 3.3 Connecting to the Server

To remotely access Ubuntu Server, open Windows PowerShell and execute:

```powershell
ssh -i "$env:USERPROFILE\.ssh\cloudnova_ed25519" cloudnova@192.168.56.103
```

If requested, enter the passphrase associated with your SSH private key.

Once connected, you can manage the server through the terminal.

To access the WordPress website, open a browser and visit:

```text
http://192.168.56.103:8080
```

## 4. Running the Docker Application

### 4.1 Verifying Docker Installation

Before managing the application, check whether Docker is properly installed.

Check the Docker Engine version:

```bash
sudo docker --version
```

Check the Docker Compose version:

```bash
sudo docker compose version
```

### 4.2 Project Directory

The CloudNova application files are maintained in the following directory:

```text
/opt/cloudnova/
```

The configuration file used on the Ubuntu server is called `compose.yaml`, while the version stored in the GitHub repository is named `docker-compose.yml`.

### 4.3 Application Containers

The application consists of two main Docker containers.

**WordPress Container**

- Container name: `cloudnova-wordpress`
- Docker image: `wordpress:latest`
- Website address: `192.168.56.103:8080`
- Persistent storage: `wordpress_data`

**MariaDB Container**

- Container name: `cloudnova-database`
- Docker image: `mariadb:11.4`
- Database configuration: Stored in `.env`
- Persistent storage: `mariadb_data`
- Network access: Internal Docker network only

### 4.4 Deploying the Application

Connect to Ubuntu Server and navigate to the CloudNova directory:

```bash
cd /opt/cloudnova
```

Start the WordPress and MariaDB services in the background:

```bash
sudo docker compose up -d
```

Verify that the containers are running:

```bash
sudo docker ps
```

To view the status of the application services, use:

```bash
sudo docker compose ps
```

### 4.5 Stopping and Restarting Services

Use the following commands when you need to manage the application.

**Stop the application:**

```bash
cd /opt/cloudnova
sudo docker compose stop
```

**Start the stopped services:**

```bash
sudo docker compose start
```

**Restart the application containers:**

```bash
sudo docker compose restart
```

**Remove the containers and Docker network while keeping persistent data:**

```bash
sudo docker compose down
```

**Important:** Do not use `docker compose down -v` unless you intend to remove the associated Docker volumes and their stored data.

### 4.6 Monitoring Application Logs

Logs can help identify errors and check whether the application services are working properly.

View WordPress logs:

```bash
sudo docker logs cloudnova-wordpress
```

View MariaDB logs:

```bash
sudo docker logs cloudnova-database
```

To monitor the logs of both services continuously:

```bash
sudo docker compose logs -f
```

## 5. Data Storage

CloudNova uses Docker volumes to maintain important application and database files. These volumes allow stored information to remain available even if containers are stopped or recreated.

| Volume | Storage Location | Purpose |
|---|---|---|
| `wordpress_data` | `/var/www/html` | Maintains WordPress application files |
| `mariadb_data` | `/var/lib/mysql` | Preserves MariaDB database information |

To display the available Docker volumes:

```bash
sudo docker volume ls
```

To examine the MariaDB storage volume:

```bash
sudo docker volume inspect mariadb_data
```

Using persistent volumes helps protect data during container restarts and recreation. However, separate backups are still necessary to provide additional protection against data loss.

## 6. Security Configuration

Security settings are applied to control access to the server, protect application services, and prevent unauthorized connections.

### 6.1 UFW Firewall Configuration

UFW is configured to block incoming connections by default while allowing outgoing network communication.

Apply the default firewall policies:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

Allow SSH connections only from the Host-only network:

```bash
sudo ufw allow from 192.168.56.0/24 to any port 22 proto tcp
```

Enable the firewall:

```bash
sudo ufw enable
```

Check the current firewall configuration:

```bash
sudo ufw status verbose
```

WordPress access is managed separately through Docker firewall rules because Docker-published ports may bypass the normal UFW filtering process.

### 6.2 SSH Security Configuration

To improve remote access protection, the server uses SSH key authentication instead of password-based login.

The following settings are applied:

```text
PermitRootLogin no
PubkeyAuthentication yes
PasswordAuthentication no
KbdInteractiveAuthentication no
MaxAuthTries 3
X11Forwarding no
AllowUsers cloudnova
```

The SSH security configuration is saved in:

```text
/etc/ssh/sshd_config.d/99-security.conf
```

To verify that the SSH configuration contains no syntax errors:

```bash
sudo sshd -t
```

To display the active SSH settings:

```bash
sudo sshd -T
```

After modifying the configuration, reload the SSH service:

```bash
sudo systemctl reload ssh
```

**Important:** Do not close your existing SSH connection immediately after changing the settings. Keep it open while testing another connection to ensure that the new configuration works and that you do not lose access to the server.

### 6.3 Docker Firewall Rules

Docker firewall rules provide additional control over connections reaching the WordPress application.

The CloudNova firewall configuration is designed to:

1. Allow previously established connections to continue.
2. Permit the Windows host (`192.168.56.1`) to access WordPress through the Host-only network interface.
3. Block other traffic attempting to access the published WordPress port.

To inspect the Docker firewall rules:

```bash
sudo iptables -S DOCKER-USER
```

The firewall management script is located at:

```text
/usr/local/sbin/cloudnova-docker-firewall.sh
```

Its corresponding systemd service file is located at:

```text
/etc/systemd/system/cloudnova-docker-firewall.service
```

To check whether the firewall service is active:

```bash
sudo systemctl status cloudnova-docker-firewall
```

### 6.4 Database Password Protection

CloudNova keeps its database credentials in a separate environment configuration file.

The file is located at:

```text
/opt/cloudnova/.env
```

To examine its file permissions:

```bash
sudo ls -l /opt/cloudnova/.env
```

Follow these security practices when handling database credentials:

- Do not commit the `.env` file to GitHub.
- Avoid sharing database passwords with unauthorized individuals.
- Keep MariaDB port 3306 private and unpublished to the host network.
- Ensure that the environment file has appropriate file permissions.

WordPress communicates with MariaDB through the internal Docker network using the service name `database`.

## 7. Automatic Database Backup

CloudNova includes an automated backup system that uses a Bash script to protect important MariaDB information.

### 7.1 Backup Script

The main backup script is located on the Ubuntu Server at:

```text
/usr/local/sbin/cloudnova-db-backup.sh
```

The corresponding copy in the GitHub repository is named:

```text
automation-script.sh
```

The script is responsible for performing these operations:

1. Retrieves the database configuration from the `.env` file.
2. Verifies that the MariaDB container is running.
3. Generates a backup copy of the database.
4. Compresses the backup using Gzip.
5. Validates the generated backup archive.
6. Adds a date and time to the backup filename.
7. Removes backup files that are older than seven days.

### 7.2 Backup Storage Location

All generated database backups are saved in:

```text
/opt/cloudnova/backups/
```

To see the existing backup files and their sizes:

```bash
sudo ls -lh /opt/cloudnova/backups/
```

### 7.3 Performing a Manual Backup

You can execute the backup script manually whenever needed.

Run:

```bash
sudo /usr/local/sbin/cloudnova-db-backup.sh
```

When the backup completes successfully, the script displays a confirmation similar to:

```text
SUCCESS: Database backup created.
File: /opt/cloudnova/backups/...
Size: ...
```

### 7.4 Verifying Backup Files

It is important to check whether the generated backup archive is valid.

Execute:

```bash
sudo bash -c 'gzip -t "$(ls -t /opt/cloudnova/backups/*.sql.gz | head -n 1)" && echo "Backup archive is valid."'
```

If the command displays `Backup archive is valid.`, the compressed backup has passed the Gzip integrity test.

### 7.5 Configuring Automatic Backups

CloudNova is configured to perform database backups every day at 2:00 AM UTC, which is equivalent to 10:00 AM Philippine Time.

The schedule is managed through the root user's Cron configuration.

Open the Cron editor:

```bash
sudo crontab -e
```

Add the following schedule:

```cron
0 2 * * * /usr/local/sbin/cloudnova-db-backup.sh >> /var/log/cloudnova-backup.log 2>&1
```

This command automatically executes the backup script every day at the specified time and records its output in a log file.

### 7.6 Verifying the Cron Schedule

To display the configured scheduled tasks:

```bash
sudo crontab -l
```

To check whether the Cron service is running:

```bash
sudo systemctl status cron
```

### 7.7 Monitoring Backup Logs

The backup process records its activities in:

```text
/var/log/cloudnova-backup.log
```

To display the complete backup log:

```bash
sudo cat /var/log/cloudnova-backup.log
```

To view only the most recent 50 lines:

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

## 8. Restoring a Database Backup

CloudNova's compressed SQL backup files can be used to recover MariaDB information when needed.

**Warning:** Restoring a database may replace its existing contents. Always create a separate backup of the current database before proceeding.

First, navigate to the project directory:

```bash
cd /opt/cloudnova
```

Load the database environment variables:

```bash
set -a
source .env
set +a
```

Specify the backup file you want to restore:

```bash
BACKUP_FILE="/opt/cloudnova/backups/your_backup_filename.sql.gz"
```

Replace `your_backup_filename.sql.gz` with the actual name of your backup file.

Execute the database restoration command:

```bash
sudo bash -c 'gunzip -c "$1" | docker exec -i -e MYSQL_PWD="$2" cloudnova-database mariadb -u root "$3"' _ "$BACKUP_FILE" "$DB_ROOT_PASSWORD" "$DB_NAME"
```

After completing the restoration, examine the MariaDB logs:

```bash
sudo docker logs --tail 50 cloudnova-database
```

This helps identify any errors that may have occurred during the recovery process.

## 9. Maintenance and Troubleshooting

Regular server monitoring helps identify problems and maintain the availability of the CloudNova application.

The following commands can be used to examine different parts of the system.

### 9.1 Viewing Container Status

```bash
sudo docker ps -a
```

This displays all containers, including those that are stopped or have exited.

### 9.2 Restarting Docker

```bash
sudo systemctl restart docker
```

Use this command when the Docker service needs to be restarted.

### 9.3 Checking Available Disk Space

```bash
df -h
```

This displays the available storage capacity and disk usage.

### 9.4 Monitoring Memory Usage

```bash
free -h
```

This provides information about the server's total, used, and available memory.

### 9.5 Examining Network Configuration

```bash
ip addr
ip route
```

These commands display the network interfaces, assigned IP addresses, and routing information.

### 9.6 Inspecting Firewall Settings

```bash
sudo ufw status verbose
sudo iptables -S DOCKER-USER
```

Use these commands to review the UFW configuration and Docker firewall rules.

### 9.7 Checking the Docker Firewall Service

```bash
sudo systemctl status cloudnova-docker-firewall
```

This command shows whether the custom Docker firewall service is operating correctly.

### 9.8 Reviewing Backup Logs

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

Use this command to review recent backup activities and identify possible errors.

### 9.9 Common Problems and Solutions

| Problem | Possible Cause | Recommended Solution |
|---|---|---|
| WordPress website is inaccessible | Container is stopped or network connection is unavailable | Verify container status and network settings |
| WordPress cannot communicate with MariaDB | Database service is stopped or unhealthy | Examine MariaDB status and application logs |
| SSH connection is rejected | Incorrect private key or SSH configuration | Verify the SSH key and server settings |
| Backup script does not work | Database is unavailable or environment variables are incorrect | Check MariaDB status and `.env` configuration |
| Server storage is running out | Excessive files or accumulated backup archives | Review disk usage and remove unnecessary old files |
| Windows cannot access the website | Firewall restrictions or incorrect Host-only configuration | Examine Docker firewall rules and network interfaces |

## 10. Important Maintenance Reminders

To keep CloudNova secure and operating properly, follow these recommended practices:

- Keep database credentials confidential.
- Never publish the `.env` file in the GitHub repository.
- Maintain MariaDB access through the internal Docker network only.
- Understand firewall configurations before changing or disabling any rules.
- Regularly inspect database backup files.
- Maintain an additional copy of important backups outside the virtual machine.
- Check Docker volumes before attempting to remove them.
- Monitor available disk space to prevent storage problems.
- Review application updates before installing them.

## 11. Conclusion

This operational manual provides the necessary procedures for operating and maintaining the CloudNova infrastructure.

By following the instructions in this guide, the IT team can manage the application containers, maintain secure server access, monitor system resources, protect stored information, and perform database backups and recovery.

These procedures help support the availability, security, and reliability of the CloudNova website.
