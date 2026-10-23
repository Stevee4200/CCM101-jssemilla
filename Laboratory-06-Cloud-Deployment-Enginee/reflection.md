# Mission 6 Reflection: The Cloud Deployment Engineer

This laboratory activity helped me understand how Docker Compose makes cloud deployment easier and more organized. Before this activity, I understood Docker mainly as a tool for running individual containers. Through this mission, I learned that a cloud application can use multiple containers that work together, such as Nextcloud for the web application and MariaDB for the database.

Writing a `docker-compose.yml` file makes an engineer's job easier because the configuration for the services is written in one place. Instead of manually starting each container and entering many options, an engineer can use one command to deploy the application. This approach also makes the setup easier to understand, repeat, and maintain.

I also learned that YAML indentation is very important. If I accidentally use a Tab or incorrect spacing, Docker Compose may not understand the configuration properly. This can cause an error and prevent the application from starting. Checking the indentation and reading error messages are important troubleshooting skills.

Environment variables, such as `MYSQL_PASSWORD` and `MYSQL_DATABASE`, allow the containers to use the required database settings. The `MYSQL_HOST=database` setting tells Nextcloud which database service to connect to. However, I learned that passwords should be protected carefully in real deployments instead of using simple example credentials.

Deploying Nextcloud was a valuable learning experience because it showed me how different services can work together in a short time. It also helped me become more confident in using Linux commands, editing configuration files, and checking whether containers are running.

Since Mission 1, my understanding of cloud computing has grown. I now see that cloud computing involves more than storing files online. It also involves configuring infrastructure, connecting services, managing applications, and solving technical problems. This mission helped me develop practical skills that I can use in future cloud computing activities and IT projects.
