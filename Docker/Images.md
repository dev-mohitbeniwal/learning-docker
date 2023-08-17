# Docker Images:

Understanding Docker Images and Layers:
Docker images are lightweight, standalone, executable software packages that encompass all essentials required to run a piece of software, such as the code, runtime, system libraries, and system tools. Think of them as blueprints for containers.

-   **Layers:** Every modification or instruction creates a new layer in the image. Layers are stacked on top of each other and share common files, making images lightweight and fast.

    > **Example:** If you have an image with Ubuntu installed and then decide to install nginx, the nginx installation forms a new layer on top of the base Ubuntu layer.

## Building Docker Images Using Dockerfiles:

A Dockerfile is a text document containing instructions to automate the process of creating a Docker image.

Dockerfile Structure, Syntax, and Best Practices:

1. **Structure:**

-   Each instruction in a Dockerfile creates a new layer for the Docker image.
-   Instructions are processed from top to bottom.

2. **Key Instructions:**

-   **FROM:** Initializes a new build stage and sets the base image.

    ```Dockerfile
    FROM ubuntu:18.04
    ```

-   **RUN:** Executes command(s) in a new layer and creates a new image. E.g., installing software.

    ```Dockerfile
    RUN apt-get update && apt-get install -y nginx
    ```

-   **CMD:** Provides defaults for executing container. There can only be one CMD.

    ```Dockerfile
    CMD ["nginx", "-g", "daemon off;"]
    ```

-   **COPY:** Copies files from source to the destination container's filesystem.

    ```Dockerfile
    COPY ./example.html /var/www/html/
    ```

## Best Practices:

-   **Minimize Layers:** Combine commands in one RUN instruction to reduce image size.
-   **Use .dockerignore:** Exclude files not relevant to the build (like `.git`, `README.md`).
-   **Avoid Cache Busting:** Changing a Dockerfile instruction can invalidate cached layers for all subsequent instructions. Place frequently changed instructions at the bottom of your Dockerfile.

## Building an Image: docker build:

To transform your Dockerfile into a usable image, you utilize the docker build command.

### Example:

If your Dockerfile is in the current directory:

```bash
docker build -t custom_nginx:latest .
```

Here:

-   `-t` tags the image with a name (custom_nginx) and tag (latest).
-   `.` indicates the context (current directory).

## Pushing and Pulling Images from Docker Hub or Private Repositories:

1. **Pulling an Image:**

-   You can fetch an image from a repository like Docker Hub.

    ```bash
    docker pull nginx:latest
    ```

2. **Pushing an Image:**
   Before pushing, you need to log in to Docker Hub or your private registry.

    ```bash
    docker login
    ```

    Once logged in, tag your custom image with your DockerHub username:

    ```bash
    docker tag custom_nginx:latest [username]/custom_nginx:latest
    ```

    Then, push your image:

    ```bash
    docker push [username]/custom_nginx:latest
    ```

### [Previous Topic: Commands](/Docker/Commands.md)

### [Previous Topic: Containers](/Docker/Containers.md)
