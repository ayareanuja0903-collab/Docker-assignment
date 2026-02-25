# Networking Assignment

When containers scale, Swarm creates:
- Multiple running tasks
- A single virtual IP  
- Built-in load balancing

Requests reach any replica through VIP, not directly to containers.

---

# 1. Key Networking Behaviors Observed

### ✔ Bridge Network
- Works only on same host  
- Supports DNS name resolution  
- Supports container-to-container ping  

### ✔ Overlay Network
- Works across multiple nodes  
- Enables cross-host container communication  
- Requires Swarm mode  
- DNS + encrypted VXLAN tunnels  

### ✔ Port Mapping
- Host ↔ Container access  
- Example: `8080:80` exposes NGINX service

### ✔ Service Discovery
- Containers resolve each other by **service name**  
- Example: `ping voting_stack_vote`

### ✔ Load Balancing
- VIP mode balances traffic  
- No manual configuration needed

---

# 2. Conclusion

Using only a few essential commands, I successfully:

- Initialized a full **Docker Swarm**
- Joined multiple nodes into the cluster
- Created **bridge** and **overlay** networks
- Launched containers across nodes
- Verified cross-node communication
- Deployed a full application stack using Docker Swarm
- Scaled services dynamically
- Observed Docker's built-in **DNS, VIP load balancing, and orchestration**

This demonstrates the powerful orchestration features built into **Docker Swarm Mode**, enabling easy deployment, scaling, and distributed networking of containerized microservices.

---

# End of README