# Activity 02: Backend, Database and Authentication

## 2.1 Backend Framework Comparison

| Criterion | Node.js / NestJS | Python / FastAPI | Go | Node.js / Express |
|---|---|---|---|---|
| Development Speed | Very high | High | Medium | Very high |
| Performance | High | High | Very high | High |
| Scalability | Excellent | Excellent | Excellent | Good-excellent |
| Real-Time Support | Excellent | Good | Excellent | Excellent |
| AI/ML Integration | Good; external AI service | Excellent | Good | Good |
| Security | Strong with proper configuration | Strong | Strong | Good with configuration |
| Maintainability | Excellent structure | Excellent | High | Medium |
| Learning Curve | Medium | Medium | Medium-high | Low |
| Ecosystem | Very large | Large | Large | Very large |
| FitFlow suitability | Excellent | Excellent | Very good | Good |

Node.js with NestJS is selected for the core API because its modular architecture, TypeScript support, WebSocket capabilities and maintainability suit the main transactional and real-time application layer.

FastAPI is retained as a separate service for specialized AI/ML processing.

---

## 2.2 Database Comparison

| Criterion | PostgreSQL | MongoDB | Firebase Firestore | DynamoDB |
|---|---|---|---|---|
| Data Model | Relational | Document | Document | Key-value/document |
| Complex Queries | Excellent | Good | Moderate | Good with planned access patterns |
| Transactions | Excellent | Good-excellent | Good | Excellent |
| Scalability | Excellent | Excellent | Excellent | Excellent |
| Real-Time Capability | Good with additional layer | Good with additional layer | Excellent with supporting services | Good |
| Health Data Handling | Excellent | Very good | Good | Very good |
| AI / Analytics | Excellent | Excellent | Good | Excellent |
| Relationships | Excellent | Moderate | Moderate | Limited |
| Cost | Predictable managed options | Moderate | Moderate | Usage based |
| Maintainability | High | High | High | Medium |

PostgreSQL is selected because FitFlow contains related users, workout plans, nutrition records, progress history and social information that benefit from relational queries, transactions and structured data integrity.

Redis can be used separately for caching and real-time pub/sub.

---

## 2.3 Authentication and Authorization

| Criterion | Firebase Auth | AWS Cognito | Auth0 | Supabase Auth |
|---|---|---|---|---|
| Ease of Integration | Excellent | Good | Excellent | Excellent |
| Social Login | Excellent | Excellent | Excellent | Excellent |
| MFA | Yes | Yes | Yes | Yes |
| OAuth / OIDC | Yes | Yes | Yes | Yes |
| Authorization | Custom claims / backend | Groups, attributes, IAM integration | Strong RBAC features | RLS-oriented |
| Scalability | Excellent | Excellent | Excellent | Excellent |
| Security | Strong | Strong | Strong | Strong |
| Cost | Low-medium | Low-medium | Medium-high | Low-medium |
| Maintainability | High | High | High | High |

AWS Cognito is selected because the proposed architecture uses AWS for core infrastructure and it provides a suitable identity-management layer.

The numerical gap between providers should not be treated as a benchmark; actual pricing, contractual coverage and service configuration must be verified before production use.

---

## 2.4 Security and Compliance

The following security and compliance considerations are important for the FitFlow system:

- Use HTTPS/TLS for all client-server and service-to-service communication.
- Encrypt sensitive data at rest, including database backups and stored objects.
- Use authentication tokens and role/resource-level authorization for protected operations.
- Apply input validation, rate limiting and secure API controls.
- Store credentials and API keys using managed secrets rather than source code.
- Use audit logging for sensitive actions and monitor application failures and security events.
- Apply data minimization, consent management, retention and deletion/export controls where applicable.
- GDPR/CCPA/HIPAA obligations depend on the actual data, users, partners, contracts and operational controls; selecting a technology alone does not create compliance.

---

## 2.5 Real-Time and AI Integration

Real-time functionality is required for community posts, challenge updates, notifications and synchronization.

NestJS can provide WebSocket endpoints, while Redis can be used for pub/sub and caching.

AI functionality can be separated into a Python/FastAPI service.

The main architecture can therefore be represented as:

React Native / React → NestJS API → PostgreSQL

NestJS API → FastAPI AI Service → ML Models

This separation keeps core application transactions independent from computationally intensive AI processing.

---

## 2.6 Cost and Maintainability

| Combination | Cost | Maintainability | Scalability | FitFlow Suitability |
|---|---|---|---|---|
| NestJS + PostgreSQL + Cognito | Medium | High | Excellent | Strong |
| FastAPI + PostgreSQL + Cognito | Medium | High | Excellent | Strong |
| Express + MongoDB + Firebase Auth | Low-medium initially | Medium | Excellent | Strong |
| Go + DynamoDB + Cognito | Medium | Medium | Excellent | Strong |

A modular monolith for the main NestJS API plus one dedicated AI service keeps operational complexity lower than immediately creating many independent microservices.

---

## 2.7 Recommended Technology Combination

| Layer | Technology | Justification |
|---|---|---|
| Mobile frontend | React Native + TypeScript | Cross-platform Android/iOS development |
| Web frontend | React / Next.js | Web-specific experience with shared TypeScript packages |
| Main backend | Node.js + NestJS | Structured and maintainable API architecture |
| AI/ML service | Python + FastAPI | Access to Python machine-learning ecosystem |
| Primary database | PostgreSQL | Relational health, workout, nutrition and progress data |
| Authentication | AWS Cognito | Scalable identity management and AWS integration |
| Object storage | Amazon S3 | Images and other large files |
| Caching / real-time support | Redis + WebSockets | Caching, pub/sub and live updates |
| Cloud | AWS | Integrated infrastructure and managed services |

---

## Final Technology Selection

For the FitFlow redesign, the selected backend technology combination is:

- **Core API:** Node.js + NestJS
- **AI/ML Service:** Python + FastAPI
- **Primary Database:** PostgreSQL
- **Authentication:** AWS Cognito
- **Object Storage:** Amazon S3
- **Caching / Real-Time:** Redis + WebSockets
- **Cloud Platform:** AWS

This combination provides a structured and maintainable backend while supporting real-time functionality, AI/ML processing, relational data management, authentication and scalable cloud infrastructure.
