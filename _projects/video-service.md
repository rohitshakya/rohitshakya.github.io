---
layout: project
title:  "Video Ads Feature"
bannerDescription: "End-to-end backend system enabling video uploads, processing, and delivery for OLX ad listings."
techUsed: Java, Kotlin, Spring Boot, Kafka, Redis, MySQL, AWS S3, CloudFront, Microservices
githubRepo: rohitshakya
comments: true
date: 2022-04-15
priority: 5
---

# OLX Indonesia – Video Ads Processing Pipeline

I designed and implemented the **video ads backend pipeline** that powers video uploads on OLX Indonesia’s marketplace listings.  
This system enables sellers to upload product videos, which significantly improves ad visibility, buyer engagement, and conversion rates across key categories like autos and electronics.

---

## Description

The Video Ads feature introduced rich media capabilities to OLX listings.  
I built the backend systems responsible for:

- Accepting user-uploaded videos  
- Validating video content  
- Processing (transcoding, compressing, thumbnail generation)  
- Storing variants securely  
- Making video streams available to buyers  
- Providing real-time upload & processing status to the app  

This required strong focus on performance, scalability, and low-latency delivery across Indonesia’s diverse network conditions.

---

## Key Capabilities Delivered

### **1. Video Ingestion Service**
- Upload APIs supporting mobile & web clients  
- Validation: file size, duration, codec, resolution  
- Secure pre-signed upload URLs  
- Temporary storage + checksum verification  

---

### **2. Video Processing Pipeline**
- Asynchronous processing with Kafka  
- FFmpeg-based transcoding into multiple resolutions  
- Thumbnail extraction + metadata generation  
- Retry logic, dead-letter queues, processing time monitoring  
- Idempotent workflows  

---

### **3. Content Delivery & Optimization**
- Multi-resolution outputs for adaptive streaming  
- Storage on AWS S3 with lifecycle rules  
- AWS CloudFront as global CDN for low latency  
- Optimized for low-bandwidth mobile networks  
- Signed URLs for private access  

---

### **4. Serving Layer APIs**
- Fetch video URL(s), metadata, and processing status  
- Seamless integration into Ad Listings service  
- Graceful fallback (thumbnail-first display)  
- Caching with Redis to reduce fetch latency  

---

## Impact

- Video processing time reduced from **~12 sec → ~4 sec**  
- Boosted user engagement & ad views by **15–20%**  
- Increased lead-to-conversion rate for high-value categories  
- Scalable pipeline processing **thousands of videos per hour**  
- Fully fault-tolerant workflow with high observability  

---

## Technology Stack

- **Backend:** Java, Kotlin, Spring Boot  
- **Data Stores:** MySQL, MongoDB (metadata)  
- **Cache:** Redis  
- **Queue:** Kafka  
- **Storage/CDN:** AWS S3 + CloudFront  
- **Processing:** FFmpeg, internal transcoding services  
- **Infra:** Docker, Kubernetes, Helm  
- **Monitoring:** Prometheus, Grafana, ELK  

---

## Setting Up (Generic Template)

```bash
git clone https://github.com/rohitshakya
cd olx-video-ads-service/
./gradlew build
