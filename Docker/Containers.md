# Docker Containers:

Containers are runtime instances of Docker images. Simply put, when you run an image, it becomes a container. Let's understand some fundamental aspects and commands associated with Docker containers.

## Running Containers from Images:

To run a container from an image:

```bash
docker run [image_name]
```

**Example:**
Running the official `nginx` image.

```bash
docker run -d nginx
```

`-d` ensures the container runs in the background.

## Mapping Ports:

Often, we need the container's service to be accessible on a specific port of the host machine.

**Syntax:**

```bash
docker run -p [host_port]:[container_port] [image_name]
```

**Example:**
Map nginx running inside the container on port 80 to be accessible on port 8080 of your host machine.

```bash
docker run -d -p 8080:80 nginx
```

## Mounting Volumes:

Volumes are essential for persistent storage or sharing data between the host and container.

1. **Bind Mounts:**

-   Link a specific location on your host to the container.
    **Syntax:**

    ```bash
    docker run -v [host_path]:[container_path] [image_name]
    ```

    **Example:**
    Share a directory from your host machine (`/host/data`) to the container (`/container/data`).

    ```bash
    docker run -v /host/data:/container/data nginx
    ```

2. **Volume Mounts:**

-   Use Docker-managed volumes for data persistence.
    **Creation:**

    ```bash
    docker volume create [volume_name]
    ```

    **Usage:**

    ```bash
    docker run -v [volume_name]:[container_path] [image_name]
    ```

## Environment Variables and Secrets:

1. **Environment Variables:**
   These allow configuration options to be passed to the container during runtime.

**Syntax:**

```bash
docker run -e [VAR_NAME]=[VALUE] [image_name]
```

**Example:**
Starting a container with an environment variable named `MY_ENV` with the value `HelloWorld`.

```bash
docker run -e MY_ENV=HelloWorld nginx
```

2. **Secrets (mostly applicable in Docker Swarm mode):**
   Docker secrets provide a safe way to store sensitive information, such as passwords or API keys, required by the container.

**Creation:**

```bash
echo "my_secret_data" | docker secret create [secret_name] -
```

**Usage:**
In Docker Swarm mode, when deploying services:

```bash
docker service create --name [service_name] --secret [secret_name]
[image_name]
```

### [Previous Topic: Images](/Docker/Images.md)

### [Previous Topic: Docker-Compose](/Docker/Docker-Compose.md)
