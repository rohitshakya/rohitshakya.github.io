---
layout: project
title:  "Microservices Backend"
bannerDescription: "Scalable backend microservices powering high-traffic classified marketplace for OLX Indonesia."
techUsed: Java, Spring Boot, Kotlin, Microservices, Kafka, Redis, MySQL, MongoDB, AWS, Docker, Kubernetes, ELK
githubRepo: rohitshakya
comments: true
date: 2022-01-10
priority: 1
---

# OLX Indonesia – Backend Microservices

At OLX Indonesia, I worked on building and scaling **high-performance microservices** that power one of the largest online marketplaces in Southeast Asia.  
The platform handles millions of daily users, real-time listings, chats, notifications, payments, and search traffic — requiring highly scalable, resilient, and low-latency backend systems.

I contributed to core backend services, system re-architecture, and performance optimization across multiple domains of the OLX Indonesia ecosystem.

---

## Description

My primary responsibilities included:

- Re-architecting existing monolith components into **microservices**  
- Building and maintaining **critical customer-facing services**  
- Improving **system performance, resilience, & scalability**  
- Optimizing API latency, DB queries, caching layers  
- Strengthening the observability stack (logs, metrics, traces)  
- Designing new end-to-end workflows for product & operations teams  
- Ensuring high availability during peak traffic events  

The services were designed to handle **millions of concurrent requests**, and were deployed across a fully containerized and monitored infrastructure.

---

## Key Projects & Capabilities Delivered

### **1. Ad Listings Service**
- High-throughput service powering all product listings  
- Query optimization & pagination improvements  
- Caching with Redis to reduce DB load by 40%  
- Improved SLA for listing creation & updates  

---

### **2. Chat & Conversation Service**
- Real-time chat service used by millions of buyers/sellers  
- Kafka-based asynchronous message processing  
- Delivery status, read receipts, user presence  
- Latency optimizations for mobile low-network zones  

---

### **3. User Profile & Authentication**
- Secure session handling with JWT  
- Rate limiting & fraud detection workflows  
- Profile metadata service with fast lookups  
- Multi-device sync + session refresh improvements  

---

### **4. Notifications Microservice**
- Push notifications (FCM + in-app)  
- Event-driven architecture with Kafka  
- Delivery analytics + retry mechanism  
- Reduced notification lag from seconds → milliseconds  

---

### **5. Payments & Transaction Workflows**
- Integrated multiple payment partners  
- Wallet, COD, prepaid flows  
- Reconciliation microservice  
- Strong validation + idempotent APIs  

---

## Technology Stack

- **Backend Languages:** Java, Kotlin  
- **Framework:** Spring Boot, Micronaut (optional)  
- **Databases:** MySQL (transactional), MongoDB (documents)  
- **Caching:** Redis, Hazelcast (optional)  
- **Messaging:** Kafka for async workflows & event streams  
- **Infra:** Docker, Kubernetes, Helm  
- **Cloud:** AWS (EC2, EKS, S3, SNS/SQS, CloudWatch)  
- **Monitoring:** Grafana, Prometheus, ELK Stack  
- **Other:**  
  - Circuit breakers (Resilience4j)  
  - Centralized config service  
  - API Gateway + rate limiting  
  - Canary deployments & blue/green releases  

---

## Setting Up the Project (Generic Microservice Template)

```bash
git clone https://github.com/rohitshakya
cd olx-microservice/
./gradlew build
