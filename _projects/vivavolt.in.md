---
layout: project
title:  "Viva Volt"
bannerDescription: "EdTech Platform for Online Learning and Assessments."
techUsed: PHP, CodeIgnitor, MySQL, Redis, APIs, Microservices, AWS
githubRepo: rohitshakya
comments: true
date: 2019-01-21
priority: 8
---

# VivaVolt – EdTech Learning & Assessment Platform

VivaVolt.in is an educational technology platform designed to make **learning, assessments, and progress tracking** simple and accessible for students and educators.  
Built with a modern Node.js backend, VivaVolt provides a seamless experience for taking quizzes, viewing results, managing courses, and tracking performance.

## Description

VivaVolt helps teachers and institutes conduct:

- **Online quizzes & assessments**  
- **Timed tests & adaptive question flows**  
- **Student performance tracking**  
- **Interactive learning modules**  
- **Topic-wise practice sessions**  
- **Auto-evaluated results & analytics**

The platform features clean UI, quick navigation, and fast-loading APIs optimized for thousands of concurrent students.

Students can simply join a course, attempt quizzes, and instantly review explanations, scores, and progress history.

### Key Capabilities

- Course management (topics, chapters, modules)
- MCQ and descriptive question support
- Test scheduling, duration control, and attempt limits
- Auto-grading with detailed analytics
- Leaderboards and performance insights
- Fast, secure REST APIs for frontend/mobile apps
- Redis-backed caching for high performance

---

## Technology Stack

- **Backend:** PHP, Laravel 
- **Database:** MySQL (normalized & indexed schema)  
- **Caching:** Redis for session and quiz caching  
- **Architecture:** Modular APIs + Microservice-ready design  
- **Other:** JWT authentication, request throttling, logging, cron-based cleanup tasks  

---

## Setting Up the Project

```bash
git clone https://github.com/rohitshakya
cd vivavolt/
npm install
cp .env.example .env
