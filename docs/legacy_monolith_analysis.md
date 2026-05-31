# Legacy Monolith Analysis

## Introduction
ShieldPay Financial Services is a mid-tier credit card issuer that processes millions of transactions daily across India, Southeast Asia, and the Middle East. The company currently uses a legacy fraud detection system built as a Java monolith. This document analyses the existing monolithic architecture, its business capabilities, external integrations, and key architectural challenges.

## Current System Overview
The current fraud detection platform is implemented as a Java monolithic application developed in 2012. Over the years, the system has grown to approximately 1.2 million lines of code. All major functionalities such as transaction processing, fraud detection, customer management, case handling, audit logging, reporting, and machine learning scoring are tightly integrated into a single application.

The application is deployed on bare-metal servers in a Mumbai data centre and runs as WAR files on Apache Tomcat 8.5. Fraud detection rules are hard-coded within Java switch statements, making modifications difficult and time-consuming. More than 500 fraud rules exist within the codebase without any external configuration mechanism.

The system uses a single Oracle 19c database for storing transactions, customer profiles, fraud cases, audit logs, and reporting data. The database size has grown to approximately 45 TB, causing analytical queries to take around 3 seconds to execute.

Machine learning scoring is performed in batch mode every 15 minutes using a cron job. This creates a delay between transaction occurrence and fraud evaluation. Deployments are performed manually and require a four-hour maintenance window every Saturday night. The Oracle database also acts as a single point of failure because there are no read replicas or cross-region backups.

## Business Capabilities
The legacy monolithic system supports several important business capabilities:

### Fraud Rule Evaluation
Evaluates incoming transactions against predefined fraud detection rules to identify suspicious activities.

### Transaction Processing
Receives, validates, and processes payment transactions from different payment channels.

### Customer Profile Management
Stores and manages customer information, account details, transaction history, and behavioural data.

### Risk Scoring
Calculates risk scores using rule-based logic and machine learning models.

### Fraud Case Management
Creates and manages fraud investigation cases for review by analysts.

### Notification Management
Sends alerts and notifications to customers and fraud analysts regarding suspicious transactions.

### Audit Logging
Records all important system activities, fraud decisions, and operational events for compliance and investigation purposes.

### Reporting and Analytics
Generates reports, dashboards, and performance metrics for business and regulatory requirements.

## External Integrations
The fraud detection platform communicates with multiple external systems to perform its operations.

### Payment Networks
The system exchanges transaction data with payment networks such as Visa, Mastercard, and RuPay for transaction authorization and settlement activities.

### Core Banking System
Customer account information, balances, and transaction records are obtained from the core banking system.

### Customer Mobile Application
The mobile application allows customers to receive fraud alerts, transaction notifications, and account-related updates.

### Regulatory Reporting Systems
The platform generates reports and shares required information with regulatory authorities to ensure compliance with financial regulations.

### Third-Party Data Sources
External data providers may supply customer verification data, device intelligence, fraud intelligence, and risk-related information.

## Architectural Pain Points
The current monolithic architecture suffers from several technical and operational limitations.

### Single Database Bottleneck
All system components depend on a single Oracle database. As transaction volume increases, database performance becomes a major bottleneck.

### Hard-Coded Fraud Rules
Fraud detection rules are embedded directly in Java code. Any rule modification requires code changes, testing, and redeployment.

### Batch Machine Learning Scoring
Machine learning models process transactions every 15 minutes instead of in real time. Fraudulent transactions may remain undetected during this delay period.

### Single Point of Failure
The Oracle database has no read replicas or cross-region replication. A database failure can affect the entire platform.

### Manual Deployments
System deployments require manual intervention and a maintenance window, increasing operational risk and reducing agility.

### Limited Scalability
The monolithic architecture makes it difficult to scale individual functionalities independently. The entire application must be scaled together.

### Technology Constraints
All functionalities are tightly coupled within a single codebase, making technology upgrades and modernization difficult.

### Lack of Graph-Based Analysis
The existing system cannot effectively analyse relationships between customers, devices, accounts, and transactions for advanced fraud detection.

### Slow Innovation
Adding new features, fraud detection techniques, or integrations requires significant development effort because of the tightly coupled architecture.

## Conclusion
The analysis of the ShieldPay legacy fraud detection platform highlights several architectural and operational challenges. The monolithic design, hard-coded business rules, batch processing model, and centralized database limit scalability, maintainability, and fraud detection effectiveness. As transaction volumes and fraud sophistication continue to increase, the existing architecture is no longer sufficient to meet business and security requirements. A transition to a microservices-based architecture will improve scalability, resilience, deployment flexibility, and real-time fraud detection capabilities while supporting future innovation and business growth.

