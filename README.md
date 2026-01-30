🐳 Docker MySQL + Adminer Lab
📌 Project Overview

This project demonstrates how to deploy a multi-container application using Docker Compose.

It includes:

🗄️ MySQL – Database server

🌐 Adminer – Web-based database management tool

💾 Docker Volume – Persistent storage

🔗 Docker Network – Communication between containers

This setup simulates a real-world application architecture used in DevOps and cloud environments.

🏗 Architecture
Browser (User)
      │
      ▼
Adminer Container (Web App)
      │
      ▼
MySQL Container (Database)
      │
      ▼
Docker Volume (Persistent Storage)

⚙️ Docker Compose File
version: "3"

services:
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: testdb
    volumes:
      - dbdata:/var/lib/mysql

  adminer:
    image: adminer
    ports:
      - "8081:8080"

volumes:
  dbdata:

🚀 How to Run
docker compose up -d


Check containers:

docker ps

🌍 Access Adminer

Open in browser:

http://localhost:8081


Login:

Field	Value
System	MySQL
Server	db
Username	root
Password	root123
Database	testdb
🔐 Networking & Security Concept

Adminer is exposed to host (port 8081)

MySQL is internal only (not exposed)

Containers communicate via Docker network using service name (db)

Architecture principle:

User → Application → Database

📚 Concepts Learned

Docker containers & images

Docker Compose (Infrastructure as Code)

Multi-container communication

Volume-based persistent storage

Port mapping (host ↔ container)

Basic application architecture

🎯 Outcome

Built a local multi-tier application stack similar to real production environments used in DevOps and cloud deployments.
