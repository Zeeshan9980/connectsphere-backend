# 🚀 ConnectSphere — Distributed Social Platform Backend

## 📄 Project Summary

**ConnectSphere** is a distributed backend system designed for high-performance social networking platforms similar to **LinkedIn** or **Twitter**.  
This system has been developed as a **scalable enterprise-grade solution** to demonstrate advanced microservice communication, event-driven architecture, and containerized deployment.

The project delivers a **robust, fault-tolerant, and modular backend** capable of supporting millions of users concurrently through efficient use of **Kafka**, **Redis**, and **Spring Cloud** infrastructure.

---

## 🎯 Objectives

- To architect and develop a **distributed microservices-based backend** for a professional networking application.  
- To ensure **horizontal scalability**, **fault tolerance**, and **real-time event propagation**.  
- To demonstrate a production-grade setup using **Docker** and **Kubernetes**.
- 
[ Client Applications ]
│
▼
[ API Gateway ]
│
▼
[ Discovery Server (Eureka) ]
│
┌───────────────────────────────────────────┐
│ │
│ User Service → Manage users, auth │
│ Post Service → Handle posts, feed │
│ Connection Service→ Manage follows │
│ Notification Service → Real-time alerts │
│ │
└───────────────────────────────────────────┘
│
▼
[ Kafka Message Bus ]
│
▼
[ Redis / MySQL / Containerized Environment ]


---

## 🧱 Microservices Overview

| Service | Responsibility | Key Features |
|----------|----------------|---------------|
| **User Service** | Manages user profiles, registration, authentication | CRUD operations, profile updates |
| **Connection Service** | Handles user connections (follow/unfollow) | Network building |
| **Post Service** | Manages post creation, likes, and comments | News feed management |
| **Notification Service** | Publishes & consumes Kafka events | Real-time notifications |
| **Discovery Server** | Service registry for all microservices | Dynamic routing |
| **API Gateway** | Entry point for client requests | Routing, filtering, load balancing |

---

## 🧠 Technology Stack

| Category | Tools & Frameworks |
|-----------|--------------------|
| **Language** | Java 21 |
| **Frameworks** | Spring Boot, Spring Cloud |
| **Database** | MySQL |
| **Messaging** | Apache Kafka |
| **Caching** | Redis |
| **Service Discovery** | Netflix Eureka |
| **API Gateway** | Spring Cloud Gateway |
| **Containerization** | Docker, Docker Compose |
| **Orchestration** | Kubernetes |
| **Build Tool** | Maven |

---

## ⚙️ Installation & Setup Guide

### 1️⃣ Clone Repository
```bash
git clone https://github.com/<your-username>/connectsphere-backend.git
cd connectsphere-backend
2️⃣ Build Services
mvn clean install -DskipTests

3️⃣ Start Application (Docker)
docker-compose -f docker-compose.base.yml up -d


For Kafka-based notifications:

docker-compose -f docker-compose.notification-kafka.yml up -d

4️⃣ Access Services
Service	URL
Eureka Discovery	http://localhost:8761

API Gateway	http://localhost:8080

User Service	http://localhost:8081

Post Service	http://localhost:8082
🔐 Security & Best Practices

Secured with JWT authentication (planned for next release)

Each service uses isolated DB schema for data separation

Communication between services via REST + Kafka Events

Containerized environment for reproducibility

🧾 Deployment Strategy
Environment	Tool
Development	Docker Compose
Staging / Production	Kubernetes (K8s)
CI/CD	GitHub Actions (optional pipeline setup)
📊 Monitoring & Logging

Centralized logging using Spring Boot Actuator

Health checks exposed via /actuator/health

Future integration with Prometheus + Grafana

📈 Business Impact

This architecture allows organizations to:

Scale horizontally under high traffic loads

Extend services independently

Integrate new features rapidly (e.g., chat, analytics)

Reduce downtime via container orchestration
