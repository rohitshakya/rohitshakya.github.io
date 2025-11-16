---
layout: project
title:  "Product Catalog Service"
bannerDescription: "High-performance product catalog microservice powering listings, search, and metadata for large-scale marketplaces."
techUsed: Spring Boot, Kotlin, Microservices, Redis, PostgreSQL, Kafka, Docker, Kubernetes
githubRepo: rohitshakya
comments: true
date: 2022-06-01
priority: 3
---

# Product Catalog Service – High-Performance Listings Backend

The **Product Catalog Service** powers the creation, storage, search, and retrieval of millions of marketplace listings.  
It is designed as a **low-latency, horizontally scalable microservice** optimized for high-read workloads typical in e-commerce and classifieds platforms.

I worked on designing, building, and optimizing this system for production-scale usage, ensuring fast listing fetches, real-time updates, and efficient search performance.

---

## Description

The catalog service manages the **complete lifecycle of product listings**, including:

- Creating & updating listings  
- Category & attribute management  
- Search indexing & synchronization  
- Enrichment (pricing, images, metadata, badges)  
- Real-time availability status  
- SEO-friendly content generation  
- Integrations with recommendations, ads, and user services  

The service handles **millions of read requests per minute**, especially during peak traffic.

---

## Key Capabilities Delivered

### **1. Listing Creation & Update API**
- CRUD APIs with strong validation  
- Optimized database writes with batching  
- Category-specific schema & dynamic attributes  
- Idempotent operations  

---

### **2. High-Performance Read APIs**
- Ultra-fast listing fetch (<20ms)  
- Redis caching layer reducing DB load by 60–70%  
- Category-level & homepage caching  
- Cache invalidation on listing update  

---

### **3. Search & Indexing Pipeline**
- Elasticsearch integration for full-text search  
- Real-time sync using Kafka event streams  
- Re-indexing workflows for schema changes  
- Faceted search (filters, sort, pagination)  
- Geo-based queries for local discovery  

---

### **4. Media & Metadata Integration**
- Seamless integration with image/video services  
- Auto-thumbnail mapping  
- Badging engine (Featured, Verified, Urgent)  
- SEO keyword generation  

---

### **5. Performance & Resilience Enhancements**
- Read/write separation with MySQL replicas  
- Circuit breakers & rate limiting  
- Async enrichment pipeline  
- Blue/green deployments  
- Observability: metrics, logs, traces  

---

## Impact

- Reduced API latency from **90ms → 18ms** through caching & query optimization  
- Increased catalog throughput by **3×** via read-write splitting  
- Faster search indexing with **<1 sec sync** using Kafka  
- Improved homepage load speed by **30%**  
- Delivered a highly stable and scalable system able to handle **millions of daily active users**  

---

## Technology Stack

- **Backend:** Java, Kotlin, Spring Boot  
- **Database:** MySQL (primary + replicas), Elasticsearch  
- **Caching:** Redis (hot data, listings, homepage)  
- **Messaging:** Kafka for real-time sync  
- **Infra:** Docker, Kubernetes, Helm  
- **Search:** Elasticsearch, Kibana  
- **Monitoring:** Prometheus, Grafana, ELK  
- **Other:**  
  - Resilience4j  
  - Centralized config service  
  - Nginx API gateway  
  - OpenAPI/Swagger  

---

## Setting Up (Generic Template)

```bash
git clone https://github.com/rohitshakya
cd product-catalog-service/
./gradlew build
