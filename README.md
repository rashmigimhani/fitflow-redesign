# FitFlow Redesign

## Overview

FitFlow is a fitness tracking application redesign focused on personalized workouts, social engagement, nutrition tracking, and an improved user experience.

This repository contains the proposed project structure, technology comparisons, decision matrices, high-level architecture, and Architecture Decision Record (ADR) for the FitFlow redesign.

## Technology Stack

- Mobile: React Native + TypeScript
- Web: React / Next.js
- Core API: Node.js + NestJS
- AI/ML Service: Python + FastAPI
- Database: PostgreSQL
- Authentication: AWS Cognito
- Object Storage: Amazon S3
- Cache / Real-Time: Redis + WebSockets / Socket.IO
- Async Processing: SQS / Background Workers
- Analytics / Push: Firebase Analytics / Mixpanel and FCM/APNs where required
- Cloud Platform: AWS

## Repository Structure

fitflow-redesign/

- frontend/
  - mobile/ - React Native mobile application
  - web/ - React/Next.js web application
- backend/
  - src/ - Node.js/NestJS core API
- ai-service/
  - src/ - Python/FastAPI AI and ML service
- docs/
  - activity-01-frontend-comparison.md
  - activity-02-backend-database-auth.md
  - activity-03-decision-matrix.md
  - activity-04-architecture.md
  - architecture-diagram.png
  - adr-001.md
- .gitignore
- README.md

## Architecture

The proposed architecture separates the client applications, core API, AI/ML processing, authentication, data storage, caching, real-time communication, and asynchronous processing.

The main NestJS API handles users, workouts, nutrition, progress, community features, and notifications. A separate Python/FastAPI service handles specialized AI and machine-learning processing.

PostgreSQL is used as the primary relational database, while Redis supports caching and real-time functionality. AWS Cognito provides authentication, Amazon S3 provides object storage, and SQS/background workers support asynchronous processing.

## Documentation

The `docs` directory contains:

1. Frontend technology comparison
2. Backend, database, and authentication comparison
3. Comprehensive weighted technology decision matrix
4. High-level system architecture
5. Architecture diagram
6. Architecture Decision Record (ADR)

## Security

Sensitive credentials, passwords, API keys, and environment variables must not be committed to this repository.

The `.gitignore` file excludes environment files, dependencies, build outputs, Python cache files, IDE files, and other unnecessary files.

## Development Structure

### Mobile Frontend

The mobile application is designed to use React Native with TypeScript for cross-platform Android and iOS development.

### Web Frontend

The web application is designed to use React/Next.js.

### Core Backend

The main API is designed using Node.js and NestJS.

### AI/ML Service

AI and machine-learning functionality is separated into a Python/FastAPI service.

## Project

**Module:** IT3060 - Human Computer Interaction

**Lab Exercise:** Lab 05 - Technology Research, Comparison and System Design

**Project:** FitFlow Redesign
