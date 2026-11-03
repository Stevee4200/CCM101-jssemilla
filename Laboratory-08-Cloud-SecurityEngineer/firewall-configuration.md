# Firewall Configuration

## 1. Allow SSH Connections

**Command:**

```bash
sudo ufw allow ssh
```

**Explanation:**

This command allows incoming SSH connections through port 22. It ensures that administrators can remotely access and manage the server.

## 2. Configure the Default Deny Policy

**Command 1:**

```bash
sudo ufw default deny incoming
```

**Explanation:**

This blocks all incoming network connections by default unless they are specifically allowed by a firewall rule.

**Command 2:**

```bash
sudo ufw default allow outgoing
```

**Explanation:**

This allows outgoing network connections so the server can communicate with other systems and access external services.

## 3. Enable the Firewall

**Command:**

```bash
sudo ufw enable
```

**Explanation:**

This activates the UFW firewall and applies the configured security rules to incoming and outgoing network traffic.

## 4. Allow Web Traffic on Port 8080

**Command:**

```bash
sudo ufw allow 8080/tcp
```

**Explanation:**

This allows incoming TCP connections through port 8080 so users can access the Nginx web application.

## 5. Verify Firewall Rules

**Command:**

```bash
sudo ufw status verbose
```

This displays the firewall status and default policies.

**Command:**

```bash
sudo ufw status numbered
```

This displays the firewall rules with numbers, making them easier to identify and manage.

## 6. Test the Web Application

**Command:**

```bash
curl http://localhost:8080
```

This tests whether the Nginx web server responds successfully to a local HTTP request.

## 7. Importance of Allowing SSH Before Enabling UFW

If I run `sudo ufw enable` before `sudo ufw allow ssh`, the firewall may block incoming SSH connections, preventing administrators from remotely accessing and managing the server.

## Conclusion

Configuring UFW helped me understand how to secure a cloud server using firewall rules. By allowing only necessary connections, blocking incoming traffic by default, and permitting web traffic on port 8080, I learned how to improve server security while maintaining access to the web application.
