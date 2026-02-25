# Docker Image Assignment - README

## Overview
In this assignment, i created a custom Docker image by writing a simple Node.js 
application (`index.js`) and a `Dockerfile`. 
and then built and tested different versions of the image while exploring Docker commands.

## What Happened

### 1. Creating and Modifying a Container
- Started an Ubuntu container using:  
  `docker container run -ti ubuntu bash`
- Inspected changes inside a container using:  
  `docker container diff <container-id>`
- Saved container changes as a new image using:  
  `docker container commit <container-id>`

### 2. Tagging and Running the Custom Image
- Tagged the new image:  
  `docker image tag <image-id> ourfiglet`
- Ran the custom image using:  
  `docker container run ourfiglet figlet hello`

### 3. Creating a Node.js Application
- Created a simple `index.js` file that prints a message.
- Created a `Dockerfile` to build a custom image.

### 4. Understanding the Dockerfile
The Dockerfile performs the following steps:

1. **FROM** – Pulls a base image (Alpine).
2. **RUN** – Installs Node.js using `apk update` and `apk add`.
3. **COPY** – Copies `index.js` into the container.
4. **WORKDIR** – Sets the working directory.
5. **CMD** – Defines the command to run when the container starts.

### 5. Building and Running the Custom Image
- Built the image:  
  `docker image build -t hello:v0.1 .`
- Ran the container:  
  `docker container run hello:v0.1`

### 6. Updating the App and Image
- Modified `index.js` to create version 0.2.
- Built a new image:  
  `docker image build -t hello:v0.2 .`

### 7. Inspecting Image Layers
- Pulled Alpine and viewed image layers using:  
  `docker image inspect`  
  `docker image inspect --format "{{ json .RootFS.Layers }}" alpine`

## Summary
I learned how to:
- Start containers and inspect changes
- Commit container changes into images
- Build custom images using Dockerfiles
- Tag and run custom images
- Inspect image layers and understand how Docker builds images

This process shows how Docker enables consistent, repeatable builds and easy sharing 
of containerized applications.

## Follow this CMD
# Docker Commands Practice - README

## Overview
This README summarizes the basic Docker and Linux commands practiced during the session. 
These commands help I understand how to run containers, pull images, explore containers,
and execute commands inside them.

---

## Commands Used

### 1. Check System Information
- `uname -a`  
  Displays system and kernel information.

---

## Working With Images

### 2. Download an Image
- `docker image pull alpine`  
  Downloads the **Alpine Linux** image from Docker Hub.

### 3. List Images
- `docker image ls`  
  Shows all images stored on my system.

### 4. Run a Simple Test Image
- `docker container run hello-world`  
  Runs the *hello-world* image (pulls it if not available).

---

## Running Containers

### 5. Run Commands Inside a Container
- `docker container run alpine ls -l`  
  Runs `ls -l` inside an Alpine container.

- `docker container run alpine echo "hello from alpine"`  
  Prints text from inside a container.

### 6. Start an Interactive Shell
- `docker container run alpine /bin/sh`  
  Opens a shell inside Alpine.

- `docker container run -it alpine /bin/sh`  
  Starts an interactive terminal session.

- `docker container run -it alpine /bin/ash`  
  Starts Alpine's `ash` shell interactively.

---

## Managing Containers

### 7. List Running and Stopped Containers
- `docker container ls`  
  Shows running containers.

- `docker container ls -a`  
  Shows all containers (running + stopped).

### 8. Start an Existing Container
- `docker container start <container-id>`  
  Starts a previously stopped container.

### 9. Execute Commands Inside a Running Container
- `docker container exec <container-id> ls`  
  Runs `ls` inside a running container.

---

## Summary
These commands help I learn how to:
- Pull and list Docker images  
- Run containers and execute commands inside them  
- Use interactive shells  
- Start and inspect existing containers  

This is a foundational step toward understanding Docker workflows and containerization.

---

# End of README