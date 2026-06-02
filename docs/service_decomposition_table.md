# Service Decomposition Table

## Introduction

The Real-Time Fraud Detection Platform is divided into multiple microservices. Each service is responsible for a specific business capability and can be independently deployed and scaled.

| Service Name | Business Capability | Primary Responsibility | Input | Output |
| --- | --- | --- | --- | --- |
| Transaction Service | Transaction Processing | Receive and validate incoming transactions | Transaction Request | Validated Transaction |
| Customer Service | Customer Management | Manage customer profiles and account information | Customer Query | Customer Profile Data |
| Fraud Rules Service | Rule-Based Detection | Execute fraud detection rules | Transaction Data | Rule Evaluation Result |
| Machine Learning Service | ML Fraud Analysis | Generate fraud probability scores | Transaction Features | ML Risk Score |
| Graph Analysis Service | Relationship Analysis | Detect suspicious links and fraud rings | Transaction Data | Graph Risk Indicators |
| Risk Assessment Service | Risk Evaluation | Calculate final risk score and decision | Rule Result, ML Score, Graph Result | Risk Decision |
| Case Management Service | Fraud Investigation | Create and manage fraud cases | Fraud Alert | Fraud Case |
| Notification Service | Alert Management | Send alerts and notifications | Alert Request | Notification Status |
| Audit Service | Compliance and Logging | Store audit records and system events | System Events | Audit Logs |