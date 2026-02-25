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
- Pull and list Docker images  
- Run containers and execute commands inside them  
- Use interactive shells  
- Start and inspect existing containers  

This is a foundational step toward understanding Docker workflows and containerization.
This assignment summarizes the basic Docker and Linux commands practiced during the session. 
These commands help I understand how to run containers, pull images, explore containers,
and execute commands inside them.

This process shows how Docker enables consistent, repeatable builds and easy sharing 
of containerized applications.

---

# End of README