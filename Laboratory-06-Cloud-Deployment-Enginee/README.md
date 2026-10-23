# Laboratory 06: Cloud Deployment Engineer

## Mission Overview

This laboratory activity demonstrates how to deploy a private cloud storage application using Nextcloud, MariaDB, Docker, and Docker Compose. The application uses a two-tier architecture with a web/application service and a database service.

## Objectives

- Explain the roles of the web/application and database tiers.
- Create a Docker Compose YAML configuration.
- Deploy and verify a multi-container application.
- Access the Nextcloud web interface through port 8080.
- Document the deployment process and Infrastructure as Code principles.

## Commands Executed

```bash
docker --version
docker-compose --version
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
docker-compose up -d
docker-compose ps
docker-compose logs
docker-compose down
```

## Skills Learned

- Understanding two-tier architecture.
- Writing and checking YAML configuration files.
- Using Docker Compose to manage multiple containers.
- Troubleshooting container deployment issues.
- Documenting technical work using Markdown.
- Maintaining a cloud computing portfolio on GitHub.


