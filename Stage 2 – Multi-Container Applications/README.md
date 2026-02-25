# Multi-container Assignment - README

## Overview

In this assignment, I set up a multi-node Docker Swarm cluster,
deployed a sample voting application, and managed services using Swarm
Mode. I used the swarm manager (Node 1) and a worker/manager join
operation (Node 2) to form the cluster.

## Node 1 (Manager Node)

### 1. Initialize Docker Swarm

    docker swarm init --advertise-addr $(hostname -i)

### 2. View Join Tokens

    docker swarm join-token manager
    docker swarm join-token worker

### 3. View Nodes in the Swarm

    docker node ls

### 4. Clone the Example Voting App

    git clone https://github.com/docker/example-voting-app
    cd example-voting-app

### 5. Review the Stack File

    cat docker-stack.yml

### 6. Deploy the Stack

    docker stack deploy --compose-file=docker-stack.yml voting_stack

### 7. Manage the Stack

    docker stack ls
    docker stack services voting_stack
    docker service ps voting_stack_vote

### 8. Scale a Service

    docker service scale voting_stack_vote=5

## Node 2 (Joining Another Node to the Swarm)

### 1. Join the Swarm

    docker swarm join --token <token> <manager-ip>:2377

### 2. Validate Node Membership

    docker node ls

## Conclusion

With only a few commands, I deployed a fully functional service stack
using Docker Swarm Mode. Swarm Mode allows orchestration of multiple
services through a simple Docker Compose file and automatically manages
scaling and distribution across nodes.

---

# End of README