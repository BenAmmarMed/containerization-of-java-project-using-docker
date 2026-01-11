Containerization of Java Project Using Docker

Containerization of Java Project Using Docker is a fork of vprofile-project
 by hkhcoder.
I have forked the original project and switched to the branch containers where I implemented full Dockerization of the application, including:

Dockerfiles for each service (App, DB, Web)

Multi-stage Java build

Docker Compose  for MySQL, Memcached, RabbitMQ, Tomcat, and Nginx

This README focuses on my containerization work, highlighting my DevOps and Docker skills.

🔧 Original Application & Containerization Work

Before containerizing, the original application was built and validated locally to:

Identify required services

Validate compatible versions

Select accurate Docker base images

Avoid runtime and dependency conflicts

✅ Validated Local Stack (from original project)
Component	Version
Database	MySQL 8.0.33
Cache Service	Memcached 1.6
Message Broker	RabbitMQ 4.0
Java Development Kit	JDK 21
Build Tool	Maven 3.9.9
Application Server	Tomcat 10 (JDK 21)
Web Server	Nginx 1.27
🐳 Dockerization Work (by Me, Ben Ammar)

Built Dockerfiles for all services: App, DB, and Nginx reverse proxy

Implemented multi-stage Java build to optimize image size

Created docker-compose.yml to orchestrate all services

Configured persistent volumes for MySQL and Tomcat

Ensured environment parity with original project

🏗 Project Architecture
Service	Image / Build	Ports	Description
vprodb	mohamedbenammar/vprofiledb	3306:3306	MySQL database initialized with dump
vprocache01	memcached:latest	11211:11211	In-memory caching service
vpromq01	rabbitmq:latest	5672:5672	Message broker for asynchronous tasks
vproapp	mohamedbenammar/vprofileapp	8080:8080	Java application deployed on Tomcat
vproweb	mohamedbenammar/vprofileweb	80:80	Nginx reverse proxy exposing the application
⚡ Running the Containerized Project
docker-compose up -d --build
docker ps


Access the application:

Browser: http://<server-IP>/

Tomcat backend: http://<server-IP>:8080

MySQL: localhost:3306 (via SQL client)

🔧 Cleanup & Maintenance
docker-compose down -v
docker system prune -af


For small instances (EC2 <2GB RAM), add swap:

sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

💡 Key Highlights (My Work)

Dockerization and orchestration of multi-service Java application

Multi-stage build for Java and optimized Docker images

Nginx reverse proxy setup

Persistent volumes for database and web apps

Resource optimization and stability

📈 Skills Demonstrated

Docker & Docker Compose

Java / Maven / Tomcat

MySQL / Memcached / RabbitMQ

Nginx configuration

Multi-container orchestration and DevOps best practices
