# Docker Compose Guide

## What Does the `services:` Block Do?

The `services:` block defines the containers that make up the application. In this activity, it defines two services: `database`, which uses the MariaDB image, and `app`, which uses the Nextcloud image. Docker Compose reads these definitions to deploy and manage the application stack.

## How Does Nextcloud Find the Database?

The Nextcloud service uses the environment variable `MYSQL_HOST=database`. The name `database` matches the database service defined in the Compose file. Docker Compose provides service-name-based networking, allowing the Nextcloud container to locate the MariaDB container by that name on their shared network.

## Docker Run vs. Docker Compose Up

The `docker run` command is useful for starting an individual container with options supplied directly in the command. The `docker-compose up -d` command reads the `docker-compose.yml` configuration and starts the services defined in it. The `-d` option runs the containers in the background, allowing the terminal to be used for other tasks.

## Commands Used

- `docker --version` — checks the Docker version.
- `docker-compose --version` — checks the Compose version.
- `mkdir nextcloud-deployment` — creates the project directory.
- `nano docker-compose.yml` — creates or edits the Compose file.
- `docker-compose up -d` — starts the application stack.
- `docker-compose ps` — checks the service containers.
- `docker-compose logs` — displays service logs.
- `docker-compose down` — stops and removes the stack's containers and default network.
