# Orchestration Assignment – README

## Overview
This assignment demonstrates how to use Docker Swarm Mode to orchestrate multi-service applications across multiple nodes. I will initialize a Swarm, join nodes, deploy a stack using a Compose file, scale services, and manage node availability.

---

## Node 1 – Swarm Initialization & Stack Deployment

### 1. Initialize Docker Swarm
```
docker swarm init --advertise-addr $(hostname -i)
```

### 2. Display Join Tokens
```
docker swarm join-token manager
docker swarm join-token worker
```

### 3. List Nodes
```
docker node ls
```

### 4. Clone the Example Voting App
```
git clone https://github.com/docker/example-voting-app
cd example-voting-app
cat docker-stack.yml
```

### 5. Deploy the Application Stack
```
docker stack deploy --compose-file=docker-stack.yml voting_stack
```

### 6. Check Stack & Services
```
docker stack ls
docker stack services voting_stack
docker service ps voting_stack_vote
```

### 7. Scale the Voting Service
```
docker service scale voting_stack_vote=5
```

---

## Node 2 – Join Swarm

### 1. Join the Swarm as a Worker
```
docker swarm join --token <worker-token> <manager-ip>:2377
```

### 2. Verify the Node Status
```
docker node ls
```

---

## What I Achieved
- Formed a Docker Swarm cluster with manager and worker nodes  
- Deployed an entire multi-service application stack using a single command  
- Scaled services easily  
- Used the Compose file (`docker-stack.yml`) for orchestration  
- Demonstrated Swarm’s automatic container scheduling  

---

## Conclusion
This assignment showed how Docker Swarm Mode turns multiple machines into a self-managing container cluster. With a few simple commands, I deployed, scaled, and managed a full application stack.

Swarm Mode provides:
- Simple cluster setup  
- Automated container scheduling  
- Easy scaling  
- Zero‑downtime rescheduling  
- Unified configuration using a Compose file  

---

# End of README