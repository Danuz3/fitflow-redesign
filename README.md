# FitFlow Redesign

## Project Overview

FitFlow is a fitness tracking application undergoing a comprehensive redesign guided by human-centered design principles. This redesign targets five core user experience deficiencies identified through the case study:

- **Personalisation gap** — Resolved through on-device AI workout recommendations powered by TensorFlow Lite.
- **Social isolation** — Addressed via real-time community challenges and activity sharing.
- **High tracking friction** — Reduced through a streamlined, unified Flutter interface across all platforms.
- **Low motivation retention** — Improved with dynamic progress dashboards and social achievement sharing.
- **Nutrition logging friction** — Eliminated using camera-based computer vision for automatic food recognition.

## Project Objectives

The primary goal is to deliver a cohesive, AI-enhanced, and socially connected fitness experience across iOS, Android, and the web — all from a single codebase — while maintaining strict health data privacy standards.

## Selected Technology Stack

| Component | Technology | Purpose |
|---|---|---|
| Frontend | Flutter (Dart) | Single codebase targeting iOS, Android, and Flutter Web |
| Backend | Node.js + Express.js | REST API, WebSocket gateway, and service orchestration |
| Database | Firebase Firestore + Realtime Database | Structured health data and low-latency social features |
| Authentication | Firebase Auth | JWT-based identity and per-user Firestore security rules |
| AI/ML | TensorFlow Lite (flutter_tflite) + GCP AI Platform | On-device personalisation and cloud inference |
| Computer Vision | Google Vision API | Camera-based nutrition photo recognition |
| Cache | Redis | Session tokens and high-frequency read caching |
| Storage | Firebase Cloud Storage | User-uploaded photos and media |
| Analytics | Firebase Analytics + Crashlytics | Behaviour tracking and crash monitoring |
| Offline Cache | Hive / sqflite (SQLite) | Offline workout logging on the Flutter client |

> **Note:** PostgreSQL/Supabase may be introduced as a secondary store for complex relational reporting (e.g., subscription analytics) in future phases.

## Architecture Overview

The system follows a modern, decoupled microservices architecture. A Flutter client communicates through a Node.js + Express API Gateway to backend services including a specialised AI Microservice and a Computer Vision Service.

For full details, see the [High-Level Architecture documentation](docs/architecture.md).

## Repository Structure

```
fitflow-redesign/
├── README.md
├── .gitignore
├── frontend/               # Flutter project (iOS, Android, Web)
├── backend/                # Node.js + Express API server
│   └── src/
│       ├── routes/         # REST endpoint handlers
│       ├── services/       # Business logic modules
│       └── middleware/     # Auth validation and error handling
├── ai-service/             # TFLite assets and GCP AI connector
└── docs/
    ├── technology-comparison.md
    ├── decision-matrix.md
    ├── architecture.md
    ├── ADR.md
    └── architecture-diagram.png
```

## Key Features

- AI-personalised workout plans (on-device TFLite + GCP AI Platform)
- Real-time social feed and group challenges
- Camera-based nutrition tracking via Google Vision API
- Animated progress dashboard
- Offline-first architecture with local SQLite cache
- Cross-platform UI consistency via Flutter's rendering engine

## Documentation

- [Technology Comparison](docs/technology-comparison.md)
- [Weighted Decision Matrix](docs/decision-matrix.md)
- [High-Level Architecture](docs/architecture.md)
- [Architecture Decision Record](docs/ADR.md)
- [Architecture Diagram](docs/architecture-diagram.png)

## Academic Context

**IT3060 – Human Computer Interaction** | Lab Exercise 05
BSc (Hons) Information Technology — Sri Lanka Institute of Information Technology
Student: BULUMULLA D.M.D.D.B | IT23620070
