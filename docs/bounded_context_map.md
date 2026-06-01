# Bounded Context Map

## Introduction

The Real-Time Fraud Detection Platform is decomposed into multiple bounded contexts. Each bounded context owns a specific business capability, data model, and set of responsibilities. This separation improves scalability, maintainability, and independent deployment of services.

## Bounded Contexts

### 1. Transaction Context

**Responsibilities:**
- Receive transactions
- Validate transaction data
- Forward transactions for processing

### 2. Customer Context

**Responsibilities:**
- Manage customer profiles
- Store customer information
- Provide customer-related data

### 3. Fraud Detection Context

**Responsibilities:**
- Evaluate fraud rules
- Execute fraud detection logic
- Generate fraud indicators

### 4. Machine Learning Context

**Responsibilities:**
- Perform ML scoring
- Generate fraud probability scores
- Manage ML models

### 5. Graph Analysis Context

**Responsibilities:**
- Detect suspicious relationships
- Analyze network connections
- Identify fraud rings

### 6. Risk Assessment Context

**Responsibilities:**
- Calculate risk scores
- Combine results from multiple engines
- Generate final risk evaluation

### 7. Case Management Context

**Responsibilities:**
- Create fraud cases
- Assign cases to analysts
- Track investigation progress

### 8. Notification Context

**Responsibilities:**
- Send alerts
- Notify customers
- Notify fraud analysts

### 9. Audit Context

**Responsibilities:**
- Record system activities
- Maintain compliance logs
- Support auditing requirements

## Context Relationships

### Transaction Context → Fraud Detection Context
The Transaction Context sends transaction data to the Fraud Detection Context for fraud evaluation.

### Fraud Detection Context → Machine Learning Context
The Fraud Detection Context requests fraud probability scores from the Machine Learning Context.

### Fraud Detection Context → Graph Analysis Context
The Fraud Detection Context requests relationship analysis and fraud ring detection.

### Machine Learning Context → Risk Assessment Context
The Machine Learning Context provides ML risk scores.

### Graph Analysis Context → Risk Assessment Context
The Graph Analysis Context provides relationship risk indicators.

### Risk Assessment Context → Case Management Context
High-risk transactions result in fraud case creation.

### Risk Assessment Context → Notification Context
Risk decisions trigger notifications and alerts.

### All Contexts → Audit Context
All business activities are recorded in the Audit Context for compliance and monitoring.

## Benefits of Bounded Contexts

- Independent service deployment
- Better scalability
- Improved maintainability
- Clear ownership of business capabilities
- Easier system evolution
- Reduced coupling between services

## Conclusion

The bounded context approach divides the fraud detection platform into well-defined business domains. Each context focuses on a specific responsibility and communicates through clearly defined interfaces, enabling a scalable and maintainable microservices architecture.