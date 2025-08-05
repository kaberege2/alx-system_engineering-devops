# **0x09. Web Infrastructure Design**

## **Project Description**

This project involves designing and diagramming various web infrastructures that support real-world websites, starting from a simple one-server stack to a distributed, secured, and scalable infrastructure. Each design explains the roles of components like DNS, web servers, application servers, databases, load balancers, firewalls, SSL, and monitoring tools.

## **Learning Objectives**

At the end of this project, you will be able to:

- Draw and explain diagrams of web infrastructures.
- Describe the role of each infrastructure component.
- Understand system redundancy and high availability.
- Identify Single Points of Failure (SPOF) and how to mitigate them.
- Know the following acronyms: LAMP, SPOF, QPS.
- Understand the difference between web servers and application servers.
- Explain basic concepts of DNS, Load Balancers, Firewalls, HTTPS, and Monitoring.

## **Repository Structure**

```
0x09-web_infrastructure_design/
├── README.md
├── 0-simple_web_stack
├── 1-distributed_web_infrastructure
├── 2-secured_and_monitored_web_infrastructure
└── 3-scale_up
```

---

## **Infrastructure Tasks**

### **0. Simple Web Stack**

- **Diagram:** [Simple Web Stack Diagram](https://drive.google.com/file/d/1k94ec54tMfnu-byGe0bb9naCCGeRCtZc/view?usp=sharing)
- **Explanation:**

  - 1 Server hosting:

    - NGINX (Web Server)
    - Application Server (e.g., PHP-FPM)
    - MySQL Database

  - Domain name: [www.foobar.com](http://www.foobar.com) mapped via DNS A Record to IP 8.8.8.8.
  - Communication: HTTP over TCP/IP.
  - **Issues:**

    - SPOF at server.
    - Downtime during deployments.
    - Cannot handle high traffic (no scalability).

---

### **1. Distributed Web Infrastructure**

- **Diagram:** [Distributed Web Infrastructure Diagram](https://drive.google.com/file/d/1rRTp5loc6qDdrVVXksF3WFTbGhlr0bq6/view?usp=sharing)
- **Explanation:**

  - Added Load Balancer (HAProxy) to distribute traffic.
  - 2 Application Servers (Active-Active) for redundancy.
  - 1 Primary MySQL Database.
  - Load Balancer Algorithm: Round-Robin.
  - **Issues:**

    - SPOF at Load Balancer and Database.
    - Lacks HTTPS and Firewall.
    - No monitoring in place.

---

### **2. Secured and Monitored Web Infrastructure**

- **Diagram:** [Secured and Monitored Web Infrastructure Diagram](https://drive.google.com/file/d/1fDFnCoufhBiBNuZK6SAgt5sL6OEP_ONH/view?usp=sharing)
- **Explanation:**

  - Added Firewalls for all public-facing servers.
  - SSL Certificate to serve HTTPS traffic.
  - Monitoring Clients (e.g., Sumologic) collect logs and metrics.
  - SSL Termination is done at the Load Balancer level.
  - **Issues:**

    - Internal traffic after SSL termination is unencrypted.
    - SPOF at the database level (single Primary node).
    - App Servers still have Web & App layers tightly coupled.

---

### **3. Scale Up**

- **Diagram:** [Scale Up Infrastructure Diagram](https://drive.google.com/file/d/1QVUBVzmnHbqznAgH8AjzOzE3pN4fZj3x/view?usp=sharing)
- **Explanation:**

  - Added a second Load Balancer for clustering (HA setup).
  - Separated Web Servers and Application Servers for scalability.
  - Implemented a Primary-Replica DB Cluster for load distribution.
  - **Benefits:**

    - No SPOF at Load Balancer level.
    - Components (Web, App, DB) scale independently.
    - Enhanced redundancy and fault tolerance.

---

## **Key Concepts Covered**

| **Term**                           | **Explanation**                                                            |
| ---------------------------------- | -------------------------------------------------------------------------- |
| **LAMP Stack**                     | Linux, Apache/Nginx, MySQL, PHP/Python — classic web service stack.        |
| **SPOF (Single Point of Failure)** | A component whose failure leads to total system failure.                   |
| **QPS (Queries Per Second)**       | Metric indicating how many queries (requests) a system handles per second. |
| **DNS A Record**                   | Maps domain names to IPv4 addresses.                                       |
| **Load Balancer (HAProxy)**        | Distributes traffic to backend servers.                                    |
| **Web Server**                     | Handles HTTP requests, serves static files.                                |
| **Application Server**             | Processes application logic (dynamic content).                             |
| **Database (MySQL)**               | Stores persistent data.                                                    |
| **Firewall**                       | Filters incoming and outgoing network traffic.                             |
| **HTTPS (SSL/TLS)**                | Encrypts communication between clients and servers.                        |
| **Monitoring (Sumologic, etc.)**   | Tracks infrastructure health, performance metrics, and logs.               |
