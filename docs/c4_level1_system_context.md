# C4 Level 1 System Context Diagram

## Purpose
The System Context Diagram provides a high-level view of the Real-Time Fraud Detection Platform, its users, and external systems that interact with it.

## Primary Users

### Fraud Analyst
Responsibilities:
- Review fraud alerts
- Investigate suspicious transactions
- Resolve fraud cases

### Customer Support Agent
Responsibilities:
- View fraud cases
- Assist customers
- Respond to fraud-related queries

### Compliance Officer
Responsibilities:
- Review audit logs
- Monitor regulatory compliance
- Generate compliance reports

## External Systems

### Payment Gateway
Responsibilities:
- Submit transaction requests
- Receive transaction decisions

### Customer Information System
Responsibilities:
- Provide customer profile information
- Supply customer risk data

### Notification Service
Responsibilities:
- Send SMS alerts
- Send email notifications
- Deliver fraud warnings

### Banking Network
Responsibilities:
- Process payment transactions
- Exchange settlement information

## Central System

### Real-Time Fraud Detection Platform

Responsibilities:
- Analyze transactions
- Evaluate fraud rules
- Perform machine learning scoring
- Execute graph analysis
- Calculate risk scores
- Generate fraud decisions
- Create investigation cases
- Maintain audit records

## System Interactions

### Fraud Analyst ↔ Real-Time Fraud Detection Platform
The Fraud Analyst receives fraud alerts, investigates suspicious activities, reviews risk assessments, and resolves fraud cases using the platform.

### Customer Support Agent ↔ Real-Time Fraud Detection Platform
The Customer Support Agent accesses customer fraud cases and assists customers affected by suspicious transactions.

### Compliance Officer ↔ Real-Time Fraud Detection Platform
The Compliance Officer reviews audit records, monitors regulatory compliance, and generates compliance reports.

### Payment Gateway ↔ Real-Time Fraud Detection Platform
The Payment Gateway sends transaction requests to the platform and receives approval or rejection decisions.

### Customer Information System ↔ Real-Time Fraud Detection Platform
The platform retrieves customer profile data and customer-related risk information from the Customer Information System.

### Notification Service ↔ Real-Time Fraud Detection Platform
The platform sends alert requests to the Notification Service, which delivers SMS and email notifications to customers and analysts.

### Banking Network ↔ Real-Time Fraud Detection Platform
The Banking Network exchanges transaction and settlement information with the platform.

## Conclusion
The C4 Level 1 System Context Diagram presents the Real-Time Fraud Detection Platform as the central system interacting with users and external systems. It illustrates the system boundary and the major relationships required for fraud detection, investigation, notification, and compliance operations.