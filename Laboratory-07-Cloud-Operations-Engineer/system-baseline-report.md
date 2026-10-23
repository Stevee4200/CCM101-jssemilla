# System Baseline Report

## 1. RAM Usage

The server has 1.9 GiB of total RAM. At the time of checking, 493.4 MiB was used and approximately 1.4 GiB was available. The `free -h` command was used to check memory usage in a human-readable format.

## 2. Disk Storage

The root filesystem (`/`) has a total capacity of 19 GB. Approximately 8.3 GB was used, and 11 GB was available. Disk utilization was 46%, according to the `df -h /` command.

## 3. CPU and Running Processes

The `top` command showed that CPU usage was low, with 0.3% user usage, 0.3% system usage, and 99.4% idle time. The load averages were 0.00 for the 1-minute, 5-minute, and 15-minute periods. There were 136 tasks, with one running.

## 4. Why Is Monitoring Important?

Monitoring RAM, disk storage, and CPU helps cloud engineers understand the server's condition before deploying applications or generating additional traffic. These baseline measurements can be compared with later results to identify resource changes and potential performance problems.
