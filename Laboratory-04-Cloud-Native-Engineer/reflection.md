Mission Reflection

During this Docker laboratory, I learned that containers can make application deployment much faster and easier compared to using a Virtual Machine. When using a VM, we usually need to install an operating system first and wait for it to boot before we can install and run an application. With Docker, we can simply download an image and start a container in a few seconds. I experienced this myself when I deployed the Nginx web server using only a few commands.

I also learned why port mapping is important. The command -p 8080:80 connects port 8080 on the host machine to port 80 inside the container. This allows me to access the Nginx web server from the host using localhost:8080. Without port mapping, it would be difficult for the host to communicate directly with the web server inside the container.

Another thing I learned is what happens when a container is removed using docker rm. The container and the data stored only inside its writable layer are removed. This made me realize that important data should be stored using volumes or another form of persistent storage if it needs to remain available after removing a container.

I also think containerization can improve the way developers and IT operations teams work together. Developers can create an application inside a container with its required dependencies, and the same container can be used for testing and deployment. This can reduce problems caused by differences between development and production environments and make teamwork more organized.

Lastly, my GitHub portfolio is slowly improving as I add more laboratory activities and technical projects. Before, my GitHub mainly contained school files, but now I am adding projects involving Linux, cloud computing, Docker, and technical documentation. I believe these projects can help show the skills I am learning as an IT student and give me a better portfolio for future opportunities.
