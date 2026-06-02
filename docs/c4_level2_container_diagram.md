# C4 Level 2 Container Diagram

## Purpose
The Container Diagram shows the major containers (applications, databases, and supporting components) that make up the Real-Time Fraud Detection Platform and how they interact with each other.

## Containers

### API Gateway

**Responsibilities:**
- Entry point for all external requests
- Request routing
- Authentication and authorization
- Rate limiting

### Transaction Service

**Responsibilities:**
- Receive transactions
- Validate transaction data
- Publish transaction events

### Customer Service

**Responsibilities:**
- Manage customer profiles
- Provide customer information
- Maintain customer records

### Fraud Rules Service

**Responsibilities:**
- Execute fraud detection rules
- Evaluate business rules
- Generate rule-based risk indicators

### Machine Learning Service

**Responsibilities:**
- Perform fraud scoring
- Execute ML models
- Generate fraud probability scores

### Graph Analysis Service

**Responsibilities:**
- Detect suspicious relationships
- Identify fraud rings
- Perform network analysis

### Risk Assessment Service

**Responsibilities:**
- Combine results from multiple engines
- Calculate final risk score
- Produce fraud decisions

### Case Management Service

**Responsibilities:**
- Create fraud cases
- Assign investigations
- Track case lifecycle

### Notification Service

**Responsibilities:**
- Send SMS notifications
- Send email alerts
- Notify analysts and customers

### Audit Service

**Responsibilities:**
- Store audit records
- Maintain compliance logs
- Track system activities

### PostgreSQL Database

**Responsibilities:**
- Store transactional data
- Store customer data
- Store fraud cases

### Apache Kafka

**Responsibilities:**
- Event streaming
- Asynchronous communication
- Event distribution between services

## Container Interactions

### API Gateway → Transaction Service
Receives transaction requests and forwards them to the Transaction Service.

### Transaction Service → Apache Kafka
Publishes transaction events for downstream processing.

### Apache Kafka → Fraud Rules Service
Delivers transaction events for rule evaluation.

### Apache Kafka → Machine Learning Service
Delivers transaction events for ML scoring.

### Apache Kafka → Graph Analysis Service
Delivers transaction events for relationship analysis.

### Fraud Rules Service → Risk Assessment Service
Provides rule evaluation results.

### Machine Learning Service → Risk Assessment Service
Provides ML fraud scores.

### Graph Analysis Service → Risk Assessment Service
Provides graph-based risk indicators.

### Risk Assessment Service → Case Management Service
Creates fraud cases for high-risk transactions.

### Risk Assessment Service → Notification Service
Triggers customer and analyst notifications.

### All Services → Audit Service
Send audit events for compliance and monitoring.

### Services → PostgreSQL Database
Store and retrieve operational data.

## Technology Stack

| Component | Technology |
|------------|------------|
| API Gateway | Spring Cloud Gateway (with Resilience4j Rate Limiting & Circuit Breaking) |
| Microservices | Spring Boot 3.x (Java 21 LTS, Virtual Threads / Project Loom for high concurrency) |
| Event Streaming | Apache Kafka (Distributed Cluster with Schema Registry & KRaft Mode) |
| Database | PostgreSQL (with TimescaleDB extension for time-series metrics & connection pooling) |
| Container Platform | Docker (Multi-stage minimal distroless base images for security hardening) |
| Orchestration | Kubernetes (EKS/GKE with Horizontal Pod Autoscaling & GitOps via ArgoCD) |
| Monitoring | Prometheus (Metrics Ingestion) & Grafana (Distributed Dashboards with Loki/Tempo) |
| Security | OAuth 2.0 / OpenID Connect (Keycloak Identity Provider) & Stateless Asymmetric JWTs |

## Conclusion

The C4 Level 2 Container Diagram decomposes the Real-Time Fraud Detection Platform into major deployable containers. These containers communicate through Apache Kafka and REST APIs, enabling scalability, resilience, and independent deployment.