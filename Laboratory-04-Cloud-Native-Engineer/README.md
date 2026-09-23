
## Mission Overview

This laboratory activity focused on learning the basic concepts of containerization using Docker. I used the KillerCoda Docker Playground to verify the Docker environment, deploy an Nginx web server, test the container, and practice managing its lifecycle.

Through these activities, I learned how containers can provide a faster and more lightweight way to run applications compared with traditional virtual machines.

---

## Objectives

The objectives of this laboratory activity are:

- Verify that Docker is installed and running.
- Learn how to download Docker images from Docker Hub.
- Deploy an Nginx web server using a Docker container.
- Understand port mapping between the host and container.
- Test a containerized web server using the `curl` command.
- Practice the basic Docker container lifecycle.
- Stop, verify, and remove Docker containers.
- Document Docker activities using Markdown and GitHub.

---

## Docker Commands Executed

### Checkpoint 3 - Enter the Docker Playground

#### Check Docker Version

```bash
docker --version
```
This command checks whether Docker is installed and displays its version.

**Check Docker environment:**

```bash
docker info
```

This command displays detailed information about the Docker environment.

**List running containers:**

```bash
docker ps
```

This command displays the containers that are currently running.

### Checkpoint 4 – Deploy Nginx

**Pull the Nginx image:**

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub.

**Run the Nginx container:**

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command runs the Nginx container in detached mode and maps port 8080 on the host to port 80 inside the container.

**Test the Nginx web server:**

```bash
curl http://localhost:8080
```

This command sends an HTTP request to the Nginx server and displays the HTML response in the terminal.

### Checkpoint 5 – Container Lifecycle

**List running containers:**

```bash
docker ps
```

This command lists the containers that are currently running.

**Stop the Nginx container:**

```bash
docker stop nginx-server
```

This command stops the running Nginx container.

**Verify the container is stopped:**

```bash
docker ps
```

This command verifies that the Nginx container is no longer running.

**List all containers:**

```bash
docker ps -a
```

This command displays all containers, including stopped containers.

**Remove the container:**

```bash
docker rm nginx-server
```

This command removes the stopped Nginx container completely.
