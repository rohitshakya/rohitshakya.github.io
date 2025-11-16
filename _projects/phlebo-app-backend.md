---
layout: project
title:  "Phlebo App – Healthians"
bannerDescription: "Backend services powering Healthians’ Phlebo mobile application."
techUsed: PHP, Laravel, MySQL, MongoDB, Redis, Microservices, AWS, Cron Jobs, REST APIs
githubRepo: rohitshakya
comments: true
date: 2020-08-10
priority: 4
---

# Phlebo App Backend – Healthians

The **Phlebo App** is the internal mobile application used by Healthians’ phlebotomists to manage their daily workflow — from sample collection to patient verification to route planning.  
This backend system powers all core operations, ensuring fast, accurate, and reliable data flow between phlebotomists, labs, logistics, and customers.

---

## Description

The Phlebo backend enables Healthians field agents (phlebotomists) to:

- View & manage assigned orders  
- Navigate to patient locations  
- Verify patient details with secure authentication  
- Record sample collection status  
- Capture barcodes, photos & notes  
- Sync real-time status with central systems  
- Manage daily schedule, route & workload  
- Communicate issues back to operations  
- Trigger lab notifications & logistics workflows  

The system is designed for **real-time sync**, **offline support**, and **high performance** to support thousands of daily sample collections across multiple cities in India.

---

## Key Capabilities

- **Order Assignment Engine** – auto-assigns orders based on shift, location & skill  
- **Real-time Tracking** – phlebo location, ETA, and sample collection status  
- **Secure Check-in Process** – phone OTP, QR/barcode, or patient validation  
- **Route Optimization** – optimized sequence of patient visits  
- **Sample Handover Workflow** – phlebo → logistics → lab  
- **Offline-first support** – queueing & sync once the device reconnects  
- **Audit Logging** – every action tracked end-to-end  
- **Notifications** – push notifications for new orders & updates  
- **Phlebo Performance Dashboard** – targets, completion rate, TAT  

---

## Technology Stack

- **Backend:** PHP, Laravel  
- **Databases:** MySQL (transactions, reports), MongoDB (event logs, app metadata)  
- **Caching:** Redis for session and real-time order states  
- **Message Queues:** Kafka/SQS (optional depending on deployment)  
- **Hosting:** AWS EC2 / ECS  
- **Storage:** AWS S3 for images, documents & attachments  
- **Other:**  
  - JWT Auth  
  - Background Cron Jobs  
  - Geo Utilities (distance matrix, routing)  
  - Nginx reverse proxy  
  - Centralized logging (ELK)  

---

## Setting Up the Project

```bash
git clone https://github.com/rohitshakya
cd phlebo-backend/
npm install
cp .env.example .env
