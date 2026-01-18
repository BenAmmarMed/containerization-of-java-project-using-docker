# 🚀 Containerization of a Java Enterprise Application (DevOps Project)

This repository showcases a **real-world DevOps containerization project** where a **multi-service Java enterprise application** has been fully dockerized and orchestrated using **Docker and Docker Compose**.

> 🔹 This project is a **fork** of the original application  
> **vprofile-project** by **hkhcoder**  
> 🔹 All DevOps and Docker work has been implemented by **Ben Ammar** in the **`containers` branch**

---

## 🎯 Project Objective

The primary objective of this project is to demonstrate **hands-on DevOps skills** by:

- Transforming a traditional Java application into a **containerized architecture**
- Ensuring **service isolation, scalability, and consistency**
- Applying **Docker best practices** used in production environments
- Delivering a **reproducible and portable deployment**

---

## 🧠 DevOps Approach

Before containerization, the application was **built and tested locally** to:

- Analyze application dependencies
- Identify required backend services
- Validate version compatibility
- Prevent runtime and configuration issues
- Select optimal Docker base images

This mirrors **real DevOps workflows** used in enterprise environments.

---

## 🏗 Application Stack

| Layer | Technology |
|-----|-----------|
| **Frontend** | Nginx |
| **Application** | Java 21 / Tomcat 10 |
| **Database** | MySQL 8.0.33 |
| **Cache** | Memcached |
| **Message Broker** | RabbitMQ |
| **Build Tool** | Maven 3.9.9 |
| **Containerization** | Docker |
| **Orchestration** | Docker Compose |

---

## 🐳 Containerization & Automation (My Work)

Implemented entirely by **Ben Ammar**:

- ✅ Dockerfiles for each service (App, DB, Web)
- ✅ **Multi-stage Docker builds** for optimized Java images
- ✅ Centralized orchestration with `docker-compose.yml`
- ✅ Persistent volumes for data integrity
- ✅ Clean separation of concerns between services
- ✅ Environment parity with on-prem / cloud deployments

---

## 🏛 Architecture Overview

| Service | Image | Ports | Purpose |
|-------|------|------|--------|
| **vprodb** | mohamedbenammar/vprofiledb | 3306 | MySQL database |
| **vprocache01** | memcached:latest | 11211 | In-memory cache |
| **vpromq01** | rabbitmq:latest | 5672 | Message broker |
| **vproapp** | mohamedbenammar/vprofileapp | 8080 | Java application |
| **vproweb** | mohamedbenammar/vprofileweb | 80 | Nginx reverse proxy |

---

## ⚡ Quick Start (Production-Like Deployment)

```bash
docker-compose up -d --build

## ⚡ Verify running containers:
        docker ps

🌐 Service Access

        Application URL
        http://localhost/

        Tomcat Backend
        http://localhost:8080

        MySQL Database
        localhost:3306

🔄 Lifecycle Management

Stop and clean the environment:

        docker-compose down -v
        docker system prune -af

⭐ Key DevOps Highlights

        End-to-end containerization of a legacy Java application
        Docker multi-stage builds for performance optimization
        Reverse proxy implementation with Nginx
        Stateful services managed with Docker volumes
        Production-ready Docker Compose architecture
        Infrastructure stability and resource optimization

📈 DevOps Skills Demonstrated

        Docker & Docker Compose
        Java / Maven / Tomcat
        Nginx reverse proxy
        MySQL / Memcached / RabbitMQ
        Multi-container orchestration
        Infrastructure automation
        DevOps best practices

👤 Author & DevOps Engineer

Ben Ammar Mohamed
DevOps Engineer | Docker | Kubernetes | Cloud Enthusiast

        This project is part of my DevOps portfolio and demonstrates my ability to design, containerize, and manage production-ready systems.
