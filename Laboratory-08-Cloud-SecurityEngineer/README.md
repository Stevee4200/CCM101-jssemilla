# Laboratory 08 – Cloud Security Engineer

## Mission Overview

In this laboratory, I performed basic cloud server security configuration using Ubuntu, Docker, Nginx, and UFW (Uncomplicated Firewall). I deployed a simple Nginx web application inside a Docker container and configured firewall rules to control incoming and outgoing network traffic.

## Objectives

- Deploy an Nginx web server using Docker.
- Create and run a container named `secure-web-app`.
- Configure UFW to protect the Ubuntu server.
- Allow SSH connections through port 22.
- Apply the Default Deny policy for incoming traffic.
- Allow TCP traffic through port 8080.
- Verify firewall rules and test the web application using curl.
- Document the security configuration and laboratory activities.

## Commands Executed

### 1. Deploy the Nginx Container

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

### 2. Check Running Containers

```bash
docker ps
```

### 3. Test the Web Application

```bash
curl http://localhost:8080
```

### 4. Allow SSH Connections

```bash
sudo ufw allow ssh
```

### 5. Configure Default Firewall Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

### 6. Enable UFW

```bash
sudo ufw enable
```

### 7. Allow Web Traffic

```bash
sudo ufw allow 8080/tcp
```

### 8. Verify Firewall Configuration

```bash
sudo ufw status verbose
sudo ufw status numbered
```

## Skills Learned

- **Docker Containerization:** Learned how to deploy and manage an Nginx web server using Docker.
- **Linux Administration:** Practiced using Ubuntu terminal commands to configure and manage a server.
- **Firewall Configuration:** Learned how to use UFW to control incoming and outgoing network traffic.
- **SSH Security:** Understood the importance of allowing SSH before activating a firewall.
- **Port Management:** Learned how to allow specific ports while blocking unauthorized connections.
- **Network Testing:** Used curl to check whether the web application was responding successfully.
- **Technical Documentation:** Practiced documenting commands, configurations, and security procedures.

## Conclusion

Through this laboratory, I gained practical experience in deploying a web application and securing a Linux server using firewall rules. I learned that proper firewall configuration, restricted access, and careful port management are important practices for protecting cloud infrastructure.
