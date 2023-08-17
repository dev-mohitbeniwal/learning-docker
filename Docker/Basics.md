# Docker Basics

## What is Docker?

Docker is a tool that lets us create, deploy, and run applications inside containers. Think of it like a box that holds everything an app needs to run.

## Why Docker?

-   **Consistency:** With Docker, apps run the same no matter where you put them.
-   **Isolation:** Apps don't interfere with each other because they're in separate containers.
-   **Development Speed:** Makes it easy for developers to build, test, and deploy apps quickly.
-   **Efficiency:** Uses less space and resources compared to running full VMs.

## Docker Architecture

![Docker Architecture](/Assets/Architecture-of-Docker.png)
Docker uses a client-server model:

-   **Docker Client:** This is what we use to tell Docker what to do, like building or running containers.
-   **Docker Daemon:** This runs on the host machine and does the heavy lifting of building, running, and managing containers.
-   **Docker Images/Containers:**
    -   **Image:** A blueprint for a container. It's like a template.
    -   **Container:** A running instance of an image. It's the live application.

## Docker Hub and Docker Registries

-   **Docker Hub:** It's like a library for Docker images. We can pull images from it or push our images to it.
-   **Docker Registries:** Places where Docker images are stored. Docker Hub is a public registry, but there are also private registries for company-specific images.

## Important Links

-   ### [Installing Docker](/Docker/Installation.md)

### [Previous Topic: Installation](/Docker/Installation.md)

### [Previous Topic: Commands](/Docker/Commands.md)
