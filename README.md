# FitFlow Redesign

## Overview

FitFlow is a fitness tracking application redesign focused on personalized workouts, social engagement, nutrition tracking and improved user experience.

## Technology Stack

- React Native + TypeScript
- React / Next.js
- Node.js + NestJS
- Python + FastAPI
- PostgreSQL
- AWS Cognito
- Redis
- Amazon S3
- SQS / Background Workers
- WebSockets / Socket.IO

## Repository Structure

- `frontend/` – Mobile and web clients
- `backend/` – Core API
- `ai-service/` – AI/ML service
- `docs/` – Comparison matrices, architecture and ADR

## Architecture

The system uses a cross-platform client layer, NestJS core API, FastAPI AI service, PostgreSQL database, Redis real-time/cache layer and AWS supporting services.

## Documentation

See the `docs` folder for:

1. Frontend technology comparison
2. Backend, database and authentication comparison
3. Weighted technology decision matrix
4. High-level system architecture
5. Architecture Decision Record

## Security

Do not commit secrets or credentials. Environment variables and managed secret services should be used for sensitive configuration.

## Development Setup

### Frontend
The mobile application uses React Native with TypeScript, while the web application uses React/Next.js.

### Backend
The main API is developed using Node.js and NestJS.

### AI Service
AI and machine-learning functionality is separated into a Python/FastAPI service.

## Repository

GitHub Repository: https://github.com/rashmigimhani/fitflow-redesign
