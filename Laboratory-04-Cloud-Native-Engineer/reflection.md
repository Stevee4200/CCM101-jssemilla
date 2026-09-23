
---

# Checkpoint 7 — `reflection.md`

Your instructor requires **250–350 words**, so I made this around **300 words** and kept the English simple and natural.

```markdown
# Mission Reflection

## 1. How does the boot time and setup process of a Docker container compare to installing an operating system on a Virtual Machine?

A Docker container is much faster to start compared with installing and booting a complete operating system on a Virtual Machine. A VM needs to allocate hardware resources and load an entire guest operating system before the application can run. Docker containers share the host operating system kernel, so they only need the application and its required files. In this activity, I was able to download the Nginx image and start the web server using only a few commands.

## 2. Why is port mapping (-p 8080:80) necessary when running a web server inside a container?

Port mapping allows users outside the container to access a service running inside it. In my activity, `-p 8080:80` connected port 8080 on the host machine to port 80 inside the Nginx container. Without this mapping, the Nginx web server would not be directly accessible through the host's port 8080.

## 3. What happens to the data inside a container when you use the docker rm command?

The `docker rm` command removes the container and its writable container filesystem. Any data stored only inside the container can be lost when the container is removed. This shows why persistent data should normally be stored using Docker volumes or other external storage.

## 4. How do you think containerization changes the way software developers and IT operations teams work together (DevOps)?

Containerization can make cooperation between developers and IT operations easier because applications can be packaged with their required dependencies. Developers can test the same container environment that operations teams deploy. This helps reduce differences between development and production environments and can make application deployment more consistent and efficient.

## 5. How is your GitHub portfolio evolving?

My GitHub portfolio is becoming more organized and practical as I add more laboratory projects. This Docker activity shows that I can use Linux, Docker commands, containers, and Markdown documentation. By continuing to add projects and technical documentation, my GitHub portfolio can demonstrate the skills I am developing in cloud computing and IT.
