# Docker CLI Commands

## Objective:

Set up an nginx web server, inspect it, manage it, and clean up.

## Basic Commands

### 1. Docker Version

Displays the installed Docker version.

```bash
docker --version
```

### 2. Docker System Information:

Offers a comprehensive view of your Docker installation.

```bash
docker info
```

### 3. Docker Help:

Showcases all Docker commands and usage instructions.

```bash
docker help
```

## Lifecycle Commands

### 1. Run a Container:

Initiates an nginx web server.

```bash
docker run -d -p 8080:80 --name web_server nginx
```

### 2. Start a Container:

Starts your container if it's stopped.

```bash
docker start web_server
```

### 3. Stop a Container:

Halts the nginx container.

```bash
docker stop web_server
```

### 4. Restart a Container:

Refreshes the container if you've adjusted configurations.

```bash
docker restart web_server
```

### 5. Remove a Container:

Deletes the container.

```bash
docker rm web_server
```

## Image Commands:

### 1. Remove an Image:

Deletes the nginx image from your local machine.

```bash
docker rmi nginx
```

### 2. Pull an Image:

Explicitly download the nginx image.

```bash
docker pull nginx
```

### 3. Push an Image:

(Note: This requires you to have a Docker Hub account and a custom image you want to push.)

Share your custom image on Docker Hub.

```bash
docker tag nginx:latest [username]/[image_name]:[tag]
docker push [username]/[image_name]:[tag]
```

## Container Inspection:

### 1. List Containers:

Shows all active containers.

```bash
docker ps
```

### 2. View Container Logs:

Display the logs of your nginx server.

```bash
docker logs web_server
```

### 3. Container Statistics:

Monitor the container's resource consumption.

```bash
docker stats web_server
```

### 4. Inspect Container Details:

Obtain detailed information about your container.

```bash
docker inspect web_server
```

## Network and Volume-Related Commands:

### 1. List Networks:

View all Docker-defined networks.

```bash
docker network ls
```

### 2. List Volumes:

Shows all created persistent storage volumes. (Note: We didn't set up a volume for nginx in this POC, but this is how you'd list them.)

```bash
docker volume ls
```

## Cleanup:

### 1. Prune Unused Resources:

-   Removes stopped containers, networks not used by at least one container, dangling images, build cache.

    ```bash
    docker system prune
    ```

-   To additionally remove any volumes not associated with a container:

    ```bash
    docker system prune --volumes
    ```

### [Previous Topic: Basics](/Docker/Basics.md)

### [Previous Topic: Images](/Docker/Images.md)
