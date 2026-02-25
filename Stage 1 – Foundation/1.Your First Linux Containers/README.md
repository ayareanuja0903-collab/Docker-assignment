# Docker Linux Containers

## 1. Docker Images
Docker images are read-only templates containing the filesystem and configuration needed to run an application.  
Example:  
- `docker image pull alpine` downloads the Alpine image.  
- `docker image inspect alpine` shows image details.

## 2. Docker Containers
Containers are running instances of Docker images. They include the application and all its dependencies, sharing the host OS kernel but running in isolation.  
Example:  
- `docker container run alpine ls`  
- `docker container ls` lists running containers.

## 3. Docker Daemon
The Docker daemon is the background service that manages building, running, and distributing containers. It handles all low-level container operations.

## 4. Docker Client
The Docker client is the command-line tool used to interact with the Docker daemon. Commands such as `docker run`, `docker pull`, and `docker ps` are executed through the client.

## 5. Docker Hub
Docker Hub is an online registry that stores Docker images. Pulling images like `alpine` or `hello-world` downloads them from Docker Hub.

---

# End of README