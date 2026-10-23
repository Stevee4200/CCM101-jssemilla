# Laboratory 07: Cloud Operations Engineer

## Mission Overview

This activity focuses on monitoring a Linux server and observing the performance of a containerized Nginx web server.

## Objectives

- Monitor RAM, disk storage, CPU, and running processes.
- Deploy an Nginx container.
- Generate HTTP requests, including a request that returns 404.
- Inspect application logs.
- Monitor CPU and memory usage with Docker.

## Monitoring Commands Executed

- `free -h` — check RAM.
- `df -h /` — check root filesystem storage.
- `top` — observe CPU and processes.
- `docker run -d --name client-website -p 8080:80 nginx` — deploy Nginx.
- `curl http://localhost:8080` — generate successful HTTP requests.
- `curl http://localhost:8080/hidden-admin-page` — generate a missing-page request.
- `docker logs client-website` — inspect application logs.
- `docker stats` — observe container metrics.

## Skills Learned

- Linux system monitoring.
- Container deployment.
- HTTP request testing.
- Application log analysis.
- Docker resource monitoring.
- Technical documentation using Markdown.
