# Docker Compose:

## Why Docker Compose?

-   **Simplification:** Easily manage and orchestrate multi-container Docker applications. Instead of running multiple Docker commands for each container, a single docker-compose command can manage the whole stack.
-   **Reproducibility:** Define and share your application's services, networks, and volumes in a single file, ensuring consistent environments.
-   **Easy Scaling:** Quickly scale services up or down based on requirements.

## `docker-compose.yml` File Structure and Syntax:

The `docker-compose.yml` file is where you define your application's services, networks, and volumes. Here's a basic breakdown:

1. **Version:**

-   Specifies the Docker Compose version.

```yml
version: "3"
```

2. **Services:**

-   Define the containers you want to run.

```yml
services:
web:
image: nginx:latest
ports: - "8080:80"
database:
image: postgres:latest
environment:
POSTGRES_DB: mydatabase
POSTGRES_USER: user
POSTGRES_PASSWORD: secret
```

3. **Networks (optional):**

-   Specify custom networks.

```yml
networks:
mynetwork:
driver: bridge
```

4. **Volumes (optional):**

-   Declare volumes for persistent storage.

```yml
volumes:
mydata:
driver: local
```

## Basic docker-compose Commands:

1. **Start Services:**

This command starts up all the services defined in docker-compose.yml.

```bash
docker-compose up
```

-   For detached mode (running in the background):

```bash
docker-compose up -d
```

2. **Stop Services:**

-   Stop and remove all services.

```bash
docker-compose down
```

To also remove volumes defined in the docker-compose.yml:

```bash
docker-compose down -v
```

3. **Build Services:**

-   If you have a custom Dockerfile for a service, you can build it using:

```bash
docker-compose build
```

4. **Logs:**

-   View logs from services.

```bash
docker-compose logs
```

5. Scale Services (For Compose file format v2 only):

-   Scale a specific service up or down.

```bash
docker-compose up -d --scale service_name=3
```

### [Previous Topic: Containers]()
