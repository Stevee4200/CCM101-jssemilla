# Mission Reflection Laboratory 7

In this laboratory activity, I learned the importance of monitoring a server and checking its performance before handling a large amount of website traffic. I used Linux commands such as `free -h`, `df -h /`, and `top` to check the server's memory, disk storage, CPU usage, and running processes. These commands helped me understand the current condition of the server and why monitoring is important.

I learned that checking the host server's resources is necessary even when containers are running properly. If the server has insufficient memory, limited disk space, or high CPU usage, the application may become slow or stop working. Monitoring these resources helps cloud engineers identify possible problems before they affect users.

I also learned how the `docker logs` command helps troubleshoot application problems. It allows engineers to review requests and errors recorded by a container. For example, an HTTP 404 error means that the requested page could not be found. By checking the logs, an engineer can investigate what happened instead of guessing the cause of the problem.

Another lesson I learned is the difference between logs and metrics. Logs provide details about events and requests, while metrics show numerical measurements such as CPU usage, memory consumption, and network activity. Both are useful because they help engineers understand application behavior and system performance.

Large companies can monitor thousands of containers using monitoring tools such as Prometheus and Grafana. These tools help collect, display, and analyze performance information from different systems, making it easier to identify problems.

Overall, this laboratory improved my Linux troubleshooting and monitoring skills. I became more familiar with checking system resources and understanding how Docker tools help maintain applications. I realized that cloud computing is not only about deploying applications but also about monitoring and maintaining them so they remain reliable and available to users.
