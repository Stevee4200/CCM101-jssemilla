# Two-Tier Architecture

## The Web/Application Tier

The web/application tier runs the Nextcloud application. It provides the user interface, handles HTTP requests, and allows users to access their files through a web browser. In this activity, Nextcloud runs inside a Docker container.

## The Database Tier

The database tier uses MariaDB to store application information, such as user account details and file metadata. Nextcloud communicates with the database to save and retrieve the information it needs.

## Why Separate Them?

Separating the web application and database into two containers makes the system easier to manage and troubleshoot. Each container has its own responsibility, and the services can be configured or updated separately. Docker Compose helps manage both containers as one application stack.
