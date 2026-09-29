# Activity 04: Design a High-Level Architecture

## 4.1 Overall System Architecture

The architecture connects the technology decisions from Activities 01-03 into a high-level system.

It separates the following main responsibilities:

- Client applications
- Core API
- AI/ML processing
- Database
- Caching
- Real-time communication
- Authentication
- Cloud storage
- Asynchronous processing

## Architecture Diagram

![FitFlow High-Level Architecture](architecture-diagram.png)

---

## 4.2 Key Components

| Component | Technology | Responsibility |
|---|---|---|
| Client layer | React Native + React/Next.js | Mobile/web interface, offline storage and synchronization |
| Core API | Node.js + NestJS | Users, workouts, nutrition, progress, community and notifications |
| AI/ML service | Python + FastAPI | Personalized recommendations and specialized ML processing |
| Primary database | PostgreSQL | Users, plans, logs, social data and progress history |
| Cache / real-time | Redis + WebSockets | Caching, pub/sub and live application updates |
| Authentication | AWS Cognito | Authentication, identity and protected access |
| Object storage | Amazon S3 | Nutrition images, profile images and other large files |
| Async services | SQS / workers | Background processing, notifications and resource-intensive tasks |

---

## 4.3 Data Flows for Critical Features

### 4.3.1 Personalized Workout Plan

1. The user requests the Daily Flow or personalized workout plan.
2. The client sends an authenticated request to the NestJS API.
3. The backend retrieves relevant profile, goal, workout and progress information from PostgreSQL.
4. NestJS sends the required input to the FastAPI AI service.
5. The AI service processes the input and returns a recommendation.
6. The backend stores relevant recommendation information and returns the result to the client.
7. The personalized workout is displayed to the user.

### Simple Flow

React Native / React  
↓  
NestJS API  
↓  
PostgreSQL  
↓  
FastAPI AI Service  
↓  
Recommendation  
↓  
User

---

### 4.3.2 Private Social Sharing

1. The user creates a post, joins a challenge or interacts with a private social circle.
2. The request is sent through the authenticated NestJS API.
3. Authorization checks confirm that the requested action is allowed.
4. Community information is stored in PostgreSQL.
5. Redis pub/sub and WebSockets distribute permitted live updates.
6. Relevant users can receive notifications.

### Simple Flow

User  
↓  
React Native App  
↓  
NestJS API  
↓  
Authorization Check  
↓  
PostgreSQL  
↓  
Redis + WebSockets  
↓  
Other Authorized Users

---

### 4.3.3 Camera-Based Nutrition Tracking

1. The user captures a food image in the mobile application.
2. On-device processing can provide a fast initial result where appropriate.
3. Cloud processing can be requested when additional analysis is required.
4. The AI service processes the image and returns available nutrition-related information.
5. The confirmed nutrition record is stored in PostgreSQL.
6. The image can be stored in Amazon S3 under appropriate retention rules.
7. The result is displayed to the user for review.

### Simple Flow

Camera  
↓  
React Native App  
↓  
NestJS API  
↓  
FastAPI AI Service  
↓  
Nutrition Analysis  
↓  
PostgreSQL + Amazon S3  
↓  
Result to User

---

## 4.4 Security Considerations

| Security Area | Implementation Consideration |
|---|---|
| HTTPS/TLS | Encrypt communications between clients, backend APIs and supporting services |
| Authentication | Use AWS Cognito with appropriate OIDC/OAuth and MFA configuration |
| Authorization | Apply role and resource-level permissions for personal data and private communities |
| Encryption | Protect data at rest, backups and stored objects |
| API security | Validate inputs, rate-limit requests and apply secure API controls |
| Secrets | Use managed secrets storage and avoid credentials in source code |
| Privacy | Apply consent, minimization, retention and deletion/export controls where required |
| Audit / monitoring | Log sensitive operations and monitor system/security events |

---

## 4.5 Scalability Considerations

The FitFlow architecture should support future growth.

The following scalability considerations are included:

- Run multiple stateless NestJS instances behind a load balancer as traffic increases.
- Use managed PostgreSQL deployment with backups, indexing and scaling options.
- Use Redis to reduce repeated database reads and support pub/sub.
- Scale the FastAPI AI service independently from the core API.
- Use Amazon S3 for scalable image and file storage.
- Move expensive work to background queues and workers.
- Use monitoring and autoscaling mechanisms to identify and respond to resource demand.
- Use local storage and synchronization for supported offline workflows.

---

## 4.6 Integration Considerations

| Integration | Approach |
|---|---|
| Frontend -> API | Secure REST APIs using JSON |
| API -> AI | Internal REST APIs or asynchronous jobs for AI processing |
| API -> Database | Only backend services access PostgreSQL directly |
| Authentication -> API | Cognito tokens are validated before protected operations |
| Real-time | WebSockets / Socket.IO with Redis pub/sub |
| Files | S3 stores large objects; PostgreSQL stores metadata and references |
| External services | Future health, wearable, payment and notification integrations use controlled APIs |
| API versioning | Versioned endpoints and consistent error formats reduce client compatibility issues |

---

## 4.7 Final Architecture Summary

The proposed FitFlow architecture uses React Native for the mobile application and React/Next.js for the web application.

Both client applications communicate with the Node.js/NestJS core API.

The core API manages the main business logic and communicates with PostgreSQL for structured application data.

Python/FastAPI is used as a separate AI/ML service for personalized recommendations and nutrition-related processing.

AWS Cognito provides authentication, while Redis and WebSockets support caching and real-time communication.

Amazon S3 stores images and other large files, while SQS and background workers can handle asynchronous tasks.

This architecture separates the major responsibilities of the system and allows the core API and AI/ML workloads to scale independently.
