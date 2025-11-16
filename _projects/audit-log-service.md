---
layout: project
title:  "Event Logging System"
bannerDescription: "Scalable, traceable, tamper-proof audit logging system for microservices."
techUsed: Java, Spring Boot, Kafka, ClickHouse, Elasticsearch, Redis, S3, Microservices, AWS
githubRepo: rohitshakya
comments: true
date: 2025-11-01
priority: 2
---

# Audit Log Service – Distributed Event Logging System

The **Audit Log Service** captures, stores, indexes, and retrieves all critical events happening across a distributed microservices architecture.  
It provides **complete traceability**, **non-repudiation**, and **high-performance event search**, essential for debugging, compliance, security, and analytics.

Designed for large-scale platforms, the system handles **millions of audit events per day** with strict guarantees around sequencing, immutability, and reliability.

---

## Description

The service records every meaningful action performed across the platform:

- User actions (login, profile updates, payments, chats)  
- Admin actions (moderation, edits, approvals)  
- System events (workflows, auto-assignments, notifications)  
- Data changes (CRUD events, mutations, side-effects)  

Each event is enriched with metadata (IP, device ID, source app, timestamp, user ID, trace ID) and stored in a **tamper-proof, append-only architecture**.

The system supports:

- Real-time streaming of logs  
- Efficient querying & filtering  
- High-performance writes  
- Secure retention and archival  
- Cross-service traceability for debugging  

---

## Key Capabilities Delivered

### **1. Logging SDK (Client Library)**
- Lightweight SDK for all microservices  
- Auto-capture: trace ID, span ID, user ID, timestamp  
- Non-blocking async logging  
- Batch + retry logic  
- Kafka producer wrapper with idempotence  

---

### **2. Ingestion Pipeline (Kafka → Processor)**
- Kafka topics segregated by domain (auth, payments, chat…)  
- Horizontal consumers for high throughput  
- Enrichment layer (geo-ip, device metadata, correlation ID)  
- DLQs for poison messages  
- Fault-tolerant retries  

---

### **3. Storage Layer**
- **ClickHouse** for high-speed analytical queries  
- **Elasticsearch** for full-text search  
- **S3** for cold storage and long-term archival  
- Partitioned by date, domain, service name  

This ensures **high-write, low-cost, and query-optimized** architecture.

---

### **4. Query Service (Read APIs)**
- Filter logs by:  
  - userId, service, action, time range, event type  
- Paginated search with ES & CH hybrid strategy  
- Sub-second responses for large time ranges  
- Structured and unstructured event retrieval  
- Secure access with RBAC  

---

### **5. Compliance & Security**
- Immutable append-only design  
- Hash-chained log entries (optional)  
- Access logs for every read operation  
- GDPR retention policies via lifecycle rules  
- PII masking before storage (optional)  

---

## Impact

- Enabled **100% traceability** of user & system actions across dozens of microservices  
- Reduced debugging time during incidents by **60–70%**  
- High-throughput pipeline handling **5M+ events/day**  
- Sub-second search & filtering for operations teams  
- Delivered audit trails required for **internal compliance & security audits**  
- Highly scalable, cost-efficient log storage with tiered architecture  

---

## Technology Stack

- **Backend:** Java, Spring Boot, Kotlin  
- **Log Pipeline:** Kafka, Kafka Streams (optional), SQS  
- **Databases:** ClickHouse, Elasticsearch, MySQL (metadata)  
- **Caching:** Redis  
- **Storage:** AWS S3  
- **Infra:** Docker, Kubernetes, Nginx  
- **Monitoring:** Prometheus, Grafana, Jaeger  
- **Other:**  
  - CDC (Debezium) for DB change capture  
  - OpenTelemetry tracing  
  - RBAC authorization layer  
  - DLQs for resilience  

---

## High-Level Architecture

**Microservices → SDK → Kafka → Log Processor → ClickHouse/Elasticsearch → Query APIs → Dashboard**

---

## Setting Up (Generic Template)

```bash
git clone https://github.com/rohitshakya
cd audit-log-service/
./gradlew build
